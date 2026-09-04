# Projeto — Previsão de rendimento de safras

Este projeto analisa o arquivo `crop_yield.csv` e apresenta uma solução completa em Jupyter Notebook para exploração dos dados, clusterização, detecção de cenários discrepantes e modelagem preditiva de `Yield`.

## Arquivos

- `crop_yield.csv`: dataset original. Não deve ser alterado.
- `analise_crop_yield.ipynb`: notebook principal, com códigos executados, gráficos, resultados e conclusões.
- `README.md`: este guia.

## Como executar

1. Mantenha `crop_yield.csv` e `analise_crop_yield.ipynb` na mesma pasta.
2. Abra o notebook em Jupyter Notebook, JupyterLab ou ambiente compatível.
3. Execute as células na ordem apresentada.

## Bibliotecas utilizadas

- pandas
- numpy
- matplotlib
- scikit-learn

## Estrutura da análise

1. Carregamento e inspeção da base.
2. Estatísticas descritivas e visualizações.
3. Verificação da repetição dos cenários climáticos.
4. Clusterização por cultura com escolha do número de clusters por silhouette score.
5. Sinalização de possíveis outliers pela distância ao centroide, sem remover registros.
6. Separação treino/teste por cenário climático para reduzir vazamento de informação.
7. Comparação de cinco modelos:
   - Ridge
   - KNN
   - SVR
   - Random Forest
   - Gradient Boosting
8. Avaliação com MAE, RMSE, R² e MAPE.
9. Interpretação do melhor modelo por importância de permutação.
10. Conclusões, pontos fortes e limitações.

## Observação metodológica importante

Os mesmos 39 cenários climáticos aparecem para as quatro culturas. Por isso, o notebook não faz uma divisão aleatória simples por linhas. A separação é feita por grupos de condições climáticas, evitando que o mesmo cenário apareça simultaneamente no treino e no teste.

## Resultado geral

Na execução entregue, Gradient Boosting apresentou o menor MAE no conjunto de teste final, com desempenho superior ao baseline baseado apenas na média de rendimento por cultura. Os resultados devem ser interpretados considerando o tamanho reduzido da amostra e a ausência de variáveis como tempo, localização, solo e manejo.
