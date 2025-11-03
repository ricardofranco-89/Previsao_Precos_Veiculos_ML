# 🚗 Projeto de Previsão de Preços de Venda de Veículos

## 📘 Contexto do Projeto

Este projeto tem como objetivo **prever o preço de veículos usados** com base em suas principais características — como ano, quilometragem, tipo de combustível, potência, transmissão e outras variáveis.

Com base em um conjunto de dados real, foi desenvolvido e comparado o desempenho de diferentes modelos de **Machine Learning supervisionados**, buscando identificar aquele com **melhor capacidade preditiva e generalização**.

📊 **Fonte dos dados:** [Kaggle – Car Data](https://www.kaggle.com/datasets/athirags/car-data)

---

## 🧠 Objetivos

- Analisar o conjunto de dados e realizar a limpeza e padronização das variáveis.
- Explorar correlações e padrões relevantes.
- Treinar modelos de regressão e comparar seus desempenhos.
- Selecionar o melhor modelo para prever preços de veículos.
- Salvar o modelo final para uso futuro em produção.

---

## 🧰 Tecnologias Utilizadas

- **Linguagem:** Python
- **Bibliotecas Principais:**
  - pandas, numpy
  - matplotlib, seaborn
  - scikit-learn
  - xgboost
  - joblib

---

## ⚙️ Etapas do Projeto

### 1️⃣ Análise e Limpeza dos Dados
- Verificação e tratamento de valores nulos.
- Conversão de variáveis categóricas em numéricas.
- Padronização e normalização com **MinMaxScaler** e **StandardScaler**.

### 2️⃣ Análise Exploratória (EDA)
- **Boxplot:** identificação de outliers.
- **Heatmap:** correlação entre variáveis.
- **Histogramas:** distribuição dos dados.

### 3️⃣ Divisão dos Dados
Divisão em **treino (75%)** e **teste (25%)**:
```python
X_Treino, X_Teste, Y_Treino, Y_Teste = train_test_split(X, Y, test_size=0.25, random_state=42)
```

### 4️⃣ Treinamento dos Modelos

Modelos testados: `LinearRegression()`, `RandomForestRegressor()`, `GradientBoostingRegressor()`, `XGBRegressor()`.

#### 📊 Avaliação dos Modelos

O desempenho foi medido com base no **R² Score**, que indica o quão bem o modelo explica a variabilidade dos preços reais.

| Modelo | R² Score |
| :--- | :--- |
| Linear Regression | 0.74 |
| Random Forest | 0.86 |
| Gradient Boosting | 0.88 |
| **XGBoost** | **🏆 0.89 (89%)** |

#### 🧩 Modelo Final

O modelo **XGBRegressor** foi selecionado como o melhor para prever os preços dos veículos. Sua acurácia de 89% mostra excelente capacidade de generalização, tornando-o ideal para aplicações comerciais e estudos preditivos.

**Salvando o Modelo:**

```python
import joblib
joblib.dump(modelo_final, 'modelo_previsao_veiculos.pkl')
```

### 📈 Conclusão

O projeto demonstrou que é possível estimar com alta precisão o preço de veículos usados com base em variáveis como quilometragem, ano e tipo de combustível. O modelo XGBoost se destacou por sua performance superior e eficiência computacional.

🔹 **Acurácia final:** 89%
🔹 **Modelo escolhido:** XGBRegressor
🔹 **Próximos passos:** integração do modelo em uma aplicação web interativa.

### 📁 Estrutura do Projeto

```
📦 previsao_preco_veiculos
├── 📄 READ ME.md
├── 📘 PrevisaoPrecoVeiculos.ipynb
├── 📊 cardata.csv
├── 💾 modelo_treinado_veiculos.pk (Ignorado pelo Git)
└── 📂 imagens (gráficos e visualizações)
```