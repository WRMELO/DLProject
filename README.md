# 🚀 Plano de Desenvolvimento — Pipeline Atualizado

## 📑 Pipeline de Desenvolvimento — Atualizado

### ✔️ Fluxo Estratégico do Projeto

```
Ingestão → Persistência (MongoDB) → Vetorização (Imagens) → Salvamento dos Vetores (Drive) → Modelagem IA → Validação e Ajustes → EDA Complementar
```

### ✔️ Justificativa da Arquitetura

Adotamos uma **arquitetura híbrida**, que separa os dados conforme suas características e volume, garantindo robustez, escalabilidade, simplicidade e baixo custo.

| Componente                       | Localização                       | Justificativa Principal                                          |
|-----------------------------------|------------------------------------|------------------------------------------------------------------|
| Dados tabulares (CSV)             | **MongoDB Atlas**                 | Leves, baixo volume, permite consultas remotas e centralizadas  |
| Metadados das imagens             | **MongoDB Atlas**                 | Permitem rastreabilidade, controle e integridade dos dados      |
| Vetores das imagens (X_img)       | **Google Drive (.npy)**            | Maior volume, armazenamento escalável e gratuito, rápido acesso |

---

## 🔥 Etapas do Pipeline

| Etapa                                    | Status   | Descrição                                                                                             |
| ----------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------- |
| 1️⃣ Configuração do Repositório           | ✅       | Estruturação do GitHub, README.md, diretórios e dependências.                                        |
| 2️⃣ Ingestão e Organização dos Dados      | ✅       | Dados tabulares (CSV) e imagens organizados.                                                         |
| 3️⃣ Persistência no MongoDB Atlas         | ✅       | Dados tabulares e metadados das imagens armazenados.                                                 |
| 4️⃣ Vetorização das Imagens               | ✅       | Imagens convertidas em vetores numéricos (shape 49152).                                              |
| 5️⃣ Salvamento dos Vetores no Drive       | ✅       | Vetores armazenados no Google Drive como arquivos `.npy`.                                            |
| 6️⃣ Construção dos Datasets para Modelagem| 🚧       | Combinação dos dados tabulares (X_csv), vetores de imagem (X_img) e labels (y).                      |
| 7️⃣ Modelagem IA                          | ⏳       | Desenvolvimento dos modelos CNN 1D, RNN (LSTM/GRU) e CNN 2D (imagens).                               |
| 8️⃣ Validação + Ajustes dos Modelos       | ⏳       | Avaliação das métricas, ajustes de hiperparâmetros e combate ao overfitting.                         |
| 9️⃣ Análise Exploratória Pós-Modelagem    | ⏳       | Análise guiada pelos erros dos modelos, refinamento de features, detecção de padrões e anomalias.    |
| 🔟 Avaliação Financeira (Backtest)        | ⏳       | Simulação financeira opcional, mas recomendada.                                                      |
| 🏁 Documentação Final + Entrega           | ⏳       | Refinamento do README.md, notebooks finais e apresentação dos resultados.                            |

---

## 🗂️ Organização dos Dados no Drive

```
/DLProject/data/processed/VALE3_SA/X_img.npy
/DLProject/data/processed/VALE3_SA/X_csv.npy
/DLProject/data/processed/VALE3_SA/y.npy

/DLProject/data/processed/PETR4_SA/X_img.npy
...
```

---

## ✅ Vantagens da Arquitetura Híbrida

- 🚀 Alta performance no carregamento dos dados.
- 🔗 MongoDB Atlas mantém os dados relacionais leves, fáceis de consultar e portáveis.
- 💾 Vetores de imagens ficam armazenados de forma eficiente e escalável no Google Drive.
- 🎯 Pipeline robusto, simples, replicável e com baixo custo operacional.

---
