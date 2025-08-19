# Telecom X – Parte 2: Prevendo Churn

## Contexto do Projeto

Este projeto faz parte do desafio **Telecom X – Parte 2**, no qual o objetivo principal é **prever a evasão de clientes (churn)** com base em variáveis contratuais, de consumo e outros.

A empresa busca reduzir o **churn** ao identificar, com antecedência, clientes que possuem maior probabilidade de cancelamento, permitindo a criação de estratégias de retenção mais eficazes.

---

## Estrutura do Repositório

```bash
├── data/
│   ├── TelecomX_Data_Limpo.csv
├── images/
├── Telecom X - Modelos.ipynb
├── requirements.txt
└── README.md
```

---

## Preparação dos Dados

* **Classificação de variáveis:**

  * Numéricas: tempo de contrato (meses), valor mensal, valor total etc.
  * Categóricas: gênero, tipo de contrato, forma de pagamento etc.

* **Tratamento aplicado:**

  * Encoding: `OneHotEncoder` e `LabelEncoder`
  * Normalização: `StandardScaler`
  * Balanceamento: `NearMiss` (undersampling)
  * Divisão dos dados: `train_test_split` com estratificação

---

## Modelagem

* **Modelos testados:**

  * `DummyClassifier` (baseline)
  * `LogisticRegression`
  * `DecisionTreeClassifier`

* **Técnicas de avaliação:**

  * Validação cruzada com `StratifiedKFold`
  * Ajuste de hiperparâmetros com `GridSearchCV`
  * Métricas: `accuracy`, `precision`, `recall`, `f1-score`, `roc_auc_score`

* **Visualizações utilizadas:**

  * `ConfusionMatrixDisplay`
  * `FeatureImportances` (Yellowbrick)

---

## Análise Exploratória (EDA)

Durante a análise exploratória, foram identificados padrões importantes relacionados ao churn como:

* Clientes com **maior tempo de contrato** apresentaram menor taxa de evasão.
* Clientes com mensalidades maiores tem maior taxa de evasão.

Outros gráficos gerados:

!['fig0'](https://raw.githubusercontent.com/alcyberan/Challenge-Telecom-X_Parte-2/refs/heads/main/images/fig0.png)
!['fi1'](https://raw.githubusercontent.com/alcyberan/Challenge-Telecom-X_Parte-2/refs/heads/main/images/fig1.png)

---

## Como Executar

1. Clone o repositório:

   ```bash
   git clone https://github.com/alcyberan/Challenge-Telecom-X_Parte-2.git
   cd Challenge-Telecom-X_Parte-2
   ```

2. Crie um ambiente virtual e instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

3. Abra o notebook principal:

   ```bash
   jupyter
   ```

4. Certifique-se de que os **dados tratados em CSV** estão na pasta `data/TelecomX_Data_Limpo.csv`.

---

## Conclusões Estratégicas

Estratégias podem incluir, mas não apenas:


1. **Incentivar contratos de um ano;**

  Os resultados dos modelos indicam uma menor probabilidade de Churn em clientes com maiores tempos de contratos, especialmente com o tipo de plano anual.

2. **Revisão no preço e serviços de assinaturas;**

  - Internet - Fibra óptica
  - Telefônia - Multiplas linhas
  - Tv-a-cabo

3. **Ações específicas nos primeiros meses de contrato;**

4. **Revisão dos meios de pagamento;**

  - Cheques-eletrônicos e por e-mail.

---

## Tecnologias Utilizadas

* **Manipulação e análise de dados**: `pandas`, `numpy`
* **Visualização**: `matplotlib`, `plotly`
* **Machine Learning**:

  * Pré-processamento: `OneHotEncoder`, `LabelEncoder`, `StandardScaler`, `make_column_transformer`
  * Modelagem: `LogisticRegression`, `DecisionTreeClassifier`, `DummyClassifier`
  * Avaliação: `ConfusionMatrixDisplay`, `classification_report`, `roc_auc_score`, `cross_validate`
  * Seleção e tuning: `StratifiedKFold`, `GridSearchCV`
* **Balanceamento de classes**: `imblearn` (`NearMiss`, `Pipeline`)
* **Interpretação de variáveis**: `yellowbrick` (`FeatureImportances`)

---

## Autor

Projeto desenvolvido por **Alan Silva**

---