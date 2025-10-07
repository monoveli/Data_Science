# Regressão Linear

## Conceitos-chave
- Variável resposta (dependente, eixo Y) e variável explicativa (independente, eixo X)
- Visualização inicial: scatter plot
- Correlação de Pearson: força e direção da relação linear

## Regressão Linear Simples
- Reta definida por intercepto (b0) e inclinação (b1)
- Ajuste por mínimos quadrados: minimiza a soma dos quadrados dos resíduos
- Interpretação: b0 é o valor previsto quando X=0; b1 é a variação média em Y para +1 em X
- Quando remover o intercepto? Somente quando há forte justificativa teórica de Y=0 em X=0 e os resíduos permanecem bem comportados

## Regressão Linear Múltipla
- Permite múltiplas variáveis explicativas (numéricas e categóricas)
- Interpretação de coeficientes mantendo demais variáveis constantes
- Categóricas: usar dummies (0/1) com baseline (equivalente ao one-hot com referência)

## Avaliação e diagnóstico
- R²: proporção da variabilidade explicada (use com cuidado)
- Gráficos e testes: resíduos vs. preditos (linearidade e homocedasticidade), QQ-plot e Shapiro-Wilk (normalidade)

## Como rodar
1) Instale dependências na raiz:
```bash
pip install -r requirements.txt
```
2) Abra os notebooks em `notebooks/`

## Dados
- Documente a fonte e instruções de download em `data/README.md`

## Referências
- Notas em `plano_estudos.md`
