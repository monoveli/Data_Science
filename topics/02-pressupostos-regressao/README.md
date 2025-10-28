# Pressupostos Estatísticos da Regressão

## Objetivos
- Verificar linearidade, normalidade dos resíduos, homocedasticidade, independência
- Diagnosticar problemas e orientar correções

## Checklist prático
- Linearidade: resíduos vs. valores previstos sem padrões
- Homocedasticidade: variância constante dos resíduos (gráfico |resíduos| vs. previstos, teste de Levene)
- Normalidade dos resíduos: histograma, Q-Q plot, Shapiro-Wilk
- Independência dos erros: atenção a dados temporais/espaciais
- Multicolinearidade: matriz de correlação, VIF
- Outliers: boxplots, resíduos padronizados (|z| > 3)

## Como rodar
1) Instale dependências na raiz:
```bash
pip install -r requirements.txt
```
2) Abra os notebooks em `notebooks/`

## Referências
- Notas em `plano_estudos.md`
