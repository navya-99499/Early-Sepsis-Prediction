#  Early Sepsis Prediction using Machine Learning & Deep Learning

Predicting sepsis early in ICU patients is critical, as delayed detection can lead to severe complications and increased mortality.  
This project develops and compares **Machine Learning (XGBoost)** and **Deep Learning (LSTM)** models to enable **early and accurate sepsis detection**.

---

##  Problem Statement

Sepsis is a **life-threatening condition** caused by the body’s extreme response to infection.  
Traditional detection methods often identify sepsis **too late**, reducing treatment effectiveness.

 **Goal:**  
Predict whether a patient will develop sepsis **hours in advance**, enabling timely medical intervention.

---

##  Dataset

- **Source:** PhysioNet Challenge 2019 (ICU patient data)  
- **Data Type:** Multivariate time-series  

**Features include:**
- **Vital signs:** HR, BP, Temp, Respiration  
- **Laboratory measurements:** WBC, Creatinine, Glucose, etc.  
- **ICU stay information:** ICULOS  

---

##  Data Preprocessing

- Handled missing values using:
  - **Forward Fill (FFill)**
  - **Backward Fill (BFill)**
  - **Median Imputation**
- Reconstructed **continuous hourly patient timelines**
- Normalized features using **MinMaxScaler**

 Created:
- **Tabular features (for XGBoost)**
- **Sequential patient data (for LSTM)**

---

##  Models Implemented

###  XGBoost (Tabular Model)

- Captures **non-linear relationships**
- Works on **engineered tabular features**
- Handles imbalanced data using `scale_pos_weight`

---

###  LSTM (Time-Series Model)

- Designed for **time-series data**
- Learns **temporal progression of patient health**
- Uses **padded patient sequences**

---

##  Results

| Model   | Accuracy | Precision (Sepsis) | Recall (Sepsis) | F1 Score | ROC-AUC |
|--------|----------|-------------------|-----------------|----------|--------|
| **XGBoost** | 87% | 32% | 72% | 45% | **89.7%** |
| **LSTM**    | 85% | 30% | **74%** | 43% | 87.0% |

### AUC - ROC Curve for XGBOOST Model:

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/9a7a6272-5238-467a-88cd-7e075965013b" />

### CONFUSION MATRIX for LSTM Model:

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/584d43b2-280a-4e08-af48-115e0b0c5448" />



---

##  Key Insights

- **XGBoost** achieved higher overall performance (**ROC-AUC ~89.7%**)  
- **LSTM** improved **recall**, detecting more sepsis cases  
- Trade-off observed:
  - Higher recall → **more false positives**
  - Higher precision → **more missed cases**

 In healthcare, **recall is critical**, as missing a sepsis case can be life-threatening.

---

##  Conclusion

- **XGBoost → strong baseline for tabular data**  
- **LSTM → better temporal learning & sensitivity**  

 Combining both approaches provides a **robust and clinically meaningful solution**


---

##  Tech Stack

- **Python**
- **Pandas, NumPy**
- **Scikit-learn**
- **XGBoost**
- **TensorFlow, Keras (LSTM)**
- **Matplotlib, Seaborn**

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

##  Key Takeaway

Combining **machine learning + deep learning** enables **early, data-driven healthcare decisions**, improving patient outcomes.
