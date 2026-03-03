 📊 TelecomX — Previsão de Evasão de Clientes (Churn Prediction)

## 📌 Visão Geral

Este projeto tem como objetivo analisar e prever a **evasão de clientes (churn)** em uma empresa de telecomunicações, utilizando técnicas de análise exploratória de dados (EDA) e modelos de Machine Learning.

A evasão de clientes impacta diretamente receita, crescimento e estabilidade do negócio. Por isso, identificar padrões e antecipar cancelamentos permite criar estratégias de retenção mais eficientes e baseadas em dados.

---

## 🎯 Objetivos do Projeto

* Analisar fatores que influenciam a evasão de clientes.
* Construir modelos preditivos para identificar clientes com maior probabilidade de churn.
* Comparar diferentes algoritmos de Machine Learning.
* Interpretar as variáveis mais relevantes.
* Propor estratégias de retenção baseadas nos resultados.

---

## 🗂️ Estrutura do Projeto

```
📁 TelecomX-Churn-Prediction
│
├── 📄 TelecomX_challenge.ipynb
├── 📄 dados_telecom_limpos.csv
├── 📄 README.md
```

---

## 🔍 Etapas Realizadas

### 1️⃣ Limpeza e Tratamento de Dados

* Conversão de colunas numéricas (`TotalCharges`) para formato adequado.
* Tratamento de valores ausentes.
* Remoção de colunas irrelevantes.
* Codificação de variáveis categóricas com **One-Hot Encoding**.
* Separação entre variáveis preditoras (X) e variável alvo (y).

---

### 2️⃣ Análise Exploratória (EDA)

Foram investigadas relações entre variáveis como:

* Tempo de contrato × Evasão
* Total gasto × Evasão
* Tipo de contrato × Evasão
* Serviços adicionais × Evasão

Principais insights observados:

* Clientes com **contrato mensal** apresentam maior risco de evasão.
* Clientes com **menor tempo de contrato (tenure)** tendem a cancelar mais.
* Faturas mensais mais altas estão associadas a maior churn.
* Ausência de serviços como suporte técnico aumenta a probabilidade de cancelamento.

---

### 3️⃣ Modelagem Preditiva

O conjunto de dados foi dividido em:

* 80% Treino
* 20% Teste
  (com `stratify` para preservar proporção das classes)

Foram testados diferentes modelos:

### 🔵 Regressão Logística

* Requer normalização das variáveis numéricas.
* Alta interpretabilidade.
* Permite análise direta dos coeficientes.

### 🟢 Random Forest

* Não exige normalização.
* Captura relações não-lineares.
* Boa performance geral.

### 🟣 XGBoost

* Modelo de boosting com alto poder preditivo.
* Fornece importância das variáveis.

---

## 📊 Avaliação dos Modelos

As métricas utilizadas foram:

* Acurácia
* Precisão
* Recall
* F1-score
* Matriz de Confusão
* Curva Precision-Recall

### Principais Resultados

* Random Forest apresentou melhor equilíbrio geral.
* Ajuste de threshold permitiu aumentar a **precisão da classe churn**, tornando o modelo mais conservador.
* Existe desequilíbrio entre classes (~73% não churn / ~27% churn), exigindo atenção na avaliação.

---

## 🧠 Variáveis Mais Relevantes

Com base na análise dos coeficientes (Regressão Logística) e importância das variáveis (Random Forest e XGBoost), os principais fatores associados à evasão foram:

* `tenure` (tempo de contrato)
* `Contract_Month-to-month`
* `MonthlyCharges`
* `TechSupport_No`
* `PaymentMethod_Electronic check`
* `InternetService_Fiber optic`

Esses fatores se repetiram entre diferentes modelos, indicando robustez nos padrões identificados.

---

## 💡 Estratégias de Retenção Propostas

Com base nos resultados:

### 🔹 Foco nos primeiros meses

Implementar onboarding estratégico e acompanhamento inicial.

### 🔹 Incentivo à migração para contratos longos

Oferecer benefícios para planos anuais ou bienais.

### 🔹 Reforço de valor percebido

Especialmente para clientes com mensalidades mais altas.

### 🔹 Oferta estratégica de suporte técnico

Clientes sem suporte apresentaram maior risco de evasão.

### 🔹 Incentivo a métodos de pagamento recorrentes

Reduzir fricção e instabilidade associadas a pagamentos manuais.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* XGBoost

---

## 📈 Possíveis Melhorias Futuras

* Aplicação de SMOTE para balanceamento de classes.
* Otimização de hiperparâmetros com GridSearch.
* Uso de SHAP para interpretabilidade avançada.
* Deploy do modelo em API.
* Criação de dashboard interativo para visualização de risco.

---

## 🚀 Conclusão

Este projeto demonstrou que é possível:

* Identificar padrões relevantes na evasão de clientes.
* Construir modelos preditivos eficientes.
* Traduzir resultados técnicos em estratégias de negócio acionáveis.
* Aplicar boas práticas de ciência de dados em um problema real.

A análise mostra que churn não é aleatório — ele segue padrões claros relacionados a tempo de contrato, tipo de plano, valor da fatura e nível de engajamento com serviços adicionais.
