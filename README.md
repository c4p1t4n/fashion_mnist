### Pré-processamento dos Dados
Para garantir que os modelos de aprendizado de máquina fossem treinados de forma eficiente e com melhor performance, as seguintes etapas de pré-processamento foram realizadas:

1. **Normalização dos Dados:**
   - **Ferramenta Utilizada:** Standard Scaler
   - **Motivação:** Tanto o KNN quanto o SVM são sensíveis à escala dos dados:
     - **KNN:** Calcula distâncias entre pontos, o que pode ser distorcido se as características tiverem escalas diferentes.
     - **SVM:** Traça hiperplanos entre classes, e uma escala inadequada pode influenciar a posição e a orientação desses hiperplanos.
   - **Processo:** Os dados foram padronizados para ter média zero e desvio padrão igual a um, garantindo que todas as características contribuíssem de maneira equilibrada para os modelos.

2. **Redução de Dimensionalidade:**
   - **Ferramenta Utilizada:** PCA
   - **Motivação:** Melhorar o tempo de treinamento e reduzir a complexidade dos dados.
   - **Processo:** O PCA foi aplicado para transformar os dados em um conjunto de componentes principais, mantendo a maior parte da variância dos dados originais, mas com uma dimensionalidade reduzida.

### Comparação dos Modelos

#### SVM Não Linear
**Pontos Fortes:**
- **Desempenho Superior:** Apresentou métricas de avaliação ligeiramente melhores em relação ao KNN (accuracy, precision, recall e F1 de 0.89 vs. 0.87 para o KNN).

**Pontos Fracos:**
- **Custo Computacional Elevado:** O treinamento foi significativamente mais caro, levando 1 hora e 51 minutos em comparação aos 25 minutos do KNN.

#### KNN (K-Nearest Neighbors)
**Pontos Fortes:**
- **Simplicidade e Rapidez no Treinamento:** Muito mais rápido no treinamento, completando em 25 minutos comparado aos 1 hora e 51 minutos da SVM.

**Pontos Fracos:**
- **Desempenho Ligeiramente Inferior:** Teve métricas de avaliação um pouco inferiores (0.87 contra 0.89 da SVM).

### Explicação das Métricas de Avaliação e Interpretação dos Resultados

#### Métricas Utilizadas:
1. **Accuracy:** Proporção de previsões corretas entre o total de previsões feitas.
2. **Precision:** Proporção de verdadeiros positivos em relação ao total de positivos previstos.
3. **Recall:** Proporção de verdadeiros positivos em relação ao total de positivos reais.
4. **F1 Score:** Média harmônica da precisão e recall, que considera ambos de forma equilibrada.

#### Interpretação dos Resultados:
- **Accuracy de 0.87 e 0.89:** Indica que ambos os modelos têm uma alta proporção de previsões corretas, com a SVM apresentando uma ligeira vantagem.
- **Precision, Recall e F1 iguais às respectivas accuracies:** Sugere que os modelos são balanceados e eficazes tanto na identificação correta de positivos quanto na minimização de falsos positivos e falsos negativos.

### Tabela Comparativa

| Nome do Modelo | Accuracy (%) | Precision | Recall | F1   | Tempo de Execução (ms) |
|----------------|--------------|-----------|--------|------|------------------------|
| KNN            | 0.87         | 0.87      | 0.87   | 0.87 | 1553 (25 minutos)      |
| SVM            | 0.89         | 0.89      | 0.89   | 0.89 | 6667 (1h 51 minutos)   |

### Escolha do Modelo:
- Devido a ambos os modelos terem desempenhado de forma similiar o modelo final que escolheria seria o KNN dado que o custo computacional de treinamento do mesmo foi menor comparado com o SVM