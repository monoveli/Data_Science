🌟 Plano de Estudos para a Monica

📋 Visão Geral
Este plano de estudos foi desenvolvido para uma analista de dados que deseja migrar para a área de ciência de dados, com foco em aprendizado progressivo e estruturado. O objetivo é construir uma base sólida em estatística, programação e aprendizado de máquina, preparando para atuar com maior autonomia em projetos de modelagem preditiva, análise de dados e experimentação.
🎯 Objetivos de Desenvolvimento
Construir uma base forte em estatística, programação (principalmente em Python) e fundamentos de machine learning
Compreender os principais tipos de modelos preditivos (classificação, regressão, agrupamento, etc.) e suas aplicações práticas
Aprender a utilizar ferramentas comuns no dia a dia da ciência de dados, como Jupyter, pandas, scikit-learn e bibliotecas de visualização
Desenvolver raciocínio analítico para resolver problemas reais com dados
Praticar a criação de pipelines simples de machine learning, com supervisão
Evoluir gradualmente para ter mais autonomia em análises, modelagem e comunicação de resultados

Pre-work: Fundamentos de Engenharia de Software
Software Engineering for Data Scientists
Udacity Data Science Nanodegree
Tópico: Object-Oriented Programming 
Explore object-oriented programming (OOP), including classes, instances, magic methods, inheritance, and polymorphism. Utilize professional coding patterns for efficient Python software development.
Tópico: Code Reproducibility
Use and create virtual environments, write Python packages, manage file paths in a way that enables cross-platform compatibility, and ensure code quality through testing and linting.
Tópico: Object-Oriented Programming 
Explore object-oriented programming (OOP), including classes, instances, magic methods, inheritance, and polymorphism. Utilize professional coding patterns for efficient Python software development.




🧩 Módulo 1: Fundamentos de Modelagem Preditiva
Tópico 1: Regressão Linear (1 semana)
Objetivos:
Entender o conceito de regressão linear e suas aplicações
Aprender a fazer uma regressão no scikit-learn
Interpretar coeficientes
Exemplo em Python:
	 Prever o preço de casas com base em área e número de quartos
	 (usando pandas, matplotlib, scikit-learn)
Notebook com exemplo
Regressão Linear Simples:
Em uma regressão linear simples, a ideia é comparar duas variáveis quantitativas entre si. Nós dividimos as variáveis entre: 
Variável resposta, ou dependente, que é a variável que vamos querer prever (o comum é posicionar essa variável no eixo Y);
Variável explicativa, ou independente, que é a variável que vamos utilizar para prever a variável dependente (o comum é posicionar essa variável no eixo X).  
Uma vez que estamos lidando com duas variáveis quantitativas, um tipo de visualização comum e útil para compará-las é o Scatter Plot. 
Uma métrica que é relacionada com o Scatter Plot e quantifica a relação linearntre duas variáveis quantitativas - muito útil no nosso contexto de Regressão Linear - é o Coeficiente de Correlação de Pearson.  A partir dele podemos mensurar a força e a direção da nossa relação.  

A ideia da regressão linear é traçar uma reta que represente a relação entre as duas variáveis que estamos trabalhando. Para definir uma reta, precisamos de um intercepto (intercept) e uma inclinação (slope).
Intercept (b_0) - O valor predito para a resposta quando a variável dependente (X) é zero
Slope (b_1) - A mudança prevista na resposta para cada unidade aumentada na variável dependente (X)

When is it ok to remove the intercept in a linear regression model?
E como encontrar a linha que melhor define a relação entre duas variáveis?
O método mais comum é chamado de least-squares, que encontra a reta que minimiza 

Ou seja, minimiza a soma do quadrado das diferenças entre as distâncias da linha até os pontos. Representação visual: 


