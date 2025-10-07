# Regressão Logística

## Conceitos-chave
- Problemas binários (0/1). Saída é probabilidade em [0,1]
- Modelo no espaço de log-odds (logit); função sigmoide mapeia para probabilidade
- Interpretação: coeficientes em log-odds; use Odds Ratio (OR) para comunicar

## Passos práticos
- Mapear target para {0,1}
- Ajustar modelo e interpretar coeficientes (OR>1 aumenta chances; OR<1 diminui)

## Avaliação
- Acurácia pode enganar em dados desbalanceados
- Use matriz de confusão, precisão, recall, ROC e AUC

## Como rodar
1) Instale dependências na raiz:
```bash
pip install -r requirements.txt
```
2) Abra os notebooks em `notebooks/`

## Referências
- Notas em `plano_estudos.md`
