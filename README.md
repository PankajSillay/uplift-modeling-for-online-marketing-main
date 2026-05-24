# Uplift Modeling for Online Marketing

A segmentation-driven, causal machine learning framework designed to optimize online marketing campaigns by answering three critical questions:

- **WHO** should be targeted?
- **WHAT** treatment should be delivered?
- **WHEN** should the treatment be delivered?

This project goes beyond traditional conversion prediction by focusing on **incremental impact (uplift)**, ensuring marketing resources are spent only on users who are truly influenced by the treatment.

---

## 📌 Problem Statement

Traditional marketing models predict the probability of conversion but fail to answer:
- Would the user convert **without** treatment?
- Is the treatment actually causing the conversion?
- When is the best time to intervene?

This leads to:
- Wasted marketing budget
- Over-targeting
- Poor ROI

**Uplift Modeling** addresses this by estimating the **causal effect** of a treatment on user behavior.

---

## 🧠 Solution Overview

This project implements a **WHO–WHAT–WHEN decision pipeline** enhanced with customer segmentation:

### 1️⃣ WHO – Target Selection
- Identifies users who convert **because of** treatment
- Uses **T-Learner uplift modeling**
- Outputs an **uplift score** per user

### 2️⃣ WHAT – Treatment Recommendation
- Predicts the most effective treatment type
- Multi-class classification problem

### 3️⃣ WHEN – Time Optimization
- Predicts the best time window for treatment delivery
- Maximizes engagement and conversion probability

Each stage is trained **segment-wise** using K-Means clustering to capture behavioral heterogeneity.

---

## 📂 Dataset

- **Source:** Criteo AI Lab Incrementality Dataset
- **Size:** ~13 million records
- **Core Fields:**
  - Numerical features (f0–f11)
  - Treatment indicator
  - Visit and conversion labels

### Engineered Features
- Temporal: hour, day, month, season
- Behavioral: recency, frequency, monetary value
- Engagement: visit rate, conversion rate, engagement score
- Treatment attributes: type, cost
- Customer segmentation (K-Means clusters)

---

## 🏗️ Architecture

→ Raw Data
→ EDA & Feature Engineering
→ Customer Segmentation (K-Means)
→ WHO Model (Uplift / T-Learner)
→ WHAT Model (Treatment Recommendation)
→ WHEN Model (Time Optimization)
→ Final Personalized Recommendation


---

## 🤖 Models Used

### WHO (Uplift Models)
- Decision Tree
- Random Forest
- Gradient Boosting
- Linear SVC (calibrated)

### WHAT & WHEN (Classification Models)
- Decision Tree
- Random Forest
- Gradient Boosting
- Linear SVC

---

## 📊 Evaluation Metrics

### Uplift Evaluation (WHO)
- Qini Coefficient
- AUUC (Area Under Uplift Curve)
- Uplift Gain (Top Decile)

### Classification Evaluation (WHAT & WHEN)
- Accuracy
- ROC-AUC (where applicable)

---

## 🏆 Key Results

- **Random Forest** achieved the best uplift performance across most segments
- Segment-wise modeling significantly improved causal discrimination
- **Linear SVC** performed best for treatment recommendation
- **Gradient Boosting / Linear SVC** performed best for time optimization

---

## 🛠️ Tech Stack

- Python
- Scikit-learn
- XGBoost
- Pandas, NumPy
- Matplotlib, Seaborn
- Google Colab

---

## 🚀 How to Run

1. Open the Google Colab notebooks (links provided below)
2. Load the dataset (Kaggle / Drive)
3. Run preprocessing & feature engineering
4. Train uplift and classification models
5. Evaluate using uplift-specific metrics

---

## 🔮 Future Work

- Individual-level uplift personalization
- Budget-aware and cost-sensitive optimization
- Joint WHO–WHAT–WHEN optimization using Reinforcement Learning
- Deep learning / transformer-based uplift models
- Explainability using SHAP for causal effects

---

## 🔗 Resources

- Dataset: Kaggle – Criteo Uplift Modeling Dataset
- Code (Google Colab):
  - https://colab.research.google.com/drive/1-jOI906eD4otuOaz54wDiYgN_x_MWUQH
  - https://colab.research.google.com/drive/1xQJZPZFujTXOohbNKG3g39TpbmKuA1Ed
  - https://colab.research.google.com/drive/1XPlJ5cf7XEkxLTDnmcpt5v7bX4LvshD-

---