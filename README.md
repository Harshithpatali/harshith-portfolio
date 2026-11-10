# Harshith Devaraja — Data Science & Applied ML Portfolio

**Live site:** https://harshithpatali.github.io/harshith-portfolio/  
**Résumé:** https://harshithpatali.github.io/harshith-portfolio/resume.html

A curated portfolio of analytical products, machine-learning research, statistical experimentation, signal-processing work and applied AI systems, with three deep case studies and fifteen additional projects. The site separates three detailed case studies from a broader project index and explicitly distinguishes measured results from assumptions and research ideas.

## Selected case studies

| Project | What it demonstrates | Evidence and important context |
|---|---|---|
| [Customer Intelligence & Graph Anomaly Lab](https://github.com/Harshithpatali/Graph-anomaly-supervised-neural-prediction) | Customer profiles, K-means segmentation, Isolation Forest + LOF anomaly ranking, user-device-IP graph investigation | Graph bounded to 50,000 transactions. Historical fraud label is excluded from the current unsupervised workflow. Rankings are cohort-relative review signals, not calibrated fraud probabilities. [Live app](https://graph-anomaly-supervised-neural-prediction-v1.streamlit.app/) |
| [Brazilian E-commerce Intelligence](https://github.com/Harshithpatali/brazilian-ecommerce-data-science) | SQL-first data modeling, customer RFM, cohorts, Kaplan–Meier purchase survival, statistical analysis and dashboard delivery | 16 SQL build stages, 20+ analytical tables/views, 7 dashboard pages and 57 point-in-time features. Holdout PR-AUC 0.01048 vs 0.01665 frequency baseline; churn model remains research-only. [Live app](https://olist-ecommerce-ds.streamlit.app/) |
| [Causal Experimentation Intelligence](https://github.com/Harshithpatali/causal_experimentation_platform) | Experiment checks, A/B tests, ATE/ATT, S/T/X learners, uplift ranking and scenario economics | Stratified 80K sample balanced 50/50; observed conversion 0.4775% vs 0.3475% (+0.13 pp; p=0.0041; 95% CI +0.041 to +0.219 pp). Original Criteo design is approximately 85% treated; ROI is assumption-driven scenario analysis, not realised profit. [Live app](https://causal-ai-customer-growth-intelligence.streamlit.app/) |

## Project index

### Data science, forecasting and engineering

- [Retail Demand & Inventory Optimization](https://github.com/Harshithpatali/retail-demand-inventory-optimization) — M5 forecasting with XGBoost/LightGBM and periodic-review inventory simulation. 200 item-store series and 388,200 feature rows. On the held-out simulation period, the selected policy reduced modeled total cost by 16.21% and increased service level by 2.46 pp under documented demonstration assumptions. [Dashboard](https://retail-demand-inventory-optimization-v1.streamlit.app/) · [API](https://retail-demand-inventory-optimization.onrender.com/)
- [Enterprise ML Platform](https://github.com/Harshithpatali/enterprise-ml-platform) — Hadoop HDFS, PySpark medallion pipeline, 180-day lookback / 90-day target, 19 temporal features, SHAP, FastAPI, Streamlit and 16 tests. The README documents severe target imbalance; this is presented as data engineering and model-governance work, not a claim of production-ready churn prediction.
- [Sensex Quant Lab](https://github.com/Harshithpatali/Sensex_Quant_Lab) — next-session Open/Close forecasting, model search, TimeSeriesSplit validation and weekday retraining. Research tool, not a trading signal.
- [Bayesian & Sequential Experimentation](https://github.com/Harshithpatali/bayesian-sequential-experimentation) — synthetic experiments, power analysis, Beta-Binomial Bayesian inference, sequential testing and multiple-testing control.

### Applied AI and evaluation

- [LLM Prompt Evaluation & Benchmarking](https://github.com/Harshithpatali/llm-prompt-benchmark) — structured product-attribute extraction evaluated across prompt strategies, model providers, extraction metrics, latency and cost. Four prompt strategies are implemented; other variants are documented as planned.
- [LLM Reliability & Evaluation Platform](https://github.com/Harshithpatali/llm-evaluation-platform) — FastAPI, Celery, Redis, asynchronous quality telemetry, KS testing and Wasserstein drift diagnostics. [Dashboard](https://llm-evaluation-platform-q.streamlit.app/) · [API](https://llm-evaluation-platform-1.onrender.com/docs)
- [LLM-as-a-Judge for E-commerce](https://github.com/Harshithpatali/llm-judge-ecommerce) — rubric-based content evaluation for faithfulness, completeness, clarity, persuasiveness and format compliance. [Dashboard](https://llm-judge-ecommerce-c.streamlit.app/)
- [TCS Financial Intelligence Agent](https://github.com/Harshithpatali/financial-intelligence-agent) — annual-report parsing, BGE embeddings, ChromaDB retrieval and source-grounded question answering. [Live app](https://financial-intelligence-agent-g.streamlit.app/)
- [Math RAG Assistant](https://github.com/Harshithpatali/rag-math-assistant) — textbook-grounded complex-analysis tutor with document retrieval and LLM evaluation.

### Customer intelligence and causal policy

- [AI-Powered E-commerce Intelligence](https://github.com/Harshithpatali/ecommerce-intelligence) — CLV prediction, segmentation, SHAP explanations, retention prioritisation, product recommendations and AI-generated business insights. [Dashboard](https://ecommerce-intell.streamlit.app/) · [API docs](https://ecommerce-intelligence-xod0.onrender.com/docs)
- [Causal Uplift Marketing Optimization](https://github.com/Harshithpatali/causal-uplift-marketing-optimization) — 64K-customer Hillstrom experiment, multi-arm uplift models, held-out Qini/AUUC and targeting-policy evaluation. Best AUUC 0.002054 and Qini 0.004129; the 50% targeting policy estimates 41.9 incremental conversions and $6,051 revenue on the evaluation sample, not a future guarantee.

### Applied AI systems

- [Multi-LLM Evaluation & Educational Synthesis](https://github.com/Harshithpatali/multi-llm-ai-platform) — parallel inference across LLM providers, a seven-dimension judge, ChromaDB memory and latency/cost dashboards. [Live app](https://multi-llm-ai-platform-cf4zxquxedber9fn3hnnxz.streamlit.app/)
- [AI-Powered Analytics & AutoML Platform](https://github.com/Harshithpatali/ai-analytics-platform) — dataset ingestion, automated cleaning, EDA, feature engineering, model training and SHAP explainability. [Dashboard](https://ai-analytics-platform-kreefks4zqxbykugnzbob6.streamlit.app/) · [API docs](https://ai-analytics-platform-rgi6.onrender.com/docs)

### Signal processing and research

- [DeepFake Noise & Wavelet Forensics](https://github.com/Harshithpatali/deepfake-noise-wavelet-ml) — interpretable 105-feature image-forensics pipeline on 304,154 images. Validation ROC-AUC 0.9249, PR-AUC 0.9124 and accuracy 0.9086; validation numbers are explicitly labelled as such. [Live app](https://deepfake-noise-wavelet-ml-hd.streamlit.app/)
- [Wavelet Voice Lab](https://github.com/Harshithpatali/Wavelet-Domain-Robust-Voice-Communication-Lab) — DWT decomposition, keyed coefficient permutation, noisy-channel experiments and voice reconstruction. An academic prototype; keyed scrambling is not cryptography.

## Research interest

**Wavelet-based attention mechanisms for Transformers.** I am interested in multi-resolution sequence representations, scale-aware attention and the efficiency/robustness trade-offs for time-series and audio tasks. This is an exploratory direction, not a completed or benchmarked architecture.

## Working principles

1. Establish a credible baseline before tuning a complex model.
2. Respect data grain, sampling and temporal boundaries.
3. Keep validation and holdout evidence separate.
4. Label scenario economics as assumptions, not realised impact.
5. Explain model limitations alongside performance.
6. Connect analysis to reproducible code, APIs and usable dashboards.

## Technical areas

Python · SQL · PostgreSQL · Pandas · NumPy · SciPy · scikit-learn · XGBoost · LightGBM · PyWavelets · NetworkX · PySpark · Hadoop · MLflow · SHAP · FastAPI · Streamlit · Docker · GitHub Actions · Redis · Celery

## Contact

- Email: harshikollur302@gmail.com
- LinkedIn: https://www.linkedin.com/in/harshith-devaraja-087ba0228
- GitHub: https://github.com/Harshithpatali

The portfolio website uses original inline SVG diagrams and CSS, with no stock-photo dependency. Performance claims are taken from the linked repositories' READMEs and committed evaluation notes; scenario assumptions and research directions are identified explicitly.