Como interpretar e avaliar uma regressão linear? 
R-squared: é o quadrado do coeficiente de correlação de Pearson. Normalmente definimos o R-squared como a quantidade de variabilidade da variável resposta que é explicada pela variável dependente no nosso modelo. 
Discussão sobre R-squared: casos em que a métrica não é tão útil
Regressão Linear Múltipla 
Na regressão linear múltipla, utilizamos mais de uma variável (podendo ser tanto quantitativas quanto categóricas) para prever a variável resposta.

Nesse caso, como vamos trabalhar com ambas variáveis categóricas e quantitativas, precisamos lembrar que o coeficiente de correlação apenas mede a relação entre duas variáveis quantitativas. 
Podemos interpretar os coeficientes na regressão linear múltipla como o aumento ou diminuição previsto na variável resposta para cada aumento de uma unidade na variável explicativa, mantendo todas as outras variáveis no modelo constantes.
Lembrete: O intercepto também é um coeficiente!
Para adicionar variáveis categóricas no nosso modelo, precisamos transformar elas em dummy variables. O jeito mais comum de realizar isso é um método de 0, 1 encoding, em que é criada uma coluna para cada valor possível distinto da coluna categórica menos um - já que o último valor pode ser inferido das outras colunas (baseline). Então, utiliza-se 0 ou 1 para indicar se aquele valor está presente ou não.  


É equivalente ao one hot encoding? 
Tópico 2: Pressupostos Estatísticos da Regressão 
Objetivos:
Verificar linearidade, normalidade dos resíduos, homocedasticidade, independência
Diagnosticar problemas nos modelos
Exemplo em Python:
	 Fazer gráficos de resíduos e histograma dos erros da regressão do topico1
	 (usar seaborn, statsmodels, scipy)
Pressupostos da Regressão Linear:
1. Linearidade
Os dados devem ter uma relação linear entre variáveis preditoras e resposta.
Como verificar? Gráfico de resíduos vs valores previstos (deve mostrar padrão aleatório)
2. Homocedasticidade (Variância Constante)
A variância dos resíduos deve ser constante ao longo de todos os valores previstos
Como verificar? Também pode ser verificado pelo gráfico de |resíduos| vs valores previstos ou Teste de hipóteses, por exemplo Teste de Levene
Link explicação teste de Levene



3. Normalidade dos Resíduos
Os resíduos devem seguir distribuição normal
Como verificar? Histograma dos resíduos, Q-Q plot, Teste de Shapiro-Wilk
Link para testes para verificação de normalidade


4. Independência dos Erros
Os resíduos devem ser independentes entre si -> Dados temporais ou espaciais podem violar este pressuposto
5. Ausência de Multicolinearidade
Variáveis preditoras não devem estar muito correlacionadas
Como verificar? Matriz de correlação, VIF (Variance Inflation Factor)
6. Outliers
Pontos que se afastam muito da tendência podem distorcer o modelo
Verificação: Boxplots, resíduos padronizados (|z| > 3)

Tópico 3: Regressão Logística
Objetivos:
Classificação binária
Intuição do logit e interpretação de outputs
Exemplo em Python:
	Prever se um cliente vai ou não clicar em uma campanha de marketing
	(usando pandas, scikit-learn, confusion_matrix)
