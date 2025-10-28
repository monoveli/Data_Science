# Tópico: Random Forest, Bootstraping e Cross-Validation

## RandomForest

Relembrando o tópico anterior… árvores de decisões são como uma série de perguntas simples que dividem seus dados em grupos mais homogêneos. O problema é que: 
1. As árvores são muito instáveis. Uma leve mudança no conjunto de dados, a árvore pode mudar completamente.
2. Elas também tendem ao overfitting, como vimos o que acontece ao não regularmos o parâmetro de número de amostras.

Para resolver esses problemas, usamos o RandomForest. Random Forest é uma coleção de árvores de decisão, cada uma treinada de forma ligeiramente diferente, e as previsões finais são baseadas em votação (para classificação) ou média (para regressão).


## Bootstraping _________________________________________________________________________________________________________

Para entendermos como fazemos essas árvores serem diferentes, primeiro precisamos entender o que é o Bootstrapping: uma técnica que nos ajuda a simular novas amostras a partir da que já temos.

Isso é feito tirando várias amostras aleatórias com reposição da amostra original. A parte da reposição é importante, significa que quando sorteamos um valor, ele volta para o conjunto antes do próximo sorteio e  pode ser escolhido de novo. Isso faz com que alguns valores se repetem e outros podem nem aparecer. Esse processo é repetido diversar vezes, gerando várias amostras bootstraps. 

Cada vez, obtemos uma nova amostra e calculamos a métrica de interesse: média, mediana, desvio padrão, ou qualquer estimador. O resultado é uma distribuição de estimativas, a distribuição Bootstrap. 

Utilidades da distribuição Bootstrap: Podemos descobrir qual a certeza que temos no nosso estimador (variabilidade e erro padrão das estimativas) e o range possível do estimador (construir intervalos de confiança).
_________________________________________________________________________________________________________

Com o conceito de Bootstraping, podemos entender como o algoritmo introduz duas fontes de aleatoriedade:

1. **Amostras aleatórias de dados (Bootstrapping)**
Cada árvore é treinada com uma amostra aleatória do conjunto de dados com reposição (amostra bootstrap).

2. **Amostras aleatórias de variáveis (Random Subset of Features)**
Quando a árvore decide em qual variável dividir, ela não olha todas as variáveis e sim apenas um subconjunto aleatório delas, fazendo com que as árvores não sejam todas idênticas.


Esses dois aspectos fazem com que tenhamos diversidade entre as árvores, o que é essencial para reduzir o overfitting.

Depois que todas as árvores são treinadas:

* Se for classificação, cada árvore “vota” em uma classe e a classe com mais votos é a previsão final.
* Se for regressão, cada árvore dá um número e o resultado final é a média dos números.

O resultado é muito mais estável e preciso do que usar uma única árvore. Isso funciona porque ao combinar muitos modelos fracos mas diferentes, o erro aleatório de cada um se cancela, e o resultado final é mais robusto. 

Avaliação: Como cada árvore é treinada com uma amostra bootstrap, cerca de um terço dos dados não são usados no treino de cada árvore. Esses dados são chamados de Out-of-Bag e são usados para avaliar o erro de cada árvore. É a métrica de avaliação padrão que vai aparecer no método score do sklearn para esse modelo.
_________________________________________________________________________________________________________

## CrossValidation

Com o conceito de *Overfitting*, vimos que não podemos avaliar o modelo utilizando dados que ele já “viu” (dados de treino). O Cross-Validation surge como um método para nos permitir estimar o erro verdadeiro do modelo, sem precisar de novos dados.

A ideia é dividir os dados em partes e usar algumas partes para treinar o modelo e as outras para testar, alternando essas funções até que todos os dados tenham sido usados para teste ao menos uma vez.  

K-Fold Cross-Validation: 
1 . Dividimos os dados em K partes aproximadamente iguais.
2. Escolhemos um dos K folds como teste e usamos os outros para treinar o modelo. 
3. Calculamos o erro no fold de teste.
4. Repetimos o processo K vezes e a cada vez, um fold diferente é usado como teste.

No fim, tiramos a média dos erros dos K testes, que será a estimativa final do desempenho do modelo. A ideia é similar a do Bootstrapping de combinar erros individuais para estimar generalização.

Outras variações são:

* Leave-One-Out (LOOCV): um caso extremo em que cada fold tem apenas uma observação.O modelo é treinado em todos os outros n−1 pontos e testado naquele único. É muito exato, mas computacionalmente caro.
* Stratified K-Fold: Usado em problemas de classificação, garante que cada fold mantenha a proporção original das classes. 
