# 🩺 Patient Readmission Prediction using Databricks Lakehouse Architecture

🎯 **Capstone Project | Healthcare Analytics & Machine Learning**  
🎥 *First-ever video project & end-to-end implementation*

---

## 📌 Project Overview

Hospital readmissions within 30 days are costly, stressful for patients, and often preventable.  
This project focuses on **predicting patient readmissions**, specifically for **diabetic patients**, so hospitals can take **early preventive actions** instead of reacting after the patient returns.

This is my **capstone project** completed as part of the  
**Codebasics × Databricks 14-Day Data & AI Challenge**, where I built an **end-to-end AI solution** using the **Databricks Lakehouse Architecture** — from raw data ingestion to business-ready risk predictions.

---

## ❓ Problem Statement

- Around **20% of discharged patients** are readmitted within 30 days  
- Avoidable readmissions cost US hospitals **$26B+ annually**
- Diabetic patients face higher risk due to multiple complications

🔍 **Goal:**  
Predict which diabetic patients are at **high risk of readmission within 30 days**, enabling hospitals to:
- improve discharge planning  
- prioritize care coordination  
- optimize clinical resources  
- improve patient outcomes  

---

## 🏗️ Solution Architecture

This project follows the **Databricks Lakehouse Architecture** using the **Medallion Pattern**:

### 🥉 Bronze Layer – Raw Data
- Raw hospital encounter data ingested using **Apache Spark**
- Stored in **Delta Lake** format
- No transformations applied (source of truth preserved)

### 🥈 Silver Layer – Clean & Standardized
- Missing and placeholder values handled
- Categorical fields standardized
- Data types corrected
- Irrelevant columns removed

### 🥇 Gold Layer – Business & ML Ready
- Curated dataset for analytics and ML
- Optimized using Delta optimizations
- Single source of truth for dashboards and models

---

## 📊 Dataset Description

The dataset contains **diabetic patient hospital encounter data**, including:

- **Demographics:** age, gender, race  
- **Admission details:** admission type, days in hospital, discharge disposition  
- **Hospital utilization:** inpatient, outpatient, emergency visits  
- **Clinical indicators:** diagnoses, lab procedures, medications  

📌 Each row represents **one hospital encounter** (patients may appear multiple times).

---

## ⚙️ Feature Engineering Strategy

Features were grouped to reflect **real-world clinical reasoning**:

- **Demographics:** patient profile patterns  
- **Hospital utilization:** dependency on healthcare services  
- **Clinical indicators:** medical complexity  
- **Admission details:** severity of hospital stay  

These features help the model understand the **overall patient risk**, not just isolated values.

---

## 🤖 Machine Learning Pipeline

Built using **Spark ML Pipeline** to ensure consistency and reliability:

1. **StringIndexer** – converts categorical values into numeric format  
2. **VectorAssembler** – combines all features into a single feature vector  
3. **Classifier** – model training and prediction  

### Models Evaluated
- Logistic Regression ✅ *(selected)*
- Random Forest

### Evaluation Approach
- Focused on **Recall over Accuracy**
- Healthcare priority: *missing a high-risk patient is worse than a false alert*
- Threshold tuned to **0.2** for better sensitivity

---

## 📈 Analytics & Insights

Using **Databricks SQL** on the Gold layer, key insights were identified:

- Majority of patients fall into low-risk category  
- High-risk patients show ~**68% average readmission probability**  
- Frequent **emergency visits** strongly correlate with readmission risk  

These insights validate both the **data preparation** and **feature selection**.

---

## 🧪 MLflow Experiment Tracking

**MLflow** was used for transparent and reproducible ML experimentation:

- Tracked model parameters and hyperparameters  
- Logged metrics: AUC, Accuracy, Recall, Precision  
- Stored full Spark ML pipeline as artifacts  
- Enabled side-by-side model comparison  

---

## 🏥 Business Impact & Use Cases

This solution can support hospitals in:

- **Discharge Planning:** flag high-risk patients before discharge  
- **Care Coordination:** prioritize outreach for high-risk patients  
- **Clinical Decision Support:** assist clinicians with risk-aware monitoring  
- **Resource Optimization:** focus limited resources where they matter most  

📌 Risk scores are stored in **Delta tables** and can be directly consumed by dashboards for non-technical stakeholders.

---

## 🚧 Challenges Faced

- Real-world healthcare data complexity  
- Severe class imbalance (accuracy ≠ usefulness)  
- Aligning ML metrics with business goals  
- Maintaining consistency across data pipeline and inference  
- Schema conflicts while writing predictions back to Delta Lake  

---

## 💡 Key Learnings

- ✔ Metric selection matters more than model complexity  
- ✔ Recall is critical in healthcare ML problems  
- ✔ Threshold tuning can significantly improve usefulness  
- ✔ ML pipelines prevent data leakage and improve reliability  
- ✔ Lakehouse architecture simplifies end-to-end workflows  
- ✔ ML delivers value only when integrated into real processes  


## 📽️ Project Demo & Documentation

🎥 **YouTube Video Presentation:**  
👉 (https://youtu.be/ftbUcdxdcQ8?si=gJdCeZ1f66yKnGX7)

📂 **Project Documentation & Code:**  
👉 [*This GitHub repository*](https://github.com/Pujitha0821/patient-readmission-databricks)

---

## 🙏 Acknowledgements

Thanks to **Codebasics** and **Databricks** for the structured learning experience and hands-on challenge that made this project possible.

This project pushed me out of my comfort zone — and that’s where the real learning happened.

---

## 👩‍💻 Author

**Pujitha Pakala**  
Aspiring Data Analyst | Healthcare & AI Enthusiast  

---

⭐ *If you find this project interesting, feel free to star the repository!*  
