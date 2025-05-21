# 🚀 Projeto Integrado Deep Learning — Pipeline Atualizado

## 📑 Visão Geral do Projeto

Este projeto tem como objetivo o desenvolvimento de um pipeline de Deep Learning aplicado à análise de séries temporais e imagens no mercado financeiro. O projeto combina dados tabulares com imagens geradas a partir de séries históricas de ativos, visando construir modelos preditivos robustos.

---

## 🏗️ Arquitetura e Justificativa

### ✔️ Visão Estratégica da Arquitetura

Adotamos uma **arquitetura híbrida**, que maximiza desempenho local para pré-processamento e vetorizacão pesada, mantendo a escalabilidade e a conveniência da nuvem para treinamento e experimentos com GPU.

| Componente                        | Localização           | Justificativa                                                                 |
| --------------------------------- | --------------------- | ----------------------------------------------------------------------------- |
| **Dados brutos (imagens + CSV)**  | Local (SSD Ubuntu)    | Alta performance no acesso e pré-processamento local sem limitação de volume. |
| **Dados tabulares processados**   | MongoDB Local         | Banco perene, controle total dos dados, rápido, escalável e offline.          |
| **Vetores das imagens (X\_img)**  | MongoDB Local + Drive | Persistência local + backup/transferência via Drive para uso no Colab.        |
| **Arquivos para modelagem (X/y)** | Google Drive          | Acesso rápido no Colab (GPU) para treinamento e experimentação.               |

---

## ![Arquitetura](./images/arquitetura_pipeline.png)

---

## 🔥 Pipeline de Desenvolvimento

### 🔄 Fluxo Completo

```plaintext
Ingestão → Persistência no MongoDB Local → Vetorização das Imagens →
Exportação (Drive) → Modelagem (Colab com GPU) → Validação → EDA Pós-Modelagem
```

---

### 🚀 Etapas Detalhadas

| Etapa                                      | Status | Descrição                                                                                               |
| ------------------------------------------ | ------ | ------------------------------------------------------------------------------------------------------- |
| 1️⃣ **Configuração do Ambiente Local**     | ✅      | Criação do ambiente em Ubuntu + MongoDB Local + Git + Estrutura de diretórios.                          |
| 2️⃣ **Ingestão dos Dados Brutos**          | ✅      | Cópia dos dados (imagens e CSVs) para SSD local.                                                        |
| 3️⃣ **Persistência no MongoDB Local**      | ✅      | Dados tabulares (treino/teste) e metadados das imagens são armazenados no MongoDB Local.                |
| 4️⃣ **Vetorização das Imagens**            | ✅      | Conversão das imagens em vetores numéricos de alta dimensão (CNN Encoder).                              |
| 5️⃣ **Persistência dos Vetores**           | ✅      | Vetores são salvos no MongoDB Local e exportados como arquivos (.npy, .csv, .json) para o Google Drive. |
| 6️⃣ **Construção dos Datasets Finais**     | 🚧     | Combinação dos dados tabulares (X\_csv), vetores de imagem (X\_img) e labels (y).                       |
| 7️⃣ **Modelagem (Deep Learning)**          | ⏳      | Desenvolvimento dos modelos CNN 1D, RNN (LSTM/GRU) e CNN 2D (imagens).                                  |
| 8️⃣ **Validação e Ajustes dos Modelos**    | ⏳      | Avaliação de métricas, ajustes de hiperparâmetros, combate a overfitting e análise de erros.            |
| 9️⃣ **Análise Exploratória Pós-Modelagem** | ⏳      | EDA baseada nos resultados dos modelos para identificar padrões, erros e melhorias potenciais.          |
| 🔟 **Backtest Financeiro (Opcional)**      | ⏳      | Avaliação financeira simulada da estratégia gerada pelos modelos (retorno, drawdown, etc.).             |
| 🏎️ **Documentação Final e Entrega**       | ⏳      | Refinamento do README, notebooks finais, dashboards e apresentação.                                     |

---

## 📂 Organização dos Dados

### 📁 Estrutura Local

```plaintext
/workspace/DLProject/
├── data/
│   ├── raw/          # Dados originais (imagens + CSV)
│   ├── processed/    # Dados processados (vetores, datasets finais)
│   └── backups/      # Backups locais
├── notebooks/        # Jupyter Notebooks
├── scripts/          # Scripts Python (.py)
├── models/           # Modelos treinados
├── README.md         # Documentação
└── requirements.txt  # Dependências
```

### ☁️ Estrutura no Google Drive

```plaintext
/DLProject/data/processed/VALE3/
├── X_img.npy         # Vetores das imagens
├── X_csv.npy         # Dados tabulares vetorizados
├── y.npy             # Labels

/DLProject/data/processed/PETR4/
...

/DLProject/models/
├── cnn1d_model.h5
├── rnn_model.h5
├── cnn2d_model.h5

/DLProject/reports/
├── resultados.xlsx
├── graficos.png
```

---

## ✅ Vantagens da Arquitetura

* 🏎️ **Desempenho local máximo:** Processamento pesado (vetorização, pré-processamento) roda no SSD local, sem custos e sem limites.
* 🔗 **MongoDB Local:** Banco perene, controle total dos dados, rápido, escalável e offline.
* ☁️ **Drive como Hub de Modelagem:** Armazena datasets prontos para uso no Colab com GPU.
* 🔐 **Segurança e Controle:** Dados sensíveis não expostos na internet, mantidos no ambiente local.
* 💰 **Zero custos adicionais:** Sem dependência de MongoDB Atlas ou outros serviços pagos para dados de alto volume.
* 🔄 **Pipeline replicável e auditável:** Documentado, organizado e adequado tanto para uso acadêmico quanto profissional.

---

## 🚩 Próximos Passos Imediatos

1️⃣ **Finalizar a construção dos datasets finais (X\_img + X\_csv + y).**
2️⃣ **Subir para o Drive e configurar o notebook Colab para leitura.**
3️⃣ **Iniciar a modelagem com CNN 1D, RNN e CNN 2D no Colab (com GPU).**
4️⃣ **Realizar EDA Pós-Modelagem e ajuste fino dos modelos.**
5️⃣ **Documentar e gerar entrega final acadêmica e profissional.**

---

## 📜 Créditos

* Projeto desenvolvido no contexto do **MBA em Deep Learning — FIAP**.
* Autor: **Wilson Melo**.
* Orientação e apoio: Comunidade e Professores da FIAP.
