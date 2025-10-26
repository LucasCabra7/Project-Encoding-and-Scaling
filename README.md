<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=66CDAA&height=120&section=header"/>

# Encoding e Scaling

Projeto desenvolvido para a disciplina de **Ciências de Dados**, utilizando a linguagem **Python** e os princípios fundamentais de **Normalização/padronização, treino e teste e modelos preditivos.**.

---

## 🎯 Objetivos do Projeto

O objetivo deste estudo é explorar o impacto da codificação de variáveis categóricas e das técnicas de normalização/padronização no desempenho do algoritmo KNN (K-Nearest Neighbors).

Para isso, foi utilizado o conjunto de dados disponível em OpenML - Dataset ID 37
Inicialmente, foram aplicadas diferentes técnicas de codificação de variáveis categóricas nas colunas nominais do dataset, incluindo:
- One-Hot Encoding
- Dummy Coding
- Effect Coding

Em seguida, os dados foram transformados utilizando distintas técnicas de normalização e padronização, tais como:
- StandardScaler
- Min-Max Scaler
- MaxAbs Scaler
- Robust Scaler
- QuantileTransformer (distribuições uniforme e normal)

Após o pré-processamento, o conjunto de dados foi dividido em 70% para treino e 30% para teste por meio da função train_test_split.
O modelo KNN foi treinado e avaliado em cada cenário utilizando o valor padrão de K = 5 (n_neighbors = 5), sem ajuste de hiperparâmetros.
As métricas de avaliação consideradas foram:
- Para modelos de Classificação: Acurácia e F1-Score
- Para modelos de Regressão: MAE (Mean Absolute Error) e RMSE (Root Mean Squared Error)
  
Por fim, foram gerados insights analíticos para interpretar o comportamento do KNN frente às diferentes estratégias de codificação e normalização, destacando como cada técnica influencia o desempenho do modelo.

---

## 👨‍💻 Características do dataset escolhido
O dataset Diabetes é composto predominantemente por variáveis quantitativas, totalizando 442 amostras. Trata-se de um problema de regressão, cujo objetivo é prever uma variável alvo numérica que representa a progressão da doença um ano após o início do estudo.

---

##  📋 Explicação sobre o tipo de problema (classificação ou regressão):

Para a Modelos de classificação, utilizando o modelo KNN (K-Nearest Neighbors), mantivemos a variável alvo “Class” em seu formato categórico original, avaliando o desempenho por meio das métricas F1-Score e Acurácia. Já para os modelos de regressão, utilizamos o KNN Regre cuja entrada requer variáveis exclusivamente numéricas, utilizamos como variável alvo a versão codificada da Class pelo método Dummy, avaliando o desempenho por meio das métricas MAE (Erro Absoluto Médio) e RMSE (Raiz do Erro Quadrático Médio).


---

## 🧩 Descrever as colunas nominais e as codificações aplicadas

A única coluna nominal disponível no dataset diabetes foi a coluna class, que nos dados representava se o teste era positivo ou negativo. Utilizando One-Hot coding criamos duas tabelas e acrescentamos no DataFrame sendo uma tabela para testes positivos  e outra para testes negativos, de forma binária 1 ou 0. O problema é que aumentamos a cardinalidade do DataFrame, o que pode criar problemas, pois pode surgir uma falsa ordenação ou classificação entre categorias. Para o Dummy coding, foi utilizada a mesma analogia, mas para uma criação de N-1 tabelas binárias, fazendo com que não aumente tanto a cardinalidade. Já para o Effect coding, tem a mesma ideia do Dummy coding, mas o grupo de comparação assume o valor -1. No projeto em geral, testei todos os Encoding para cada Scaling, mas no final para não deixar o projeto grande o suficiente, optei por deixar o Encoding Dummy nos modelos de Regressão, por ter sido o melhor em todas as comparações de Encoding. 


### 🧠 Classificação - Acurácia:

| Encoding         | Scaling                                           | Acurácia - KNN                            |
|------------------|----------------------------------------------------------------|---------------------------------------|
| **One-Hot**       | **Standard**                   | 0.66   |
| **Dummy**  | **Min-Max**                          | 0.68   |
| **Effect**| **Roubst**              | 0.70|
| **Dummy**     | **MaxAbs Scaler**        | 0.68 |

---

### 🧠 Classificação - F1-SCORE:

| Encoding         | Scaling                                           | F1- Score - KNN                            |
|------------------|----------------------------------------------------------------|---------------------------------------|
| **One-Hot**       | **Standard**                   | 0.4689   |
| **Dummy**  | **Min-Max**                          | 0.496  |
| **Effect**| **Roubst**              | 0.53|
| **Dummy**     | **MaxAbs Scaler**        | 0.52 |
---

### 🧠 Regressão - MAE (Erro Absoluto Médio):

| Encoding         | Scaling                                           | F1- Score - KNN                            |
|------------------|----------------------------------------------------------------|---------------------------------------|
| **Dummy**       | **Standard**                   | 0.347   |
| **Dummy**  | **Min-Max**                          | 0.34  |
| **Dummy**| **Roubst**              | 0.33|
| **Dummy**     | **MaxAbs Scaler**        | 0.34 |
| **Dummy**     | **Quantile - Uniforme**        | 0.33 |
| **Dummy**     | **Quantile - Normal**        | 0.3575 |
---

### 🧠 Regressão - MAE (Erro Absoluto Médio):

| Encoding         | Scaling                                           | F1- Score - KNN                            |
|------------------|----------------------------------------------------------------|---------------------------------------|
| **Dummy**       | **Standard**                   | 0.46   |
| **Dummy**  | **Min-Max**                          | 0.456  |
| **Dummy**| **Roubst**              | 0.45|
| **Dummy**     | **MaxAbs Scaler**        | 0.45 |
| **Dummy**     | **Quantile - Uniforme**        | 0.43 |
| **Dummy**     | **Quantile - Normal**        | 0.458 |
---

## 📊 Comparativos de desempenho do KNN - Classificação
<img width="1016" height="590" alt="One-hot" src="https://github.com/user-attachments/assets/b0223bec-75c2-4a83-a3cb-e761a9c4fe38" />

---

## 📊 Comparativos de desempenho do KNN - Regressão
<img width="989" height="590" alt="regressão" src="https://github.com/user-attachments/assets/64658992-0035-4df1-9d06-66fd985e7f96" />

---

## Equipe do Projeto

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="https://avatars.githubusercontent.com/u/155683708?v=4" width="100px" alt="Lucas Cabral"/><br/>
        <b>Lucas Cabral</b>
      </td>
    </tr>
  </table>
</div>

---

<p align="center">
  &copy; 2025 Universidade Federal de Pernambuco - Centro de Informática. Todos os direitos reservados.
</p>

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=66CDAA&height=120&section=header"/>
