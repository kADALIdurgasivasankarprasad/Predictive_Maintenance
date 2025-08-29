# 🚀 Predictive Maintenance for Wind Turbines

## 📌 Project Overview
This project predicts **system failures within the next 48 hours** using **machine learning**.  
It combines:
- **Supervised Learning (RandomForest Classifier)** → learns from labeled data.  
- **Unsupervised Learning (IsolationForest)** → detects anomalies without labels.  

The project is implemented in **Google Colab** and evaluates models on **imbalanced datasets**, where failure events are rare.

---

## ⚙️ Workflow

1. **Data Preparation**
   - Loaded dataset with operational features and labels (`failure` / `normal`).  
   - Preprocessed missing values, scaling, and train-test split.  
   - Defined target = *failure in next 48h*.  

2. **Handling Imbalanced Data**
   - Applied **SMOTE oversampling** to balance rare failure cases.  
   - Used `class_weight="balanced"` in RandomForest to penalize misclassification of failures.  

3. **Modeling**
   - **RandomForestClassifier (Supervised):**
     - Handles class imbalance.
     - Learns from historical failures.
   - **IsolationForest (Unsupervised):**
     - Detects anomalies without labeled failures.

4. **Evaluation Metrics**
   - Precision  
   - Recall  
   - F1-Score  
   - **False Alarm Rate (FAR):** proportion of false positives among normal cases.  
   - **Lead Time Before Failures:** how early the model predicts failure before the actual event.  

---

## 📊 Results (Sample)

| Model                        | Precision | Recall | F1 Score | False Alarm Rate | Lead Time |
|-------------------------------|-----------|--------|----------|------------------|-----------|
| RandomForest (Supervised)     | ↑ Improved | ↑ Better | ↑ Better | Reduced | Provides early warning |
| IsolationForest (Unsupervised)| Lower      | Lower  | Moderate | Higher           | Not Applicable |

- **RandomForest** is better when labeled data is available.  
- **IsolationForest** helps when only normal behavior is known.  

---

## 📈 Key Insights
- RandomForest **captures failures better after imbalance handling** (SMOTE + class weights).  
- IsolationForest **detects anomalies**, useful when failure labels are missing.  
- Adding **FAR** ensures the model doesn’t raise too many false alarms.  
- **Lead Time** shows how much advance warning the model gives → crucial for predictive maintenance.  

---

## 🚀 How to Run in Colab
1. Open the project in [Google Colab](https://colab.research.google.com/).  
2. Upload your dataset (with timestamps and failure labels if available).  
3. Run cells step by step:
   - Data preprocessing  
   - Train-test split  
   - Apply SMOTE  
   - Train RandomForest & IsolationForest  
   - Evaluate metrics (Precision, Recall, F1, FAR, Lead Time)  
4. At the end, generate the **PDF Report** from Colab.  

---

## 🔮 Future Improvements
- Try advanced models: **XGBoost, LightGBM** for better supervised performance.  
- Use **time-series deep learning (LSTM, GRU, Prophet)** for sequential failure patterns.  
- Deploy as a **real-time monitoring system** with live alerts.  

---

## 📂 Project Deliverables
- `notebook.ipynb` → Google Colab Notebook  
- `Failure_Prediction_Project_Report.pdf` → Auto-generated project summary  
- `README.md` → Documentation (this file)  

---

👨‍💻 **Author**: Budatha Koja  
📅 Year: 2025  
