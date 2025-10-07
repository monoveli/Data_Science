# Árvores de Decisão, Random Forest e XGBoost

## Conceitos
- Árvores: regras de divisão (gini/entropy, MSE), fácil interpretabilidade
- Random Forest: ensemble de árvores, reduz variância, importância de features
- XGBoost (e afins): boosting gradiente, learning_rate, n_estimators, max_depth

## Avaliação
- Use AUC/ROC para classificação, R²/RMSE para regressão (conforme tarefa)

## Como rodar
1) Instale dependências na raiz:
```bash
pip install -r requirements.txt
```
2) Abra os notebooks em `notebooks/`

## Referências
- Notas em `plano_estudos.md`
