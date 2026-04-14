# 🚨 Early Sepsis Prediction using Machine Learning & Deep Learning

Early detection of sepsis in ICU patients can **save lives**. Delays in diagnosis significantly increase mortality risk.  
This project builds and compares **Machine Learning (XGBoost)** and **Deep Learning (LSTM)** models to enable **early, data-driven clinical decisions**.

---

## 🧠 Problem Statement

Sepsis is a **life-threatening condition** caused by the body’s extreme response to infection.

⚠️ Traditional systems often detect sepsis **too late**, limiting treatment effectiveness.

🎯 **Goal:**  
Predict sepsis **hours in advance** to enable **timely medical intervention and improved patient outcomes**.

---

## 📊 Dataset

- 📍 **Source:** PhysioNet Challenge 2019 (ICU data)  
- 📈 **Type:** Multivariate time-series  

### 🔎 Features:
- ❤️ **Vital Signs:** HR, BP, Temp, Respiration  
- 🧪 **Lab Measurements:** WBC, Creatinine, Glucose  
- ⏱️ **ICU Info:** ICULOS (length of stay)

---

## 🛠️ Data Preprocessing

## Handled missing values using:
- 🔄 Forward Fill (FFill)  
- 🔁 Backward Fill (BFill)  
- 📉 Median Imputation  

 Reconstructed **continuous hourly patient timelines**  
 Normalized features using **MinMaxScaler**

📦 Created:
- 📊 Tabular dataset → for XGBoost  
- 🔗 Sequential data → for LSTM  

---

## 🤖 Models Implemented

### 🌳 XGBoost (Tabular Model)

-  Captures **complex non-linear relationships**  
-  Works on **engineered tabular features**  
-  Handles imbalance using `scale_pos_weight`  

---

### 🔁 LSTM (Time-Series Model)

-  Designed for **sequential time-series data**  
-  Learns **temporal progression of patient health**  
-  Uses **padded patient sequences**  

---

## 📈 Results

| Model        | Accuracy | Precision (Sepsis) | Recall (Sepsis) | F1 Score | ROC-AUC |
|-------------|---------|--------------------|-----------------|----------|--------|
| 🌳 **XGBoost** | 87%     | 32%                | 72%             | 45%      | 🟢 **89.7%** |
| 🔁 **LSTM**    | 85%     | 30%                | 🔴 **74%**       | 43%      | 87.0% |

---

### 📉 AUC-ROC Curve (XGBoost)

📊 Demonstrates strong classification performance with high separability.
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/e9910d23-4714-4f93-aa33-dbda7cf523a4" />

---

### 📊 Confusion Matrix (LSTM)

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/f3e4e4e7-ec75-4abc-bb09-c73bb3462de7" />

🔍 Highlights improved **recall**, capturing more sepsis-positive cases.

---

## 💡 Key Insights

 🌳 **XGBoost** → Higher overall performance (**ROC-AUC ~89.7%**)  
 🔁 **LSTM** → Better **recall (74%)**, detects more sepsis cases  

⚖️ **Trade-off Observed:**
- 🔺 Higher recall → More false positives  
- 🔻 Higher precision → More missed cases  

🚑 In healthcare:  
👉 **Recall is critical** → Missing a sepsis case can be life-threatening  

---

## 🧾 Conclusion

- 🌳 **XGBoost** → Strong baseline for structured/tabular data  
- 🔁 **LSTM** → Captures temporal patterns & improves sensitivity  

---

## ⚙️ Tech Stack

-  Python  
-  Pandas, NumPy  
-  Scikit-learn  
-  XGBoost  
-  TensorFlow, Keras (LSTM)  
-  Matplotlib, Seaborn  

---

## 📂 Project Structure

```
Early_Sepsis_Prediction/
│
├── Notebooks/
│   └── Early_Sepsis_Prediction.ipynb
│
├── Results/
│   ├── LSTM_AUC-ROC_Curve.png
│   ├── LSTM_ConfusionMatrix.png
│   ├── XGBoost_AUC-ROC_curve.png
│   ├── XGBoost_ConfusionMatrix.png
│
├── .gitignore
├── README.md
├── requirements.txt
```

---


## 🚀 Key Takeaway

💡 Combining **Machine Learning + Deep Learning** enables:

- ⏱️ **Early detection of critical conditions**  
- 📊 **Data-driven healthcare decisions**  
- ❤️ **Improved patient survival and outcomes**
