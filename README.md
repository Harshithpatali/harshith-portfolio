# Harshith Devaraja — Data Science & Applied ML Portfolio

**Live portfolio:** https://harshithpatali.github.io/harshith-portfolio/  
**Résumé:** https://harshithpatali.github.io/harshith-portfolio/resume.html  
**Source:** https://github.com/Harshithpatali/harshith-portfolio

A research- and engineering-led portfolio across customer intelligence, SQL analytics, causal inference, retail optimisation, signal processing and applied AI. It presents three detailed case studies and fifteen additional projects. The site deliberately separates measured results from scenario assumptions and research ideas.

## Featured case studies

### 1. Customer Intelligence & Graph Anomaly Lab

**Repository:** [Graph-anomaly-supervised-neural-prediction](https://github.com/Harshithpatali/Graph-anomaly-supervised-neural-prediction) · **[Live dashboard](https://graph-anomaly-supervised-neural-prediction-v1.streamlit.app/)**

An unsupervised customer investigation workspace combining behavioural profiles, K-means segmentation, a cohort-relative behavioural index, Isolation Forest and Local Outlier Factor anomaly ranking, and a user–device–IP graph.

- **Scope:** at most 50,000 input transactions for graph construction; at most 100,000 investigation edges; up to 50 recent transactions in each customer purchase timeline.
- **Methods:** anomaly ranking blends Isolation Forest percentile (60%) and LOF percentile (40%). The separate behavioural-risk score is a heuristic and is excluded from the anomaly-model inputs to avoid circular scoring.
- **Product surface:** eight workspaces cover executive overview, Customer 360, customer exploration, segmentation, graph intelligence, anomaly review, executive export and methodology.
- **Interpretation:** the historical fraud label is dropped from the current unsupervised workflow. Scores are cohort-relative review signals—not calibrated fraud probabilities or proof of wrongdoing. They should not be used alone to block or penalise customers.

### 2. Brazilian E-commerce Intelligence

**Repository:** [brazilian-ecommerce-data-science](https://github.com/Harshithpatali/brazilian-ecommerce-data-science) · **[Live dashboard](https://olist-ecommerce-ds.streamlit.app/)**

A SQL-first customer analytics product built on the public Olist marketplace dataset (~100K orders), with careful source-table grain, customer RFM, cohorts, survival analysis, statistics, point-in-time features and a seven-page dashboard.

- **Data/analytics scope:** 16 ordered SQL build stages, 20+ analytical tables/views, 9 source entities, seven dashboard pages and 57 point-in-time churn/second-purchase features.
- **Feature/target design:** 180-day historical lookback to predict a second delivered purchase in the next 90 days. The evaluation pipeline uses date-grouped temporal folds, a 90-day purge, a separate validation threshold and an untouched chronological holdout.
- **Holdout result:** 143,208 customer-month snapshots; PR-AUC **0.01048** versus **0.01665** for the lifetime-frequency baseline. The model also failed to beat baseline precision at 5%, 10% and 20% contact capacity.
- **Decision:** the model artifact is correctly marked `research_only`. The stronger demonstration is the governed SQL layer, RFM/cohort/survival analysis, timestamp integrity and business reporting—not a claim of successful churn prediction.
- **Data discipline:** item and payment records are aggregated separately before order-grain joins to avoid many-to-many row multiplication. Customer-level analysis uses the stable `customer_unique_id`.

### 3. Causal Experimentation Intelligence

**Repository:** [causal_experimentation_platform](https://github.com/Harshithpatali/causal_experimentation_platform) · **[Live dashboard](https://causal-ai-customer-growth-intelligence.streamlit.app/)**

An end-to-end Criteo experimentation workflow that checks assignment integrity and covariate balance before measuring lift, then estimates ATE/ATT, fits S/T/X learners and translates uplift rankings into capacity-based campaign scenarios.

- **Scope:** 80,000-row sample; 40,000 control and 40,000 treatment records; 12 pre-treatment features.
- **Experiment checks:** no sample-ratio mismatch (χ² p=1.00); maximum absolute standardised mean difference 0.0134 across the 12 features.
- **Observed outcome:** conversion was 0.3475% in control and 0.4775% in treatment: +0.13 percentage points, +37.4% relative, p=0.0041, 95% CI +0.041 to +0.219 pp.
- **Business scenario:** 10% targeting projected 18.5% ROI when scaled to 100,000 targeted users under configured assumptions ($0.05 contact cost, $25 per conversion, 40% margin).
- **Interpretation:** the shipped sample is re-balanced 50/50 although the original Criteo design is approximately 85% treated. The ROI output is assumption-sensitive scenario analysis, not realised campaign profit.

## Additional projects

### Data science, forecasting and engineering

| Project | Scope and methods | Evaluation, impact and limits |
|---|---|---|
| [Retail Demand & Inventory Optimisation](https://github.com/Harshithpatali/retail-demand-inventory-optimization) · [Dashboard](https://retail-demand-inventory-optimization-v1.streamlit.app/) · [API](https://retail-demand-inventory-optimization.onrender.com/) | M5 demand panel: 30,490 candidate item–store series, a deterministic 200-series deployment subset and 388,200 prepared feature rows. XGBoost/LightGBM, naïve and seasonal baselines, out-of-sample residual uncertainty, periodic-review (R,S) inventory simulation. | XGBoost validation WAPE 0.2808 vs 0.6873 naïve (59.2% lower). Held-out policy simulation: total modeled cost −16.21%, stockout units −30.65%, service level +2.46 pp. Costs use documented demonstration assumptions, not retailer-calibrated economics. |
| [Enterprise ML Platform](https://github.com/Harshithpatali/enterprise-ml-platform) · [API docs](https://enterprise-ml-platform.onrender.com/docs) | Olist HDFS + PySpark Bronze/Silver/Gold layers, 95,194 customer snapshots, 93,358 customers, 19 temporal features, 180-day lookback / 90-day target, SHAP, FastAPI and five-page Streamlit dashboard. | 16 automated tests. The target is heavily imbalanced (~96.1% churn observations); the repository notes that an always-churn rule already yields ~0.981 F1. Presented as data engineering, reproducibility and serving—not a claim of production-ready churn prediction. |
| [AI-Powered E-commerce Intelligence](https://github.com/Harshithpatali/ecommerce-intelligence) · [Dashboard](https://ecommerce-intell.streamlit.app/) · [API docs](https://ecommerce-intelligence-xod0.onrender.com/docs) | Olist customer/product system with CLV prediction, segmentation, SHAP, retention prioritisation, recommendations and LLM-generated narratives. Evaluation report covers 96,096 customers, 6,012 high-value inactive customers and 3,640 recommendation rows. | CLV report: MAE 0.922, RMSE 17.30, R² 0.073; mean predicted future revenue 0.068 vs actual 0.934. Current CLV fit is weak and underpredicts; segmentation and recommendations remain prototype decision-support outputs, not proven revenue lift. |
| [Causal Uplift Marketing Optimisation](https://github.com/Harshithpatali/causal-uplift-marketing-optimization) | 64,000-customer Hillstrom experiment; three email arms; 48K train / 16K test; ATE, LightGBM T-learners, class transformation, uplift-at-k and held-out policy evaluation. | Best AUUC 0.002054 and Qini 0.004129. Best uplift@10/20/30: 0.63% / 0.41% / 0.55%. Held-out targeting at 50% depth estimated ~41.9 incremental conversions. These are historical-sample estimates, not guaranteed future conversions or revenue. |
| [Sensex Quant Lab](https://github.com/Harshithpatali/Sensex_Quant_Lab) | Next-session open/close return forecasting, 7,229 rows, 108 features, 6,145 train / 1,084 test, three TimeSeriesSplit folds with a one-row gap, five candidate regressors and scheduled weekday refresh. | Open-return Ridge: MAE 0.00342, directional accuracy 59.96%, R² −0.017. Close-return mean baseline ranked first (MAE 0.00599; directional accuracy 52.86%). Latest run does not establish a robust forecasting edge; research tool, not a trading signal. |
| [Bayesian & Sequential Experimentation](https://github.com/Harshithpatali/bayesian-sequential-experimentation) | Synthetic Bernoulli/Normal and multi-arm generators; power/sample sizing; frequentist z-tests; Beta–Binomial Bayesian A/B; sequential tests; Bonferroni, Holm and Benjamini–Hochberg FDR. | Supports study of Type I error, power, credible intervals, expected loss and always-valid p-values under optional stopping. No consolidated Monte Carlo calibration result is published; this is a teaching/research lab. |

### Signal processing and research

| Project | Scope and methods | Evaluation, impact and limits |
|---|---|---|
| [DeepFake Noise & Wavelet Forensics](https://github.com/Harshithpatali/deepfake-noise-wavelet-ml) · [Live app](https://deepfake-noise-wavelet-ml-hd.streamlit.app/) · [API](https://deepfake-noise-wavelet-ml.onrender.com/) | DeepFakeFusion-304K: 304,154 labelled images, with 105 handcrafted spatial/noise/wavelet descriptors; db2 level-3 DWT, L1 feature selection and regularised logistic regression. | Validation ROC-AUC 0.9249, but locked test ROC-AUC 0.6623 / PR-AUC 0.6675 / accuracy 0.623. Separate 100-image blind holdout ROC-AUC 0.4872 / accuracy 0.56. The validation-to-holdout gap highlights generalisation risk; not forensic-grade detection. |
| [Wavelet Voice Lab](https://github.com/Harshithpatali/Wavelet-Domain-Robust-Voice-Communication-Lab) · [Live app](https://wavelet-domain-robust-voice-communication-lab.streamlit.app/) | DWT, coefficient thresholding and keyed permutation; AWGN and burst-loss channels; packet transport, CRC32, one-packet-per-four XOR recovery and up to 180 parameter-sweep combinations. | Dashboard reports recovered SNR, MSE, correlation, retained coefficients and packet recovery. Unit tests cover codec round-trip and permutation reversibility. Keyed scrambling is reversible obfuscation, not cryptography; live-call/device testing remains a limitation. |

### Applied AI and evaluation systems

| Project | Scope and methods | Evaluation, impact and limits |
|---|---|---|
| [LLM Prompt Evaluation & Benchmarking](https://github.com/Harshithpatali/llm-prompt-benchmark) · [Live demo](https://llm-prompt-benchmark-a.streamlit.app/) | Amazon Berkeley Objects product copy; 10-field JSON extraction; zero-shot, few-shot, chain-of-thought and structured JSON prompting; Groq/OpenRouter adapters; MLflow runs. | One documented Groq/Llama-3.1-8B-Instant run: few-shot exact match 0.417 vs zero-shot 0.097. This is a single run, not a generalised cross-model result. Role-based and self-consistency strategies are planned, not shipped. |
| [LLM Reliability & Evaluation Platform](https://github.com/Harshithpatali/llm-evaluation-platform) · [Dashboard](https://llm-evaluation-platform-q.streamlit.app/) · [API](https://llm-evaluation-platform-1.onrender.com/docs) | FastAPI inference, Celery background evaluation, Redis telemetry, Streamlit dashboard, Prometheus support; correctness, clarity, helpfulness, safety and professionalism scoring. | Uses KS tests and Wasserstein distance to compare historical and recent evaluation-score distributions. No fixed benchmark or validated drift-detection score is published; thresholds and false-alarm rates need controlled evaluation. |
| [LLM-as-a-Judge for E-commerce](https://github.com/Harshithpatali/llm-judge-ecommerce) · [Dashboard](https://llm-judge-ecommerce-c.streamlit.app/) · [API](https://llm-judge-ecommerce.onrender.com/docs) | Single and batch evaluation of product descriptions, titles and attributes on five rubric dimensions: faithfulness, completeness, clarity, persuasiveness/SEO and format compliance. | Produces criterion scores, reasoning, score distributions and product-level analysis. No fixed labelled benchmark or judge-agreement score is published; human calibration is needed for release-gate use. |
| [TCS Financial Intelligence Agent](https://github.com/Harshithpatali/financial-intelligence-agent) · [Live app](https://financial-intelligence-agent-g.streamlit.app/) | Six listed annual-report knowledge files from FY2020–21 through FY2025–26; PDF-to-Markdown parsing, BGE embeddings, ChromaDB retrieval, Groq generation, FastAPI and Streamlit. | Answers are designed to include retrieved source context and citations. Retrieval precision, citation accuracy and faithfulness have not been reported as a fixed benchmark. |
| [Math RAG Assistant](https://github.com/Harshithpatali/rag-math-assistant) | Complex Analysis textbook ingestion, PDF/TXT chunking, vector retrieval, Groq generation, FastAPI, Streamlit and LLM-as-a-Judge evaluation. | Focuses on source-grounded technical tutoring. No retrieval hit-rate or expert-reviewed answer-accuracy benchmark is published. |
| [Multi-LLM Evaluation & Synthesis](https://github.com/Harshithpatali/multi-llm-ai-platform) · [Live demo](https://multi-llm-ai-platform-cf4zxquxedber9fn3hnnxz.streamlit.app/) | Parallel inference across DeepSeek, Llama 3.3, OpenRouter and Groq; seven-dimension AI judge; ChromaDB memory; answer synthesis and latency/token/cost dashboards. | Records judge scores, latency, token use and estimated cost. No controlled quality benchmark is published; model rankings should be treated as exploratory until evaluated against labelled data and human agreement. |
| [AI-Powered Analytics & AutoML](https://github.com/Harshithpatali/ai-analytics-platform) · [Dashboard](https://ai-analytics-platform-kreefks4zqxbykugnzbob6.streamlit.app/) · [API](https://ai-analytics-platform-rgi6.onrender.com/docs) | CSV/XLSX ingestion, schema validation, cleaning, EDA, feature engineering, training, SHAP and PostgreSQL persistence. Regression: Linear Regression and Gradient Boosting. Classification: Logistic Regression, Random Forest, XGBoost, LightGBM and SVM. | Demonstrates a guided analytics workflow, but the repository does not publish a fixed held-out benchmark or a common comparison result. Present as workflow automation rather than proof of superior AutoML performance. |

## Research interest

**Wavelet-based attention mechanisms for Transformers.** I’m interested in multi-resolution sequence representations, scale-aware attention and the efficiency/robustness trade-offs for time-series and audio tasks. This is an exploratory research direction—not a completed or benchmarked architecture.

## Working principles

1. Establish a credible baseline before tuning a complex model.
2. Respect data grain, sampling and temporal boundaries.
3. Keep validation, locked test and blind-holdout evidence separate.
4. Label scenario economics as assumptions, not realised impact.
5. Explain model limitations alongside performance.
6. Connect analysis to reproducible code, APIs and usable dashboards.

## Technical areas

Python · SQL · PostgreSQL · Pandas · NumPy · SciPy · scikit-learn · XGBoost · LightGBM · PyWavelets · NetworkX · PySpark · Hadoop · MLflow · SHAP · FastAPI · Streamlit · Docker · GitHub Actions · Redis · Celery

## Contact

- Email: harshikollur302@gmail.com
- LinkedIn: https://www.linkedin.com/in/harshith-devaraja-087ba0228
- GitHub: https://github.com/Harshithpatali

The portfolio site uses original inline SVG diagrams and CSS rather than stock-photo decoration. Metrics above are tied to the named evaluation split or artifact where indicated. Metrics from different projects and datasets are not directly comparable.