A regressão logística é utilizada quando queremos prever uma variável categórica binária (quando só temos dois possíveis resultados, geralmente associados a um “sucesso” e um “fracasso". 
Na regressão linear, vimos que a variável resposta pode assumir qualquer valor sem restrição - mesmo valores que não fazem sentido. Na regressão logística a variável resposta é limitada a uma probabilidade entre 0 e 1.

Para fazer uma regressão logística, precisamos:
Atribuir valores de 0 e 1 para a coluna categórica binária que iremos usar como variável resposta. Por exemplo, para o exemplo que vamos trabalhar de entender se um cliente clicou ou não em uma campanha de marketing, o clique pode ser atribuído ao 1 (o “sucesso”) e o não-clique ao 0. 
Um modelo linear vai prever o logaritmo da razão de chances, em que:
Razão de chances: a probabilidade de um evento ocorrer sob a probabilidade dele não ocorrer
Logaritmo: Controla a razão de chances para ser um número entre 0 e 1
Com algumas transformações matemáticas, a função passa a ter essa cara: 

que resolve a probabilidade diretamente! Essa função é chamada Sigmóide.
A função Sigmóide é responsável por pegar um valor de uma linha de regressão linear e mapear entre 0 e 1.



Cada βi representa a mudança no log-odds de p quando a variável  aumenta em 1 unidade, mantendo as outras fixas.
Log-odds não é intuitivo → por isso a gente converte para odds ratio.
Se OR>1 →  aumenta as chances do evento acontecer (ex.: maior chance de compra).
OR<1 →  diminui as chances.
OR=1 →​ não afeta a probabilidade.








Para avaliar um modelo de regressão logística, a avaliação mais comum é a acurácia, que mede a proporção de acertos. Porém, a acurácia nem sempre é a melhor medida, principalmente em datasets muito desbalanceados. 
Matrizes de confusão: 

Recall: Positivo Verdadeiro (Pos,Pos) / (Positivo Verdadeiro (Pos,Pos) + Falso Negativo (Pos,Neg). Ou seja, de todos os itens positivos de verdade, quantos foram corretamente classificados como positivos. 
Precision: (Pos,Pos) / (Positivo Verdadeiro (Pos,Pos) + Falso Positivo (Neg,Pos)). Ou seja, de todos os itens preditos como positivos, quantos realmente são positivos. 
Material sobre curva ROC e AUC
Curva ROC
A curva ROC é uma representação visual da performance do modelo em todos os limites. Ela é desenhada calculando a taxa de verdadeiros positivos (TPR, na sigla em inglês) e a taxa de falsos positivos (FPR, na sigla em inglês) em todos os limites possíveis (na prática, em intervalos selecionados) e, em seguida, representando a TPR em relação à FPR. Um modelo perfeito, que em algum limite tem um TPR de 1,0 e um FPR de 0,0, pode ser representado por um ponto em (0, 1) se todos os outros limites forem ignorados ou pelo seguinte:

Área sob a curva (AUC)
A área sob a curva ROC (AUC) representa a probabilidade de o modelo, se receber um exemplo positivo e negativo escolhido aleatoriamente, classificar o positivo como melhor do que o negativo.
A AUC é uma medida útil para comparar a performance de dois modelos diferentes, desde que o conjunto de dados esteja aproximadamente equilibrado. O modelo com maior área sob a curva geralmente é o melhor.


Material muito bom sobre curva ROC, AUC e Reg Log
Tópico Extra: Padronização/Normalização dos Dados

Material de apoio - Artigo no Medium sobre padronização
Material de apoio - Google Developers sobre normalização
Objetivos:
Entender a importância do dimensionamento de dados em Machine Learning
Conhecer diferentes métodos de padronização e normalização
Saber quando aplicar cada técnica
Por que Padronizar/Normalizar?
Problema com dados não dimensionados:
Algoritmos baseados em gradiente podem ter convergência lenta ou não convergir
Modelo pode dar peso excessivo a features com escalas maiores
Risco de valores NaN quando features têm valores muito altos
Performance preditiva degradada
Decision Trees e Random Forest são robustos e não necessitam dimensionamento* -> ver com mais profundidade nos módulos das árvores
Padronização
Resulta em média = 0 e desvio padrão = 1 e mantém a forma da distribuição original
Normalização:
Coloca variáveis no intervalo [0,1] ou [-1,1] se houver valores negativos -> comprime todos os valores dentro de um intervalo específico
Métodos de Padronização:
StandardScaler

Quando usar: Dados com distribuição aproximadamente normal, algoritmos como regressão linear e logística, quando não temos outliers extremos
MinMaxScaler

Quando usar: Distribuição não é normal, desvio padrão pequeno, quando queremos preservar a distribuição original
Não trata outliers efetivamente
RobustScaler

Quando usar: Presença de outliers (baseado em percentis, não em média/desvio padrão ou seja reduz impacto negativo dos outliers)
Métodos de Normalização:
Escalonamento Linear (Linear Scaling)
Converte valores para intervalo padrão [0,1] ou [-1,+1]
Quando usar: Limites dos dados são estáveis ao longo do tempo, poucos outliers não extremos, distribuição aproximadamente uniforme
Exemplo: idade humana (0-100 anos)
Escalonamento Z-Score
Mesmo que StandardScaler - mais comum que escalonamento linear
 Escalonamento Logarítmico
Para dados com distribuição muito assimétrica
Regra Geral de Escolha:
Situação
Método Recomendado
Distribuição normal, sem outliers
StandardScaler
Distribuição não-normal
MinMaxScaler
Presença de outliers
RobustScaler
Dados com muita disparidade de escalas
Normalização obrigatória


Importante lembrar: Se normalizar no treino, precisa normalizar na predição também.

Tópico 4: Avaliação de Modelos + Regularização
Objetivos:
R², MAE, MAPE, RMSE (para regressão)
Introdução a overfitting e regularização (Ridge, Lasso, ElasticNet)
Exemplo em Python:
	Comparar os resultados de uma regressão linear simples com Ridge e Lasso
(usar sklearn.linear_model)

Overfitting
Acontece quando um modelo aprende os dados de treinamento tão bem, que confunde ruído/especificidades dos dados de treino como padrões. Isso leva a uma performance ruim para dados que não sejam de treino.
Em termos mais técnicos, significa que o modelo não é generalista.
Como isso aparece? Como detectar overfitting?
Quando a métrica escolhida para avaliação possuí resultados muito bons para os dados de treino e para os dados de teste, resultados bem piores.
Quando notamos introdução de ruído excessivo nos dados de previsão.
Exemplo prático de caso de Overfitting dentro do contexto de SR:
Quando utilizávamos o modelo Prophet para prever pedidos, como não especificamos tanto a sazonalidade, ele começou a aprender os ruídos e variações pequenas como sazonalidades! O resultado era uma previsão sem sazonalidade clara e muita introdução de ruído, mesmo quando os dados de input eram estáveis.
—
Regularização: artigo no Médium sobre
Regularização é o processo de adicionar informações para prevenir over-fitting.
LASSO(Least Absolute Shrinkable and Selection Operator) - L1 Regularization:
Adicionamos uma “Penalidade” na função objetivo baseado nos valores absolutos dos coeficientes.
O termos de regularização L1 é a soma dos valores absolutos dos coeficientes multiplicado por um parâmetro λ.
 Se λ é grande pode suprimir os coeficientes de features importantes (alta correlação).
Se λ é 0, a loss vira RSS. 
O tamanho de λ define se queremos evitar under-fitting (quando λ é grande) ou over-fitting (quando λ é pequeno).

Na prática, o efeito é: se temos uma linha passando por todos os pontos de dados, a soma quadrática dos erros vai ser 0 (primeira parte da função). O termo adicional que colocamos (segunda parte da função) deve ser minimizado para minimizar a função de custo. Mas, fazendo isso, faremos a linha não passar exatamente por todos os pontos, e isso previne overfitting. 
RIDGE Regularizarion - L2 Regularization:
É uma variação do LASSO, em que o termo de penalização não pode ser zerado já que elevamos o coeficiente ao quadrado.

—
Elastic-Net Regression
É um mix entre LASSO e Ridge, que adiciona os dois termos (L1 e L2).
Por que misturar?
 L1 força alguns coeficientes a virar exatamente zero (feature selection).
L2 encolhe todos os coeficientes proporcionalmente (lida bem com multicolinearidade).
Elastic-Net traz o melhor dos dois: faz seleção de variáveis e mantém estabilidade quando há correlação alta entre features.
—
Quando usar cada um? 
Se você não realizou feature selection nos seus dados, e tem várias features com alta correlação e precisa tirar algumas que não são necessárias, LASSO é uma melhor opção. 
Se o número de features é maior que o número de observações e temos multicolinearidade, RIDGE é uma melhor opção.
Se temos os dois casos, usar o Elastic-Net.
—
Resumo das métricas de avaliação

———————————————————————————————————————
Módulo Extra: Gradiente Descendente 
Objetivos:
Entender como os algoritmos "aprendem" minimizando erros
Visualizar o conceito de descida em uma função de custo
Compreender learning rate
Exemplo em Python:
Implementar gradiente descendente simples para regressão linear (usando numpy, matplotlib para visualizar a descida)
Material - Médium
Notebook
O gradiente descendente é o algoritmo que permite que os modelos de machine learning "aprendam". É o processo matemático por trás de praticamente todos os algoritmos ( regressão linear, regressão logística, redes neurais, etc.)
A ideia dele é que, uma vez que temos uma função de custo (que mede o quanto errado seu modelo ta) e quer encontrar os parâmetros que minimizam essa função. O gradiente descendente é o método para chegar nesse ponto de erro mínimo.

Como funciona?
Fazemos o primeiro chute de valores aleatórios para os parâmetros do modelo
Calculamos o erro atual do modelo usando a função de custo
Calculamos a derivada da função de custo (o gradiente) 
Interpretamos a derivada para entender em em qual direção devemos ajustar os parâmetros para reduzir o erro
Atualizamos os parâmetros na direção que reduz o erro
Repetimos até convergir (até o erro parar de diminuir significativamente)

Learning Rate
O learning rate controla o tamanho dos passos que vamos dar para ajustar os parâmetros:
Learning rate muito alto: pode fazer o algoritmo pular o ponto ótimo e nunca convergir. O erro vai ficar oscilando ou até aumentando.
Learning rate muito baixo: vai convergir muito devagar. Pode levar muito tempo para treinar.



Funções de custo/loss function
É sempre escolhido a mesma da métrica de avaliação do modelo? Como escolher uma loss boa? 

———————————————————————————————————————

Módulo Extra: Feature Selection 
Objetivos:
Identificar features mais relevantes para o modelo
Reduzir dimensionalidade dos dados
Melhorar performance e interpretabilidade
Exemplo em Python:
Selecionar as 5 melhores features de um dataset de marketing usando pelo menos um método univariado e dois métodos multivariados (que consideram interações entre features na seleção), e pro mesmo dataset aplicar PCA. Comparar os resultados.

Feature Selection é onde identificamos e selecionamos as variáveis mais relevantes para o modelo. A ideia é manter apenas as features que contribuem significativamente para a performance, e tirar variáveis redundantes, irrelevantes ou que vão introduzir ruído.
Ajuda em:
Redução de overfitting: menos variáveis diminuem a complexidade do modelo
Melhoria na interpretabilidade: modelos com menos features são mais fáceis de explicar
Redução do tempo de treinamento: menos dados para processar
Redução de ruído: eliminação de variáveis que não agregam valor preditivo
Métodos Univariados
Avaliam cada feature individualmente em relação ao target, sem considerar interações entre features. Geralmente são mais rápidos de calcular, simples de interpretar e bons métodos baselines, mas ignoram interações entre features e podem descartar features importantes que só funcionam em combinação
Exemplos comuns:
SelectKBest: seleciona K melhores features baseado em teste estatístico
Chi-squared: para features categóricas e target categórico
F-test (ANOVA): para features numéricas e target categórico
Métodos Multivariados
Consideram interações entre features durante a seleção.
Wrapper Methods
Usam o próprio modelo para avaliar subconjuntos de features. 
Recursive Feature Elimination (RFE):
Treina modelo com todas as features
Remove features menos importantes iterativamente
Repete até atingir número desejado de features
Forward/Backward Selection:
Forward: adiciona features uma por vez
Backward: remove features uma por vez
Embedded Methods
Seleção de features integrada ao processo de treinamento do modelo. É o caso das Regularizações que vimos anteriormente. 
Feature Importance (Tree-based models): Random Forest, XGBoost fornecem importância das features
Redução de Dimensionalidade vs Feature Selection
Feature Selection: Mantém features originais (interpretabilidade preservada), seleciona subconjunto das variáveis existentes, features selecionadas têm significado original
Redução de Dimensionalidade (ex: PCA): Cria novas features como combinações das originais, reduz dimensões através de transformações matemáticas, features resultantes podem perder interpretabilidade original
Principal Component Analysis (PCA)
Como Funciona:
Padroniza as variáveis (média 0, desvio padrão 1)
Calcula matriz de covariância
Encontra autovalores e autovetores
Ordena componentes por variância explicada
Seleciona primeiros N componentes
Detalhes sobre o cálculo
Características:
Componentes são ortogonais: não correlacionados entre si
Ordenados por variância: primeiro componente explica mais variância
Combinação linear: cada componente é soma ponderada das features originais
Preservação de variância: componentes mantêm máxima variância possível
Quando Usar PCA: Quando temos features altamente correlacionadas, muitas features numéricas, necessidade de reduzir dimensionalidade mantendo informação



Modelo
Default Loss
Observações sobre Learning Rate
Regressão Linear (sklearn)
MSE (Mean Squared Error)
scikit-learn usa otimização direta (não gradiente) por padrão. Se usar SGDRegressor, a learning rate influencia a velocidade de convergência.
Regressão Logística (sklearn)
Log Loss / Cross-Entropy
Otimiza via liblinear ou lbfgs por padrão; learning rate só se usar SGDClassifier.
Random Forest / XGBoost / LightGBM / CatBoost
Não usa loss “tradicional” no scikit-learn; internamente usam critérios como Gini, MSE ou Log Loss
Learning rate existe em boosting (learning_rate) e controla o passo de cada árvore na soma ponderada.
Redes Neurais (PyTorch / TensorFlow)
Nenhuma por padrão; você passa explícito (nn.MSELoss, nn.CrossEntropyLoss)
Learning rate define o tamanho do passo do gradiente; muito grande → instável, muito pequeno → lento.
Classificação Binária (PyTorch)
nn.BCEWithLogitsLoss ou nn.BCELoss
Mesma lógica: learning rate não muda a função, só a velocidade de aprendizado.
Classificação Multiclasse (PyTorch)
nn.CrossEntropyLoss
Learning rate afeta convergência; se muito alta pode explodir gradientes.

1️⃣ Qual é a loss function default?
Regressão Linear (scikit-learn, PyTorch, TensorFlow) → default normalmente é Mean Squared Error (MSE).
Regressão Logística / Classificação Binária → default normalmente é Binary Cross-Entropy (Log Loss).
Classificação Multiclasse → default normalmente é Categorical Cross-Entropy.
Redes neurais genéricas → depende da camada de saída e do framework; por exemplo, nn.Linear sozinho não define loss, você passa explicitamente.
💡 Resumo: cada modelo já “assume” uma loss que faz sentido para o tipo de problema (regressão ou classificação).
———————————————————————————————————————

🌳  Módulo 2: Modelos com Árvores e Ensemble
Tópico 1: Árvores de Decisão
Objetivos:
Lógica de divisão dos dados
Vantagens e limitações
Exemplo em Python:
	 Construir uma árvore para classificar tipo de cliente com base em idade e renda
	(DecisionTreeClassifier, plot_tree)
Tópico 2: Random Forest
Objetivos:
Combinar várias árvores para melhorar performance
Feature importance
Exemplo em Python:
	 Prever churn com Random Forest e plotar a importância das variáveis
	(RandomForestClassifier)
Tópico 3 – XGBoost (Extra: LightGBM, CatBoost)
Objetivos:
Introdução a modelos gradient boosting
Ajuste de hiperparâmetros básicos
Exemplo em Python:
	 Usar xgboost para prever se um cliente vai comprar ou não
	(com avaliação AUC, curva ROC)
Tópico 4 – Interpretabilidade de Árvores
Objetivos:
Feature importance, SHAP values
Explicar modelos para o negócio
Exemplo em Python:
	 Usar SHAP para mostrar o impacto das variáveis no modelo do topico anterior
	(shap.TreeExplainer)
———————————————————————————————————————
🚀 Módulo 3: Pipeline, Deploy e Boas Práticas 
Tópico 1: Pipelines de Machine Learning e Pré-processamento
Objetivos:
Compreender o ciclo completo de um pipeline com scikit-learn
Aplicar boas práticas de pré-processamento: imputação, escalonamento, encoding
Evitar problemas comuns como data leakage
Modularizar o código e tornar reproduzível
Conceitos-chave:
Pipeline, ColumnTransformer, SimpleImputer, StandardScaler, OneHotEncoder
Separação entre treino e teste antes do pré-processamento
Funções reutilizáveis (def preprocessar_dados(), def treinar_modelo())


Exemplo em Python:
 Criar um pipeline completo que:
Carrega os dados de clientes
Trata valores nulos e codifica variáveis categóricas
Treina um modelo de churn prediction
Avalia com métricas como ROC AUC e precisão
Tópico 2: Fundamentos de Produção: Docker, Cloud e CI/CD
Objetivos:
Entender o que é necessário para colocar um modelo no ar
Aprender o básico de Docker para empacotar código
Conhecer o ciclo CI/CD (ex: GitHub Actions)
Ter noções iniciais de uso da nuvem para cientistas de dados (S3, notebooks gerenciados, endpoints)
Exemplo em Python:
Exemplo prático sugerido:
Criar um requirements.txt
Versionar um projeto simples com GitHub
Criar um Dockerfile básico com Python e scikit-learn
Rodar o container localmente
Ativar um fluxo automático com GitHub Actions (por exemplo: rodar testes)
———————————————————————————————————————
🧠 Módulo 4: Aprendizado Não Supervisionado (Clustering)
Objetivos:
Entender os principais métodos de agrupamento (ex: K-means)
Aplicar clustering para segmentação de dados sem rótulos
Avaliar qualidade do agrupamento com métricas simples (ex: índice de silhueta)
Exemplo em Python:
	Usar KMeans do scikit-learn para segmentar clientes com base em variáveis numéricas
Visualizar clusters com matplotlib ou seaborn
———————————————————————————————————————
🤖 Módulo 5: Introdução a Redes Neurais e Machine Learning / IA

Objetivos:
Entender o que são redes neurais e por que são importantes no contexto de Machine Learning e Inteligência Artificial
Conhecer a estrutura básica de uma rede neural: camadas, neurônios, ativação
Compreender conceitos simples como forward propagation, função de perda e backpropagation (intuitivamente)
Aprender a criar um modelo de rede neural simples usando bibliotecas como Keras/TensorFlow ou PyTorch
Comparar redes neurais básicas com modelos tradicionais como regressão e árvores
Conteúdo:
O que é uma rede neural: inspiração biológica e aplicação computacional
Camadas: entrada, escondidas, saída
Funções de ativação comuns: ReLU, Sigmoid, Softmax
Treinamento básico: como a rede “aprende” ajustando pesos
Exemplos de aplicação: reconhecimento de imagem, classificação de texto, séries temporais
Exemplo em Python:
Construir uma rede neural simples para classificação binária usando Keras
———————————————————————————————————————
🔍 Módulos extras (opcionais, para revisão rápida)
Extra 1: Análise Exploratória e Storytelling com Dados
Recapitular boas práticas de visualização e interpretação
Técnicas rápidas para comunicação clara de insights


Extra 2: Testes de Hipóteses e AB Testing
Revisar conceitos de testes estatísticos básicos (t-test, p-valor
Entender o ciclo de um teste A/B simples


🚀  Módulo Carreira
O que do que você anotou até agora acha que já domina de verdade?
Tenho começado a dominar as situações em quando eu deveria/poderia utilizar uma regressão, como interpretar os resultados, quando pode ser útil mesmo sem ser no contexto preditivo - por exemplo, essa semana precisei mesurar qual era a diferença média entre conversões entre variantes com custos diferentes. Como alguns desses dados estavam bem esparsos somente tirar a diferença entre pares adjacentes não estava gerando uma resposta legal, então fitei uma regressão e usei o coeficiente, multiplicado pela diferença média entre custos, pra me dar essa diferença média! Os resultados fizeram bem mais sentido, e também consegui correlacionar o R2 pra interpretação. A matemática por trás da coisa também tem feito bem mais sentido.
O que você sente que ainda não conseguiu transformar em prática, só está no papel?
Ainda não consegui transformar em prática talvez a parte de transformações - tanto normalização quando regularizações, por mais que tenha conseguido aplicar o código e entendido a teoria, acho que ajudaria muito um exemplo por exemplo, pra regularização, em que eu tenho um overfitting para resolver, por que nos estudos que fiz acabou não tendo diferença significativa entre os resultados usando as técnicas.
Se tivesse que explicar em 5 minutos o que estudou essa semana para alguém da área de negócio, como faria?
	“ Essa semana, estudei sobre maneiras de resolver quando temos um problema de falta de adaptação dos dados. Por exemplo, se estamos querendo prever pedidos e utilizamos dados da época de Big Brother, o modelo pode aprender alguns padrões relativos às variações pelo BBB - por exemplo, alta de pedidos na prova do anjo. O problema é que não temos BBB o ano todo e queremos uma solução que vai funcionar independente dessas especificidades da época, ou seja, que o modelo aprenda o comportamento geral da coisa, que é constante o ano todo (por exemplo: alta de pedidos no final do semana) do que comportamento específicos do período que estamos dando para o modelo aprender. Pra isso, temos algumas soluções matemáticas que nos ajudam com esse problema, desajustando o modelo de propósito em alguns pontos que sejam muitos específicos e fora do padrão geral!”
Qual diferença prática você enxerga entre o que um Analista de Dados faz e o que um Cientista de Dados faz com o mesmo conjunto de dados?
Acho que varia como cada um tem que entender o problema. Enquanto um Analista de Dados tem que se aprofundar muito na parte de diagnóstico, de entender o que aconteceu e o que pode ter impactado para os resultados, o Cientista de Dados tem que fazer isso de forma mais “profunda”- não necessariamente tal nuance vai acarretar em um problema para o modelo, mas o cientista de dados tem que se antecipar e já se preparar para isso.
Se tivesse que priorizar o próximo tema de estudo com base no que você já sabe, qual escolheria e por quê?
Antes de entrar em modelos de Árvore, eu escolheria priorizar estudar a parte de Gradiente Descendente, que vejo que é um tópico em comum entre vários assuntos de Ciência de Dados, e a parte de diferentes features selection - que entram junto com as técnicas de preparar os dados para os modelos. 
Você sente que seu caderno está mais como um resumo teórico ou um guia de prática?
Mais como um resumo teórico e um compilado de referências úteis, mas pra mim é o que mais me ajuda a aprender e fixar os conceitos. Às vezes o exercício de ter que escrever as coisas de um jeito diferente já ajuda a pegar se eu realmente entendi o que foi passado ou não.
Como podemos transformar suas anotações em algo que vire portfólio (GitHub, Kaggle, Medium)?
Podemos criar um Gitlab com tanto às anotações quando os notebooks práticos!
De 0 a 10, qual sua confiança no que estudou essa semana? O que faria subir esse número?
7 - acho que entra no mesmo ponto de “como eu conseguiria forçar um overfitting para conseguir agir na resolução desse problema?”

