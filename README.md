
# 🩺 Chronic Kidney Disease Detection

### **Supervised + Unsupervised Machine Learning with Explainable AI (XAI)**

*A complete end-to-end ML pipeline integrating classification, clustering, feature engineering, and interpretability.*

---

## 📌 Project Overview

This project presents a **comprehensive machine learning pipeline** for **Chronic Kidney Disease (CKD)** detection and patient phenotyping.
It is designed using:

* **Supervised ML Models** → XGBoost, CatBoost, Random Forest, LightGBM
* **Unsupervised ML Models** → K-Means, DBSCAN, GMM, Spectral Clustering
* **Explainable AI (XAI)** → SHAP, LIME, Permutation Importance
* **Advanced Feature Engineering & Data Preprocessing**
* **Hyperparameter Optimization** (Optuna, Bayesian Optimization)

The goal is to deliver a **clinically interpretable**, **high-performance**, and **robust predictive system** suitable for early CKD detection and patient risk stratification.

---

## 🚀 Key Features

✔️ Full end-to-end ML lifecycle
✔️ Handles missing values, noise, and imbalanced classes
✔️ Feature engineering with domain-specific clinical indices
✔️ Multiple clustering pipelines to uncover hidden patient groups
✔️ SHAP-based interpretability for clinical trust
✔️ Hyperparameter tuning for maximum model performance
✔️ Visualizations of all steps (EDA, clustering, ROC, confusion matrices)

---

## 📂 Project Structure

```
📁 Chronic-Kidney-Disease-Detection
│
├── 📄 notebook.ipynb                # Full implementation
├── 📄 report.pdf                    # Detailed academic project report
├── 📄 kidney_disease.csv            # Dataset
├── 📄 README.md                     # Project documentation
│
├── 📁 models/                       # Saved models (optional)
├── 📁 visuals/                      # Charts, ROC curves, clustering plots
└── 📁 src/                          # Scripts for modular deployment
```

---

## 🧪 Dataset

* **Source:** UCI / Kaggle CKD dataset
* **Size:** 400 patient records
* **Features:** 25 clinical attributes

  * Hemoglobin
  * Serum creatinine
  * Blood pressure
  * Specific gravity
  * Albumin
  * RBC count
  * Diabetes / Hypertension indication
* **Target:** CKD vs. non-CKD (binary)

---

## 🛠 Methodology Summary

### **1️⃣ Data Preprocessing**

* Dropped irrelevant columns (`id`)
* Standardized column names
* Fixed categorical inconsistencies (`yes`, ` no`, `notpresent`, etc.)
* Handled missing values using:

  * **Mode imputation**
  * **Random sampling imputation**
* Converted mixed-type columns into numeric format
* Encoded target labels (`ckd → 0`, `notckd → 1`)

---

### **2️⃣ Exploratory Data Analysis**

* Distribution plots for all categorical & numerical features
* Class imbalance evaluation
* Correlation heatmap
* Boxplots for medical indicators
* Identified clinically important features (hemoglobin, PCV, albumin, etc.)

---

### **3️⃣ Unsupervised Learning**

Pipelines implemented:

| Model                            | Description                                           |
| -------------------------------- | ----------------------------------------------------- |
| **DBSCAN**                       | Density-based clustering (failed due to high overlap) |
| **Spectral Clustering**          | Graph-based approach with moderate cluster separation |
| **Improved K-Means**             | PCA + silhouette score → k=2                          |
| **Gaussian Mixture Model (GMM)** | Best at revealing hidden subgroups (k=6)              |

➡ **GMM identified meaningful CKD subgroups**, highlighting hidden phenotypes.

---

### **4️⃣ Supervised Learning Models**

All models included:

* Feature engineering
* Feature selection (SHAP, MI, RFECV)
* Hyperparameter tuning (Optuna)
* SMOTE for class imbalance
* Probability calibration

#### **Model Performance**

| Model             | Accuracy | AUC  | Notes                           |
| ----------------- | -------- | ---- | ------------------------------- |
| **CatBoost**      | **99%**  | 1.00 | Best overall performance        |
| **Random Forest** | 99%      | 1.00 | Excellent interpretability      |
| **LightGBM**      | 99%      | 1.00 | Efficient with large-scale data |
| **XGBoost**       | 97%      | 0.99 | Great with engineered features  |

---

### **5️⃣ Explainable AI (XAI)**

Used to ensure **clinical transparency**:

✔ **SHAP summary plots**
✔ **Permutation importance**
✔ **LIME explanations**
✔ **Feature importance scores**

Top influential features consistently included:

* Serum Creatinine
* Hemoglobin
* Packed Cell Volume
* Albumin
* Specific Gravity

---

## 📊 Results Snapshot

### ⭐ Best Supervised Model

**CatBoost Classifier**

* Accuracy: **99%**
* Precision & Recall: **1.00**
* AUC: **1.00**
* Perfect separation of CKD vs non-CKD

### ⭐ Best Unsupervised Model

**Gaussian Mixture Model (GMM)**

* Revealed **6 hidden patient groups**
* One cluster contained 145/150 CKD cases
* Provides new clinical insights

---

## 📈 Visualizations Included

* ROC curves
* Confusion matrices
* SHAP summary plots
* PCA visualizations
* t-SNE cluster maps
* k-distance graphs
* Silhouette score plots

---

## 💡 Future Work

* Deploy model with **Streamlit** dashboard
* Integrate into a clinical decision support system (CDSS)
* Add time-series modeling for CKD progression
* Collect a larger and more diverse dataset

---

## 👨‍💻 Team Members

* **Ali Sena Danishwer** – Supervised Learning & Coding Lead
* **Bakary Gibba** – Project Manager & Supervised ML Lead
* **Rashidul Islam** – Unsupervised ML & Reporting Lead
* **Hafizullah Mohammadi** – Data Processing & Validation Lead

---

## 📜 Citation

If you use this project for academic work, please cite our report.

---

## 🧷 License

This project is licensed under the **MIT License**.

---
Best Regards, 
Ali Sena Danishwer

