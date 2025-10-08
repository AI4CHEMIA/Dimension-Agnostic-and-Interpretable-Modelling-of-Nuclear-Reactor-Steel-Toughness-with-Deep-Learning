# Predictive Framework for DBTT and USE Estimation in Structural Steels

This repository presents a comprehensive workflow for predicting **ductile-to-brittle transition temperature (DBTT)** and **upper shelf energy (USE)** in steels using an integrated attention-based deep learning framework. The approach combines **physics-informed feature engineering**, **attention-enhanced multilayer perceptrons (MLP)**, and **Evidential Deep Learning (EDL)** to achieve accurate and uncertainty-aware predictions, facilitating reliable evaluation of structural integrity in critical applications such as pipelines, pressure vessels, and cryogenic systems.

---

# ✨ Overview

**Dataset:** 4,105 experimental samples comprising 167 descriptors, including Magpie-derived features, compositional variables, impact energy, and test temperature.

**Descriptors:** Physics-informed and statistically curated features embedding compositional, microstructural, and thermomechanical information.

**Models:**

- **Attention-Enhanced MLP:** Learns nonlinear feature–property relationships with adaptive weighting through an attention mechanism.
- **Evidential Deep Learning (EDL):** Extends the MLP to jointly predict property values and associated aleatoric and epistemic uncertainties.
- **Baselines:** Ensemble regressors—Random Forest, Extra Trees, and XGBoost—for comparative evaluation.

**Evaluation Metrics:** MAE, RMSE, R², and Negative Log-Likelihood (NLL) to assess prediction accuracy and uncertainty calibration.

---

# 📂 Repository Structure

```

├── dataset/ # Dataset files
├── MLP/ # Scripts for attention-based MLP and EDL training
├── mlp_models/ # Saved MLP and EDL model checkpoints
├── Traditional ML/ # Random Forest, XGBoost, and Extra Trees training scripts
└── README.md

```

---

# ⚙️ Methodology Pipeline

### 1. Data Preprocessing

- Curated dataset containing 4,105 samples with 167 descriptors.
- Integration of compositional, impact energy, and temperature data.
- Standardization and outlier filtering to ensure model robustness.

### 2. Feature Engineering

- Physics-informed and Magpie-derived features capturing composition–structure–property relationships.
- Redundancy reduction via correlation and variance filtering.
- Domain-guided feature selection to preserve interpretability.

### 3. Modeling

- **Attention-Enhanced MLP:**
  - Layers: Dense + Attention + Dropout
  - Optimizer: Adam with learning rate scheduling
  - Hyperparameter tuning using Optuna
- **Evidential Deep Learning (EDL):**
  - Output: Normal–Inverse–Gamma (μ, ν, α, β) parameters
  - Captures both aleatoric and epistemic uncertainty
  - Penalized loss to balance accuracy and uncertainty calibration
- **Baselines:**
  - Random Forest, Extra Trees, and XGBoost regressors trained on identical features for fair comparison.

### 4. Evaluation

- Metrics: MAE, RMSE, R², and NLL.
- EDL demonstrated improved uncertainty calibration and overall predictive reliability.

---

# 🧩 Key Contributions

- Integration of **attention mechanisms** within MLP for selective feature relevance learning.
- Application of **Evidential Deep Learning** for simultaneous prediction and uncertainty estimation.
- Development of a **physics-informed, data-driven** framework for fracture behavior modeling.
- Establishes a **reliable and interpretable** predictive pipeline for materials design and screening.
