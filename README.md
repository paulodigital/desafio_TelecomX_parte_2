# **📊 TelecomX: Predição de Evasão de Clientes (Churn) - Parte 2**
### 📌 Sobre o Projeto
Este projeto é a segunda etapa do desafio “Telecom X – Análise de Evasão de Clientes”, cujo objetivo foi compreender os fatores que levam ao cancelamento de clientes (Churn) em uma empresa de telecomunicações.

A partir da análise exploratória dos dados, buscamos gerar insights estratégicos que possam apoiar decisões de negócio e servir de base para a construção de modelos preditivos voltados à retenção de clientes.

A base de dados contém informações sobre clientes, como tempo de contrato, serviços contratados, gastos mensais, dados demográficos e status de churn. Nessa fase será usada a base já tratada da etapa anterior.

### 🎯 Objetivo da Análise

O objetivo central deste projeto é desenvolver um modelo de Machine Learning capaz de prever com precisão o churn (cancelamento de serviços) dos clientes da TelecomX. 
Através da análise de variáveis contratuais e financeiras, buscamos identificar os principais "gatilhos" da evasão para permitir que a empresa tome ações preventivas de retenção.

## 🧰 Tecnologias e Bibliotecas Utilizadas

O projeto foi desenvolvido em ambiente **Python 3.10+**, utilizando as seguintes bibliotecas para o pipeline de Ciência de Dados:

* ![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python) **Linguagem Base:** Utilizada para toda a lógica de programação e integração dos modelos.
* ![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?logo=pandas) **Manipulação de Dados:** Utilizada para carregar o CSV, limpar os dados, aplicar o One-Hot Encoding e estruturar os DataFrames.
* ![NumPy](https://img.shields.io/badge/NumPy-Numerical-orange?logo=numpy) **Computação Numérica:** Suporte matemático para operações em arrays, fundamental para o processamento dos modelos de Machine Learning.
* ![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?logo=matplotlib) **Visualização:** Base para a criação de gráficos estáticos, como a visualização da Árvore de Decisão.
* ![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-purple) **Análise Estatística:** Utilizada para gerar o Heatmap de correlação e os Boxplots de comparação entre as classes de Churn.
* ![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?logo=scikit-learn&logoColor=white) **Machine Learning:** A biblioteca central para o treinamento da Regressão Logística, KNN, Random Forest, SVM e para o pré-processamento com MinMaxScaler.
* ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter) **Desenvolvimento:** O ambiente interativo utilizado para documentar o passo a passo da análise.

## 📂 Estrutura do Projeto

**README.md:** Arquivo com a explicação do projeto, objetivos da análise e instruções básicas de uso

**TelecomX_parte2_prevendo_churn_NB_Final.ipynb:** Notebook principal com todo o fluxo de análise e modelagem.

**dados_tratados.csv:** Base de dados limpa (gerada na Parte 1 do projeto).

## 🛠️ Preparação dos Dados
Para garantir que os modelos de aprendizado de máquina funcionassem corretamente, o processo de preparação seguiu estas etapas:

**1. Classificação de Variáveis**
   * **Numéricas:** tempo_contrato, valor_mensal e total_cobrado.
   * **Categóricas:** tipo_contrato, forma_pagamento, servicos_internet, entre outras.

**2. Engenharia de Dados (Encoding e Normalização)**
   * **One-Hot Encoding:** Aplicado às variáveis categóricas para transformá-las em colunas binárias ($0$ ou $1$), facilitando o processamento matemático.
   * **MinMaxScaler:** As variáveis numéricas foram normalizadas para uma escala entre $0$ e $1$. Isso é vital para modelos como KNN e SVM, que são sensíveis à escala das distâncias entre os dados.

**3. Divisão dos Dados**
     
A base foi dividida em 70% para treino e 30% para teste, utilizando uma amostragem estratificada para manter a proporção da variável alvo (churn) em ambos os conjuntos, garantindo uma avaliação justa.

### 📈 Insights da Análise Exploratória (EDA)

Durante a EDA, identificamos padrões críticos que explicam a evasão:

* **Tipo de Contrato:** Clientes com contratos Mensais possuem uma taxa de evasão dramaticamente superior aos de contratos Anuais.

* **Tempo de Casa:** Existe uma relação inversamente proporcional entre o tempo_contrato e o churn. Clientes novos são os de maior risco.

* **Serviços Adicionais:** A ausência de serviços como suporte_tecnico e seguranca_online aumenta as chances de cancelamento.

### 🤖 Modelagem e Justificativas

Foram testados diversos modelos para encontrar o equilíbrio entre precisão e explicabilidade:

**1. Regressão Logística (80,41% de Acurácia):** Escolhida por ser o melhor modelo em termos de performance e pela facilidade de interpretar os coeficientes (pesos das variáveis).

**2. SVM (80,01% de Acurácia):** Excelente para encontrar a fronteira de decisão mais clara entre as classes.

**3. Random Forest:** Utilizado para rankear a importância das variáveis por redução de impureza.

**4. Árvore de Decisão:** Forneceu uma visualização clara das regras de "Se-Então" que levam ao churn.


### 🚀 Como Executar o Projeto
Google Colab

Faça o upload do notebook e do arquivo dados_tratados.csv, abra o notebook no Google Colab e execute as células em ordem.
