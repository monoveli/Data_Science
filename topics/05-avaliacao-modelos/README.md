# Avaliação de Modelos e Regularização

## Métricas (regressão)
- R², MAE, MAPE, RMSE
- Interprete sempre no contexto do negócio

## Overfitting vs. Underfitting
- Overfitting: ótimo no treino, fraco no teste; aprende ruído
- Indicadores: gap de métricas, ruído nos resíduos

## Regularização
- LASSO (L1): zera coeficientes (seleção de variáveis)
- Ridge (L2): encolhe coeficientes (estável com multicolinearidade)
- Elastic-Net: mistura L1+L2

## Como rodar
1) Instale dependências na raiz:
```bash
pip install -r requirements.txt
```
2) Abra os notebooks em `notebooks/`

## Referências
- Notas em `plano_estudos.md`
