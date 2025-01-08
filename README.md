# 🛡️ Detecção de Transações Fraudulentas em Criptomoedas

Este projeto apresenta a construção de um sistema para detecção de fraudes em transações financeiras com criptomoedas, utilizando **XGBoost** e técnicas avançadas de **programação orientada a objetos** e **pipelines de Machine Learning**. O objetivo é criar um modelo robusto que contribua para a prevenção de atividades fraudulentas no mercado de criptomoedas.

## Fonte dos Dados  
Os dados utilizados no projeto foram extraídos do [Kaggle - Ethereum Fraudulent Transactions Dataset](https://www.kaggle.com/datasets/vagifa/ethereum).

---

## Estrutura do Projeto

### 1. Pré-Processamento Inicial  
- Realização de importações necessárias.  
- Ajuste dos nomes das colunas no *dataframe* para remover espaços em branco, evitando possíveis problemas no processamento.

---

### 2. Engenharia de Atributos (*Feature Engineering*)  
- Identificação e remoção de colunas com valores constantes (valores únicos), reduzindo a dimensionalidade e otimizando o modelo.

---

### 3. Construção de Pipelines  
- Desenvolvimento de pipelines que simplificam o fluxo de pré-processamento e treinamento, evitando ajustes manuais no momento do deploy.  
- Foram implementadas **quatro classes**, incluindo uma classe base que herda de `BaseEstimator` e `TransformerMixin`. Essa abordagem modulariza e organiza o código.  

![Pipeline Exemplo](https://github.com/user-attachments/assets/e7943267-c01f-4c3b-9864-c2428ae0954c)

---

### 4. Pipeline de Machine Learning  
- Integração do pipeline de pré-processamento ao modelo de classificação **XGBClassifier**, garantindo escalabilidade e eficiência no treinamento.  

![Pipeline de ML](https://github.com/user-attachments/assets/de053bf5-5be1-41f4-b70c-c665633b33c9)

---

### 5. Treinamento  
- Treinamento realizado utilizando o pipeline completo.  
- Métricas de desempenho alcançadas:  
  - **AUC**: 97%  
  - **Recall**: 95%  

---

### 6. Deploy  
- O modelo final é salvo em disco com **Joblib** e pode ser carregado para aplicação em novos dados.  
- Os dados de entrada para o modelo devem seguir o mesmo formato utilizado no treinamento.

---

