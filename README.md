# Machine Learning Approaches for Breast Cancer Classification

**University of Newcastle · Business Analytics · 2024**  
`Python` `Logistic Regression` `Random Forest` `Classification` `Healthcare Analytics` `Model Evaluation` `Scikit-learn`

---

## 📌 Project Overview

Breast cancer is one of the most prevalent cancers globally, and early, accurate diagnosis is critical to improving patient outcomes. Machine learning classification models can support clinical decision-making by rapidly analysing diagnostic data to distinguish malignant from benign tumours — reducing diagnostic uncertainty and enabling faster treatment initiation.

This project builds, trains, and evaluates **multiple machine learning classification models** on a breast cancer diagnostic dataset, comparing model performance to identify the most accurate and reliable approach for supporting clinical decision support.

> **Note:** This project is for educational and analytical purposes. Results are not intended for clinical use without appropriate validation, regulatory approval, and medical oversight.

---

## 🎯 Business / Clinical Problem

Healthcare providers and diagnostic teams face a critical challenge in breast cancer diagnosis:
- Manual analysis of diagnostic measurements is time-consuming and subject to variability between practitioners
- Misclassification — either false negatives (missed malignancies) or false positives (unnecessary biopsies) — carries serious consequences for patients and healthcare systems
- Early identification of malignant cases significantly improves treatment outcomes and reduces long-term care costs

Machine learning offers the potential to provide **consistent, fast, and accurate classification support** that augments clinical expertise.

---

## 📂 Repository Contents

| File | Description |
|---|---|
| `*.ipynb` | Jupyter Notebook — full ML pipeline: EDA, preprocessing, model training, evaluation, and visualisation |
| `*.csv` | Breast cancer diagnostic dataset (tumour measurements and class labels) |
| `*.pdf` | Full project report — methodology, model comparison, results, and healthcare application discussion |

---

## 🔧 Methodology

### 1. Dataset Overview
- Used a standard breast cancer diagnostic dataset containing **30 numerical features** derived from digitised images of fine needle aspirate (FNA) of breast masses
- Features include: radius, texture, perimeter, area, smoothness, compactness, concavity, symmetry — measured as mean, standard error, and worst value per tumour
- **Target variable:** Binary classification — Malignant (1) or Benign (0)

### 2. Exploratory Data Analysis (EDA)
- Analysed feature distributions across malignant and benign classes
- Identified key features with the strongest separation between classes (radius, concavity, concave points)
- Generated correlation heatmaps to identify multicollinearity and inform feature selection

### 3. Data Preprocessing
- Handled missing values and standardised features using `StandardScaler` (essential for distance-based models)
- Split dataset into training (80%) and test (20%) sets with stratified sampling to preserve class balance
- Checked and addressed class imbalance where present

### 4. Models Trained & Compared

| Model | Key Characteristic | Clinical Relevance |
|---|---|---|
| **Logistic Regression** | Interpretable, probabilistic, baseline standard | Regulatory-friendly, explainable to clinicians |
| **Random Forest** | Ensemble method, handles non-linearity, feature importance | High accuracy, robust to noise in diagnostic data |

### 5. Model Evaluation

Evaluated using metrics critical for healthcare classification:

| Metric | Importance in Healthcare Context |
|---|---|
| **Accuracy** | Overall classification correctness |
| **Recall (Sensitivity)** | Critical — catching all malignant cases; false negatives are the most dangerous error |
| **Precision** | Avoiding unnecessary false positive diagnoses |
| **F1-Score** | Balances precision and recall |
| **AUC-ROC** | Overall discriminative ability of the model |
| **Confusion Matrix** | Detailed view of true/false positives and negatives |

---

## 📊 Key Results

| Model | Accuracy | Recall (Malignant) | AUC-ROC |
|---|---|---|---|
| Logistic Regression | High | High | High |
| Random Forest | Higher | High | Higher |

> **Critical Finding:** **Recall** is the most important metric in this clinical context — a false negative (predicting benign when actually malignant) is far more dangerous than a false positive. Both models were evaluated with this priority in mind, and thresholds were adjusted to maximise sensitivity for malignant detection.

> **Feature Importance (Random Forest):** The most predictive features were `concave points_worst`, `radius_worst`, and `perimeter_worst` — consistent with clinical literature indicating that tumour size and irregularity are key malignancy indicators.

---

## 💡 Business & Clinical Value

| Stakeholder | Value |
|---|---|
| **Radiologists / Pathologists** | Decision support tool to flag high-risk cases for priority review |
| **Hospital administrators** | Reduce diagnostic backlog by triaging cases by risk probability |
| **Health insurers** | Data-driven risk stratification for early intervention programmes |
| **Researchers** | Benchmark ML approaches for future clinical AI development |

---

## 🛠️ Tools & Libraries

| Category | Tools |
|---|---|
| Language | Python 3 |
| Machine Learning | Scikit-learn (Logistic Regression, Random Forest, GridSearchCV) |
| Data Processing | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Evaluation | ROC-AUC, confusion matrix, classification report |
| Environment | Jupyter Notebook |

---

## ⚠️ Ethical Considerations

- **Clinical context:** ML models in healthcare must be validated on diverse, representative datasets before clinical deployment — results here are for educational purposes only
- **Explainability:** Clinicians require interpretable models; black-box predictions without reasoning are insufficient for clinical decision-making
- **Bias:** If training data over-represents certain demographics, model performance may be unequal across patient populations
- **Human oversight:** AI should augment, not replace, clinical expertise in diagnosis — final decisions must remain with qualified medical professionals
- **Data privacy:** Patient diagnostic data must be handled under strict data governance and privacy legislation (Health Records Act, GDPR equivalents)

---

*Project completed as part of the Bachelor of Business Analytics at the University of Newcastle, 2024.*
