# 🎯 Otimização de Hiperparâmetros em Modelos de Classificação de Inadimplência

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/VictorGMSS/Otimizando-modelos-de-machine-learning/blob/main/Otimizando_modelos.ipynb)

Projeto prático desenvolvido durante o curso **"Classificação: Otimizando modelos de machine learning"**. O objetivo deste repositório é melhorar o desempenho de modelos que preveem a **inadimplência de clientes**, comparando três técnicas de otimização de hiperparâmetros: **Busca em Grade (Grid Search)**, **Busca Aleatória (Random Search)** e **Otimização Bayesiana**, todas avaliadas com **validação cruzada aninhada** e a métrica **recall**.

---

## 🎯 Objetivos do Projeto

* **Modelos de Referência:** Treinar modelos base (Árvore de Decisão e Regressão Logística) para comparar o ganho obtido com a otimização.
* **Busca em Grade:** Testar combinações de hiperparâmetros de forma exaustiva com `GridSearchCV`, aplicada a três algoritmos (Árvore de Decisão, Regressão Logística e KNN).
* **Busca Aleatória:** Explorar o espaço de hiperparâmetros por amostragem com `RandomizedSearchCV`, reduzindo o custo computacional.
* **Otimização Bayesiana:** Buscar os melhores hiperparâmetros de forma guiada com `BayesSearchCV` (**scikit-optimize**).
* **Validação Cruzada Aninhada:** Estimar o desempenho dos modelos otimizados sem viés, separando a escolha dos hiperparâmetros (CV interno) da avaliação (CV externo).
* **Melhor Modelo:** Comparar as técnicas e os algoritmos para encontrar o melhor modelo para os dados trabalhados.

---

## 🗂️ Estrutura do Repositório

* `Otimizando_modelos.ipynb`: Notebook principal com todo o pipeline de preparação, modelagem, otimização e avaliação.
* `dados_inadimplencia.csv`: Base de dados de clientes, com a variável alvo `inadimplente` indicando se o cliente é inadimplente.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

* **Python 3**
* **Pandas & NumPy:** Manipulação dos dados e definição dos espaços de busca (`np.linspace`).
* **Matplotlib:** Gráficos de dispersão relacionando hiperparâmetros ao desempenho (`mean_test_score`).
* **Scikit-Learn:** Modelos (`DecisionTreeClassifier`, `LogisticRegression`, `KNeighborsClassifier`), `Pipeline` com `StandardScaler`, `train_test_split`, `StratifiedKFold`, `GridSearchCV`, `RandomizedSearchCV`, `cross_val_score` e `recall_score`.
* **Scikit-Optimize (`BayesSearchCV`):** Otimização Bayesiana de hiperparâmetros, com espaços definidos por `Real`, `Integer` e `Categorical`.

---

## 🚀 Etapas Desenvolvidas no Notebook

1. **Preparação dos Dados:** Carregamento da base (`[PREENCHER]` registros), análise da proporção de clientes inadimplentes e separação em treino e teste (`67%/33%`, `random_state=42`).
2. **Modelos de Referência:** Treino de uma Árvore de Decisão (`max_depth=3`) e de uma Regressão Logística com padronização, avaliados pelo **recall** no conjunto de teste (DT: `[PREENCHER]` | LR: `[PREENCHER]`).
3. **Busca em Grade:** Otimização de Árvore de Decisão, Regressão Logística e KNN com `StratifiedKFold`, análise dos `cv_results_` e gráficos de hiperparâmetros contra o desempenho.
4. **Validação Cruzada Aninhada:** Avaliação da Árvore de Decisão e da Regressão Logística com CV interno de 5 folds e CV externo de 3 folds.
5. **Busca Aleatória:** Otimização com `RandomizedSearchCV` (100 iterações para a Árvore de Decisão e 50 para a Regressão Logística), também com validação aninhada.
6. **Otimização Bayesiana:** Otimização com `BayesSearchCV` (50 iterações) para os dois modelos, também com validação aninhada.
7. **Previsão:** Uso do melhor estimador da Regressão Logística otimizada para gerar previsões no conjunto de teste.

---

## 💻 Como Executar

1. **Via Google Colab (Recomendado):** Clique no botão **"Open in Colab"** no topo deste README para abrir e executar o notebook diretamente no navegador sem precisar configurar ambiente local.
2. **Localmente:**
```bash
git clone https://github.com/VictorGMSS/Otimizando-modelos-de-machine-learning.git
cd Otimizando-modelos-de-machine-learning
pip install pandas numpy matplotlib scikit-learn scikit-optimize jupyter
jupyter notebook Otimizando_modelos.ipynb
```

---

## 👨‍💻 Informações pessoais

Victor Gabriel Martins e Souza

* 💼 LinkedIn: [https://www.linkedin.com/in/victorgms](https://www.linkedin.com/in/victorgms)
* 🌐 Portfólio: [https://verxstech.vercel.app](https://verxstech.vercel.app)
