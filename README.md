# Early Biomarker Discovery for Lung Cancer Using High-Dimensional RNA Sequencing Data

This repository presents a **biomarker-oriented machine learning framework** for detecting lung cancer using **high-dimensional RNA sequencing data**.  
Unlike traditional workflows focused only on classification performance, this project emphasizes:

- **Early detection potential** through gene-level signal separation  
- **Biomarker discovery** using interpretable feature importance  
- **Stability across folds** to ensure reproducibility  
- **Handling extreme feature dimensionality** (20,530 genes)

The goal is not just to classify samples, but to **identify transcriptomic signatures** that consistently distinguish cancerous from non-cancerous lung tissue.

---

## 📌 Dataset Overview

- **Source:** RNA-seq expression matrix (20,530 genes)  
- **Target Variable:** `sample_type_id`  
  - `0.0` → Non-cancer  
  - `1.0` → Cancer  
- **Feature Space:**  
  - Extremely high-dimensional transcriptomics  
  - Gene expression values as continuous numeric features  
- **Objective:** Reveal robust biomarkers while achieving high diagnostic accuracy

---

## 🧬 Project Highlights (Novelty)

### 🔍 **1. Biomarker-Centric Feature Discovery**
Although the dataset is high-dimensional, the model reveals a **small set of dominant genes** that capture the majority of predictive signal.  
This supports the biological hypothesis that **lung cancer progression is driven by concentrated transcriptomic disruptions**.

### 🧪 **2. Extreme Dimensionality Handling (20,530 Features)**
The workflow emphasizes:
- Mutual Information for relevance filtering  
- XGBoost for sparse-signal pattern learning  
- Stability of selected genes across folds  

This showcases effective learning under **p >> n** conditions (features far exceed samples).

### 🧠 **3. Robust & Reproducible Detection**
Cross-validation accuracy remains consistently above **99%**, showing the approach generalizes well despite small sample imbalance.

### 🔄 **4. Heterogeneity-Aware Modeling**
Lung cancer exhibits high molecular heterogeneity.  
This project’s explainability module helps highlight **patient-level heterogeneity** by quantifying the influence of each gene on predictions.

---

## ⚙️ Workflow Overview

1. **Data Preprocessing**  
   - Normalization of gene expression values  
   - Handling high-dimensional structure  
2. **Feature Selection**  
   - Mutual Information to identify relevant genes  
3. **Classification Model**  
   - XGBoost (optimized for sparse signal patterns)  
4. **Evaluation**  
   - Classification metrics  
   - Cross-validation reliability  
5. **Explainability**  
   - Ranking of top genes by model importance  

---

## 📈 Model Performance

### **Classification Report**

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0.0 (Non-Cancer) | 0.97 | 0.97 | 0.97 | 29 |
| 1.0 (Cancer)     | 1.00 | 1.00 | 1.00 | 301 |

- **Accuracy:** 0.99  
- **Macro F1 Score:** 0.98  
- **Weighted F1 Score:** 0.99  

---

## 🔁 Cross-Validation Performance (5-Fold)

| Fold | Accuracy |
|------|----------|
| 1 | 1.000 |
| 2 | 0.9935 |
| 3 | 1.000 |
| 4 | 0.9935 |
| 5 | 0.9935 |

**Average Accuracy:** 0.9961  

> Stability across folds highlights strong generalization despite high-dimensional gene space.

---

## 🧬 Top 20 Biomarker Genes (Feature Importance)

| Rank | Gene | Importance |
|------|------|------------|
| 1 | **STX11** | 0.4773 |
| 2 | SFTPC  | 0.0574 |
| 3 | ADPRH  | 0.0496 |
| 4 | PECAM1 | 0.0429 |
| 5 | ADRB2  | 0.0279 |
| 6 | FAM107A | 0.0265 |
| 7 | TGFBR2 | 0.0172 |
| 8 | JPH4 | 0.0136 |
| 9 | HPS4 | 0.0128 |
| 10 | OPLAH | 0.0116 |
| 11 | ABCC5 | 0.0104 |
| 12 | CNTD2 | 0.0094 |
| 13 | ADAM11 | 0.0093 |
| 14 | RAB21 | 0.0089 |
| 15 | MC1R | 0.0087 |
| 16 | STRC | 0.0086 |
| 17 | BCS1L | 0.0086 |
| 18 | DNM1P35 | 0.0082 |
| 19 | PLD2 | 0.0081 |
| 20 | ZNF18 | 0.0081 |

### 🧠 Biological Insight
- **STX11** dominates predictive importance, suggesting it may act as a core signature in this dataset.  
- Several immune-linked and structural genes appear, hinting at immune dysregulation in lung cancer microenvironments.

---

## 🧠 Key Takeaways

- **Near-perfect diagnostic performance** using transcriptomic profiles.  
- **Strong biomarker discovery potential**, especially around STX11 and PECAM1.  
- **Generalizes well across folds**, indicating robustness.  
- **Explainability reveals focused gene-level disruptions**, valuable for follow-up biological studies.

---

## 🛠 Tools & Technologies

- Python  
- XGBoost  
- Scikit-Learn  
- Pandas & NumPy  
- Matplotlib / Seaborn (optional for plots)

---

## 🤝 Contribution
This repository is for research demonstration only.  
For collaboration, questions, or discussions, feel free to open an issue.

