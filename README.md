# IEEE-CIS Fraud Detection - Detecção de Fraudes com Redes Neurais LSTM
### Aluno: Vinícius Oliveira Fernandes

## Introdução

Esta atividade consiste em analisar o dataset IEEE-CIS Fraud Detection, disponível em [https://www.kaggle.com/competitions/ieee-fraud-detection/data], com o objetivo de identificar padrões de fraude em transações financeiras utilizando redes neurais LSTM (Long Short-Term Memory). A seguir, será detalhado o processo de análise exploratória, preparação dos dados, treinamento e validação do modelo, além da análise dos resultados obtidos.

## Análise Exploratória de Dados

A primeira etapa da análise foi carregar o dataset e explorar suas características principais. Para isso, foram utilizados gráficos e estatísticas descritivas, incluindo:

- **Distribuições**: As distribuições nos mostram como os valores de uma variável estão distribuídos ao longo de seu intervalo. 
- **Correlação**: A correlação mede a força e a direção da relação entre duas variáveis.
- **Outliers**: Outliers são valores que estão significativamente fora do padrão da maioria dos dados. Eles podem ser indicativos de erro de medição ou comportamento anômalo.

## Preparação dos Dados

Antes de treinar a rede neural, os dados precisaram ser preparados adequadamente:

1. **Tratamento de valores ausentes**: os valores numéricos no dataset, foram preenchidos por 0. (utilizando o método fillna()).
2. **Normalização**: As variáveis foram normalizadas, utilizando o Robust Scaler, ele transforma os dados subtraindo a mediana e dividindo pela amplitude interquartil (IQR, Interquartile Range).
3. **Criação de sequências temporais**: Normalmente o modelo LSTM trabalha com dados sequenciais, mas neste caso não foi necessário transformar o dataset em sequências temporais. Nesta etapa normalmente é definido algumas janelas temporais e a criação de batches.


## Definição da Arquitetura do Modelo LSTM

A rede neural LSTM foi escolhida para detectar fraudes por sua capacidade de aprender padrões de longo prazo em dados sequenciais. A arquitetura definida incluiu:

- **Número de camadas LSTM**: 3 camadas
- **Número de neurônios**: Arquitetura piramidal de 100, 50 e 20 neurônios
- **Dropout**: Foi utilizado dropout para evitar overfitting, com taxa de `0.2`.
- **Função de ativação**: Sigmoid
- **Função de perda**: A função de perda foi definida como `binary_crossentropy` para lidar com a classificação binária (fraude ou não fraude).
- **Otimizador**: O otimizador utilizado foi o Adam.


## Treinamento e Validação do Modelo

O modelo foi treinado utilizando o conjunto de dados de treinamento e validado com um conjunto de teste separado. Foram aplicadas as seguintes métricas de avaliação para verificar a performance do modelo:

- **Acurácia**
- **Precisão**
- **Recall**
- **F1-score**
- **AUC-ROC**

Durante o treinamento, foi observada a **curva de aprendizado** para identificar sinais de overfitting ou underfitting. A abordagem utilizada para melhorar o desempenho do modelo incluiu técnicas como ajuste de hiperparâmetros e regularização.

## Conclusão

Este projeto abordou o uso de redes LSTM para a detecção de fraudes em transações financeiras. A documentação cobre desde a análise exploratória até a avaliação final do modelo, destacando as etapas de preparação dos dados, definição da arquitetura da LSTM, treinamento e validação do modelo. 
