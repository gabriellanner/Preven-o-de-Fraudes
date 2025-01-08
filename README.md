# Detecção de Transações Fraudulentas em Criptomoedas

Este projeto demonstra na prática como construir um modelo XGBoost para classificar transações financeiras com criptomoedas a fim de detectar possíveis fraudes. Utilizando técnicas avançadas de programação orientada a objetos e pipelines de Machine Learning, o projeto visa criar um sistema robusto para prevenir atividades fraudulentas no mercado de criptomoedas.

**Fonte dos dados:**  
Os dados foram extraídos do [Kaggle - Ethereum Fraudulent Transactions Dataset](https://www.kaggle.com/datasets/vagifa/ethereum).


## Estrutura do Projeto  
O estudo foi segmentado nas seguintes etapas:  

### 1. Ajustes Iniciais
Nesta etapa, foram realizadas as importações necessárias e verificou-se que o *dataframe* apresentava espaçamentos nos nomes das colunas, o que poderia causar problemas futuros. Este problema foi resolvido para garantir consistência no processamento dos dados.  

### 2. Feature Engineering
Ao fazer uma analise nos dados percebi que havia muitas colunas com dados constantes (valores unicos), com isso realizei a remoção delas.

### 3. Criando o Pipeline
Para evitar ajustes no deploy, como por exemplo: padronização e preenchimento de dados faltantes, crei um pipeline que facilita esses ajustes. Foram 4 classes criadadas, sendo uma delas a classe 'mãe' que herda os BaseEstimator , TransformerMixin. Segue a descrição que inclui no Jupyter:
![image](https://github.com/user-attachments/assets/e7943267-c01f-4c3b-9864-c2428ae0954c)

### 4. Criando o Pipeline de Machine Learning 
Após esse pré-processamento, criei o pipeline com o modelo de classificação. O escolhido foi o XGBClassifier
![image](https://github.com/user-attachments/assets/de053bf5-5be1-41f4-b70c-c665633b33c9)

### 5. Treinamento
Com todos pipelinas feitos, realizei o treinamento que teve um retorno de 97% de AUC e o Recall de 95%

### 6. Deploy 
Ao aprovar o modelo, salvo ele em disco (utilizando o joblib) carrego novamente e aplico em novos dados.
Os dados devem ter o mesmo formato que utilizei para treinar o modelo 

