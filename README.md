# Predição de Renda para Segmentação de Clientes

Este repositório contém um pipeline de ciência de dados para prever se um indivíduo possui **renda acima da média**, apoiando decisões de **marketing, risco e crédito** com segmentações e scores de propensão.

---

## 🎯 Objetivo

Construir um **pipeline end-to-end** que classifica indivíduos em relação à renda (acima vs. abaixo de um limiar), permitindo:

- Priorizar leads e ofertas.
- Apoiar políticas de crédito e risco.
- Personalizar campanhas de marketing com base em propensão.

---

## 💼 Por que este projeto é relevante?

Empresas que dependem de **capacidade de gasto** — bancos, varejo, seguradoras, empresas SaaS, etc. — precisam decidir **para quem oferecer o quê, e quando**.

Um modelo de classificação de renda ajuda a:

- Reduzir **CAC** priorizando leads com maior probabilidade de retorno.
- Aumentar **taxas de conversão** ao direcionar ofertas para perfis mais aderentes.
- Apoiar **gestão de risco**, evitando superexposição a clientes com baixa capacidade de pagamento.

---

## 📦 O que você encontrará neste repositório

- 🧩 **Story de consultoria**: do problema ao impacto (hipóteses, trade-offs e recomendações executivas).
- 🛠️ **Pipeline de dados end-to-end**:  
  exploração → preparo de dados → modelagem → avaliação → explicabilidade → entrega.
- 📊 **Métricas de negócio**: uplift potencial em conversão/receita, priorização de fila, impacto em CAC.
- 📈 **Métricas técnicas**: F1, ROC AUC, Precision@K, curvas de lift/ganho.
- 🔍 **Explainability**: SHAP / feature importance para justificar decisões perante áreas de negócio e compliance.
- ✅ **Checklist de produção**: monitoramento de drift, fairness checks e plano de re-treino.

---

## 🧾 Dados

Base tabular com variáveis:

- **Demográficas**: idade, gênero, estado civil etc.
- **Educacionais**: escolaridade em anos, nível educacional.
- **Ocupacionais**: tipo de ocupação, setor, regime de trabalho.
- **Carga horária**: horas trabalhadas por semana.

**Target binário**: `<=50K` vs `>50K` (renda).

Inclui:

- Tratamento de **missing values**.
- Engenharia de variáveis categóricas (**one-hot encoding** e/ou **target encoding**).
- **Balanceamento** da base (stratified split, SMOTE quando necessário).

---

## 🔁 Pipeline (visão geral)

1. **Exploração (EDA)**: análise univariada, bivariada e multivariada.
2. **Preparo de dados**: limpeza, tratamento de outliers, encoding, escalonamento.
3. **Modelagem**: treino e tuning de modelos (baseline vs. modelos de árvore/boosting).
4. **Avaliação**: métricas técnicas + métricas de negócio (lift, impacto em conversão).
5. **Explainability**: SHAP, feature importance, análise de estabilidade.
6. **Entrega**: modelo empacotado + front simples para consumo (scorecard).

---

## 🧰 Stack

- **Linguagem**: Python  
- **Pacotes principais**:
  - `pandas`, `numpy`
  - `scikit-learn`
  - `XGBoost` / `LightGBM`
  - `SHAP`
- **MLOps / Tracking**:
  - `MLflow` para rastreamento de experimentos e versionamento de modelos
- **App / Demo**:
  - `Streamlit` para scorecard e explicabilidade por indivíduo

---

## 📂 Entregáveis

- 📓 **Notebook(s) reprodutíveis** com EDA, preparo de dados e modelagem.
- 📑 **Relatório executivo** com insights acionáveis e plano de implementação.
- 🖥️ **Aplicação Streamlit**:
  - input de indivíduo/perfil
  - score de propensão
  - explicabilidade local (SHAP).
- 📦 **Artefatos de modelo versionados** (MLflow) e **guia de deploy**.

---

## 🎯 Resultados esperados (metas de exemplo)

- **Desempenho técnico**:
  - AUC ≥ **0,88**
  - Precision@20% ≥ **0,65** em dados de teste.
- **Impacto de negócio (estimado)**:
  - **+15–25%** de lift em conversão no topo da fila (teste A/B simulado).
  - Redução de **10–20%** no CAC ao priorizar leads de alta propensão.

---

## 🚧 Status

> Projeto em evolução contínua. Melhorias futuras incluem:
> - Testes adicionais de fairness e estabilidade.
> - Integração com APIs de produção.
> - Monitoramento automatizado de drift e re-treino programado.
