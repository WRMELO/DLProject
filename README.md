# DLProject — Previsão de Tendência de Ações com Deep Learning

Este repositório contém o desenvolvimento do Projeto Integrado de Deep Learning do MBA FIAP. O objetivo é construir um pipeline completo de ingestão, processamento e modelagem preditiva de tendência de ações com uso de IA.

---

## 🚀 Arquitetura Geral do Projeto

* Dados organizados em MongoDB Atlas
* Pipeline de ingestão e pré-processamento
* Modelagem IA com CNN 1D, RNN (LSTM/GRU) e CNN 2D (imagens)
* Simulações financeiras (backtest)
* Pipeline escalável e reproduzível

---

## 🏗️ Estrutura de Diretórios

```
/                    # Raiz do projeto
├── data/
│   ├── raw/         # Dados originais (CSV, imagens)
│   └── processed/   # Dados pré-processados
├── notebooks/       # Notebooks Colab para EDA e modelagem
├── src/             # Scripts auxiliares
├── models/          # Modelos treinados
├── requirements.txt # Dependências Python
├── README.md        # Documentação
└── .gitignore       # Arquivos ignorados pelo Git
```

---

## 🔥 Fluxo de Desenvolvimento Atualizado

```
Ingestão → Persistência (MongoDB) → Pré-processamento → Modelagem IA → Validação e Ajustes → EDA Complementar
```

### ✔️ Justificativa:

* Priorizamos construir o pipeline e testar modelos antes da EDA detalhada.
* A EDA torna-se mais assertiva quando feita após a primeira rodada de modelagem, guiada pelos resultados e erros.

---

## 📑 Pipeline de Desenvolvimento

### 1. Configuração Inicial

* Setup do repositório GitHub e ambiente Colab.

### 2. Ingestão e Organização de Dados

* Dados de múltiplos ativos em CSV e imagens.
* Estruturação em MongoDB Atlas.

### 3. Persistência no MongoDB

* Dados tabulares e imagens com metadados organizados por ativo.

### 4. Pré-processamento para IA

* Criação dos datasets `X_csv`, `X_img`, `y`.

### 5. Modelagem IA

* CNN 1D, RNN e CNN 2D.

### 6. Análise Exploratória de Dados (EDA) — pós-modelagem

* Balanceamento, erros, distribuição, refinamento.

### 7. Avaliação e Backtest

* Métricas e simulações financeiras.

### 8. Documentação e Entrega

* README, notebooks finais, apresentações.

---

## 🌐 Banco de Dados

* **MongoDB Atlas**
* Banco: `DLProject`
* Coleções:

  * `VALE3_SA`, `PETR4_SA`, `CSNA3_SA`, `BBAS3_SA`
  * * coleções de imagens: `VALE3_SA_imagens`, etc.

---

## 👨‍💻 Tecnologias

* Python + Colab
* MongoDB Atlas
* TensorFlow / Keras
* Pandas, Matplotlib, Seaborn, Plotly
* VSCode, Git, GitHub

---

## 📜 Justificativa da Flexibilização do Pipeline

```
Ingestão → Persistência (MongoDB) → Pré-processamento → Modelagem IA → Validação e Ajustes → EDA Complementar
```

* Esta abordagem permite validar rapidamente o pipeline de IA e otimizar o tempo.
* A EDA feita após o modelo fornece insights mais relevantes e é guiada por erros e acertos do modelo.

---

## 🚀 Autor

* Wilson Melo — `WRMELO`
