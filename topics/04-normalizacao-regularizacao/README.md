# Padronização, Normalização e Regularização

## Por que dimensionar os dados?
- Convergência de métodos baseados em gradiente
- Evitar que features em grandes escalas dominem o modelo
- Reduzir risco de NaN e melhorar desempenho preditivo
- Observação: Árvores e Random Forest tendem a ser robustos sem escalonamento

## Padronização e Normalização
- StandardScaler (média 0, desvio 1): distribuição ~normal, regressão linear/logística, sem outliers extremos
- MinMaxScaler ([0,1]): distribuição não-normal, preserva forma; não trata outliers
- RobustScaler: presença de outliers (percentis)

## Métodos de normalização
- Linear scaling ([0,1] ou [-1,1])
- Z-Score (equiv. StandardScaler)
- Log transform: dados muito assimétricos

## Regularização
- L1 (LASSO): penaliza |coef|; zera alguns coeficientes (feature selection)
- L2 (Ridge): penaliza coef²; encolhe coeficientes, bom com multicolinearidade
- Elastic-Net: combina L1+L2 (seleção + estabilidade)
- Escolha de λ (força de regularização): maior → mais viés, menos variância; menor → menos viés, mais variância

## Como rodar
1) Instale dependências na raiz:
```bash
pip install -r requirements.txt
```
2) Abra os notebooks em `notebooks/`

## Referências
- Notas em `plano_estudos.md`
