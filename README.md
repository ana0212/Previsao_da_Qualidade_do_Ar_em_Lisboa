# Previsão da Qualidade do Ar em Lisboa (Séries Temporais)

## Visão Geral

Este projeto tem como objetivo desenvolver um sistema de **previsão dos níveis de poluição do ar (Material Particulado – PM)** a partir de **séries temporais ambientais** coletadas pela **Agência Europeia do Meio Ambiente (EEA)**, considerando dados da cidade de **Lisboa entre 2018 e 2023**.

O foco do trabalho é comparar abordagens clássicas de séries temporais com modelos de **Machine Learning supervisionado**, avaliando desempenho, generalização e robustez em diferentes estratégias de validação temporal.

---

## Objetivos do Projeto

- Analisar padrões temporais e sazonalidade nos níveis de poluição do ar  
- Comparar modelos estatísticos e de Machine Learning para previsão de séries temporais  
- Avaliar o impacto de **feature engineering temporal** no desempenho preditivo  
- Construir um pipeline reprodutível para previsão ambiental orientada a dados  

---

## Dados

- **Fonte:** European Environment Agency (EEA)  
- **Período:** 2018 – 2023  
- **Local:** Lisboa, Portugal  
- **Variável alvo:** Concentração de Material Particulado (PM)  

---

## Modelos Avaliados

Foram testados diferentes modelos de previsão:

- Regressão Linear  
- Random Forest Regressor  
- XGBoost Regressor  
- SARIMAX (baseline clássico de séries temporais)  

Além disso, foram aplicadas **transformações na série**, incluindo `log1p`, e técnicas de **feature engineering temporal**.

---

## Feature Engineering

O melhor desempenho foi obtido utilizando variáveis derivadas da própria série histórica, incluindo:

- Defasagens temporais (*lags*)  
- Estatísticas móveis:
  - Média
  - Mínimo
  - Máximo
  - Desvio padrão  
- Codificação temporal para capturar sazonalidade  

---

## Avaliação e Resultados

A avaliação foi conduzida utilizando **estratégias de validação cruzada específicas para séries temporais**, garantindo que o modelo respeitasse a ordem temporal dos dados e evitasse vazamento de informação.

### Melhor Modelo

- **Modelo:** Regressão Linear  
- **Transformação da série:** `log1p`  
- **Desempenho:**
  - **MAE:** 0.595  
  - **RMSE:** 0.826  

Esse modelo apresentou desempenho superior:
- Aos modelos treinados com a série original (sem transformação)
- Ao baseline com SARIMAX puro
- Aos modelos de Machine Learning mais complexos, evidenciando a importância do **feature engineering temporal** em problemas de séries temporais

---

## Principais Conclusões

- Variáveis derivadas da série histórica foram mais relevantes do que modelos mais complexos  
- A transformação `log1p` contribuiu para estabilizar a variância e melhorar o desempenho  
- Modelos simples podem superar abordagens mais sofisticadas quando bem ajustados ao problema  
- Estratégias adequadas de validação temporal são essenciais para garantir generalização  

---

Projeto_Previsao_Qualidade_do_ar_Lisboa.ipynb

Relatório do Projeto.pdf
SPO-PT03082_00005_100.parquet



## Estrutura do Repositório

```bash
├── Projeto_Previsao_Qualidade_do_ar_Lisboa.ipynb    # Análises exploratórias e modelagem
├── Relatório do Projeto.pdf                         # Relatório 
├── SPO-PT03082_00005_100.parquet                    # Dados da Série Temporal
└── README.md              # Documentação
