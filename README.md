
# Detecção de Fraudes em Transações com Aprendizado de Máquina

Este projeto é focado na detecção de fraudes em transações financeiras, utilizando algoritmos de aprendizado de máquina não supervisionados, como o **Isolation Forest** e o **Local Outlier Factor (LOF)**. O objetivo principal é identificar anomalias ou fraudes em um conjunto de dados baseado nas características das transações.

## Índice

- [Instalação](#instalação)
- [Sobre os Dados](#sobre-os-dados)
- [Exploração de Dados](#exploração-de-dados)
- [Pré-processamento](#pré-processamento)
- [Modelagem](#modelagem)
- [Métricas de Avaliação](#métricas-de-avaliação)
- [Previsão de Novas Transações](#previsão-de-novas-transações)
- [Conclusão](#conclusão)

## Instalação

Para executar o projeto, você precisará de algumas bibliotecas. Para instalar as dependências necessárias, execute os comandos abaixo:

```bash
!pip install -U -q threadpoolctl
!pip install scikit-learn pandas numpy matplotlib seaborn
```

Certifique-se de que o arquivo `dataset.csv` esteja disponível na pasta `dados/` do seu diretório de trabalho.

## Sobre os Dados

O dataset utilizado neste projeto contém dados de transações financeiras, onde cada transação é classificada como:

- **0**: Transação Normal
- **1**: Transação Fraudulenta

As transações possuem características anonimizadas (colunas `V1` a `V28`), bem como os campos **Time** (tempo desde a primeira transação) e **Amount** (valor da transação).

## Exploração de Dados

Durante a análise exploratória, são examinadas as seguintes características:

- Distribuição de transações normais e fraudulentas.
- Valores estatísticos (mínimo, máximo, média) para transações normais e fraudulentas.
- Análises gráficas, como histograma e scatter plots, para observar a distribuição de valores e tempos.

## Pré-processamento

Foi criada uma amostra de 10% dos dados originais para facilitar a manipulação e treinamento dos modelos. A proporção de fraudes no conjunto de dados foi calculada para determinar a taxa de contaminação a ser utilizada pelos algoritmos de detecção de outliers.

## Modelagem

Dois algoritmos principais foram usados para detectar transações fraudulentas:

- **Isolation Forest**: Algoritmo que isola pontos de dados anômalos, assumindo que outliers são mais fáceis de isolar do que pontos normais.
- **Local Outlier Factor (LOF)**: Identifica outliers comparando a densidade local de um ponto de dados com a de seus vizinhos.

Cada modelo foi avaliado com base em suas previsões, e métricas de desempenho como **F1-Score**, **Precision**, **Recall** e **Accuracy** foram calculadas.

## Métricas de Avaliação

Os modelos foram comparados com base nas seguintes métricas:

- **F1-Score**: Métrica que pondera precision e recall.
- **Precision**: Proporção de transações identificadas como fraudulentas que realmente são fraudes.
- **Recall**: Proporção de fraudes que foram corretamente identificadas.
- **Accuracy**: Proporção de transações corretamente classificadas (normais e fraudulentas).

Os resultados foram plotados em um gráfico de barras para facilitar a comparação entre os dois modelos.

## Previsão de Novas Transações

Foi implementado um exemplo de previsão de fraude para uma nova transação. O modelo treinado **Isolation Forest** foi utilizado para prever se uma transação específica seria fraudulenta ou não.

## Conclusão

Os dois modelos mostraram boa acurácia geral, mas o **Isolation Forest** se destacou, apresentando melhores resultados em termos de precision e recall, sendo mais eficaz na detecção de transações fraudulentas. 

Este projeto pode ser expandido para incluir mais técnicas de ajuste de modelos, bem como a incorporação de novos algoritmos de detecção de anomalias.
