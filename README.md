# 📊 Insurance Fraud Detection System

> End-to-end machine learning system achieving **94% accuracy** in detecting fraudulent insurance claims using Python, scikit-learn, and Streamlit.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit)](https://isshasfrauddetectionapp.streamlit.app/)
[![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python)](https://www.python.org/)


---

## 👩‍💻 Built By
**Issha Sethi** — Senior Configuration Analyst | Data Analytics Enthusiast

---

## 📌 Table of Contents
- [Problem Statement](#-problem-statement)
- [Solution Overview](#-solution-overview)
- [Key Results](#-key-results)
- [Tech Stack](#%EF%B8%8F-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [Model Performance](#-model-performance)
- [Screenshots](#-screenshots)
- [Business Impact](#-business-impact)
- [Future Enhancements](#-future-enhancements)
- [Contact](#-contact)

---

## 🎯 Problem Statement

Insurance companies lose **billions annually** to fraudulent claims. Traditional manual review processes are:

| Problem | Impact |
|---------|--------|
| 🐢 **Slow** | 2-3 days per claim review |
| 💸 **Expensive** | ₹500+ per manual review |
| ⚠️ **Inconsistent** | Human bias and error-prone decisions |
| 📈 **Unscalable** | Cannot handle 10,000+ daily claims |

**Core Business Question:**  
*Can we automate fraud detection to reduce financial losses while simultaneously speeding up legitimate claim processing?*

---

## 💡 Solution Overview

Built an **end-to-end ML pipeline** that:

✅ Analyzes **15+ claim features** — amount, vehicle age, incident time, witnesses, repair shop, policy tenure, and more  
✅ Predicts fraud risk in **real-time** (2 seconds vs 2-3 days manually)  
✅ Achieves **94% accuracy** with **91% recall** — catches 9 out of 10 fraudulent claims  
✅ Deployed as an **interactive Streamlit web app** accessible to all stakeholders  

---

## 🏆 Key Results

| Metric | Value | Business Impact |
|--------|-------|----------------|
| **Accuracy** | 94.2% | High overall correctness |
| **Precision** | 89.7% | Low false alarms — reduced investigation waste |
| **Recall** | 91.3% | Catches 91% of actual fraud cases |
| **F1-Score** | 90.5% | Balanced performance across classes |
| **Processing Time** | 2 seconds | 99.9% faster than manual review |
| **Estimated Cost Savings** | ₹7-10 Cr/year | For a mid-sized insurer with 50K claims/year |

---

## 🛠️ Tech Stack

### **Data Processing & Analysis**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

### **Machine Learning**
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Random Forest](https://img.shields.io/badge/Algorithm-Random%20Forest-green)

### **Visualization & Deployment**
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat)

### **Development Tools**
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Anaconda](https://img.shields.io/badge/Anaconda-44A833?style=flat&logo=anaconda&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

---

## 📁 Project Structure
Insurance-Fraud-Detection/
│
├── app/
│ └── streamlitapp.py # Streamlit web application
│
├── data/
│ └── insurance_claim.csv # Dataset (50,000+ claims)
│
├── models/
│ ├── random_forest_model.pkl # Trained Random Forest model
│ ├── scalar.pkl # Feature scaler
│ ├── label_encoders.pkl # Categorical encoders
│ └── feature_name.pkl # Feature names
│
├── notebooks/
│ └── Insurance_Fraud_Detection.ipynb # Full EDA + model training
│
├── screenshots/
│ ├── app_demo_main.png # Streamlit app main page
│ └── app_prediction_result.png # Prediction result screenshot
│
├── .gitignore # Git ignore file
├── LICENSE # MIT License
├── README.md # This file
└── requirements.txt # Python dependencies


---

## 🚀 Installation

### **Prerequisites**
- Python 3.8 or higher
- Anaconda (recommended) or pip

### **Step 1: Clone Repository**
```bash
git clone https://github.com/Issha111/Insurance-Fraud-Detection.git
cd Insurance-Fraud-Detection
```

### **Step 2: Create Environment (Anaconda)**
```bash
conda create -n fraud-detection python=3.8
conda activate fraud-detection
```

**Or using venv:**
```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

### **Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

### **Step 4: Run Application**
```bash
streamlit run app/streamlitapp.py
```

**App will open at:** `http://localhost:8501`

---

## 💻 Usage

### **1. Interactive Web App (Recommended)**
```bash
streamlit run app/streamlitapp.py
```

1. Enter claim details — amount, vehicle age, incident time, etc.
2. Click **"Analyze Claim"** or **"Predict"**
3. Get instant fraud risk prediction with probability score

### **2. Run the Jupyter Notebook**
Open `notebooks/Insurance_Fraud_Detection.ipynb` to explore:
- Data loading & exploration (EDA)
- Data cleaning & preprocessing
- Feature engineering
- Model training (Random Forest, Logistic Regression)
- Performance evaluation
- Model saving with joblib

### **3. Use Model Directly in Python**
```python
import joblib
import pandas as pd

# Load trained model
model = joblib.load('models/random_forest_model.pkl')
scaler = joblib.load('models/scalar.pkl')

# Prepare claim data
claim_data = pd.DataFrame([[25000, 3, 14, 2, ...]])  # Your features
claim_scaled = scaler.transform(claim_data)

# Predict
prediction = model.predict(claim_scaled)
probability = model.predict_proba(claim_scaled)

print(f"Fraud Prediction: {prediction}")
print(f"Fraud Probability: {probability:.2%}")[1]
```

---

## 📊 Model Performance

### **Classification Metrics**
precision recall f1-score support

Legitimate 0.96 0.93 0.94 8547
Fraudulent 0.90 0.91 0.91 1453

accuracy 0.94 10000
macro avg 0.93 0.92 0.92 10000
weighted avg 0.94 0.94 0.94 10000


### **Top 10 Fraud Indicators (Feature Importance)**

| Rank | Feature | Importance | Insight |
|------|---------|-----------|---------|
| 1 | **Claim Amount** | 23.4% | High-value claims most suspicious |
| 2 | **Vehicle Age** | 18.7% | New cars with total loss = red flag |
| 3 | **Incident Hour** | 12.3% | Midnight accidents = higher risk |
| 4 | **Number of Witnesses** | 9.8% | Zero witnesses = suspicious |
| 5 | **Repair Shop** | 8.2% | Unknown shops = higher fraud rate |
| 6 | **Policy Tenure** | 7.5% | New policies claiming quickly |
| 7 | **Previous Claims** | 6.9% | Frequent claimers flagged |
| 8 | **Driver Age** | 5.4% | Certain age brackets higher risk |
| 9 | **Vehicle Category** | 4.2% | Luxury vehicles pattern |
| 10 | **Incident Type** | 3.6% | Certain incident types flagged |

---

## 📷 Screenshots

### **Streamlit Web App - Main Interface**
![App Demo](screenshots/app_demo_main.png)

### **Fraud Prediction Result**
![Prediction Result](screenshots/app_prediction_result.png)

---

## 💼 Business Impact

### **Operational Transformation**

| Metric | Before ML | After ML | Improvement |
|--------|-----------|----------|------------|
| **Review Time** | 2-3 days | 2 seconds | 99.9% faster |
| **Fraud Detection Rate** | 70-80% | 91.3% | +15-20% |
| **Cost Per Review** | ₹500+ | Near zero | ~100% savings |
| **Daily Capacity** | ~500 claims | Millions | Unlimited scale |
| **Human Bias** | High | Eliminated | Consistent |

### **Cost Savings Calculation**

Mid-sized insurer processing 50,000 claims/year:

Manual Review Cost:
50,000 claims × ₹500/review = ₹2.5 Cr/year

ML System Cost:
Setup: ₹5 lakh (one-time)
Maintenance: ₹20 lakh/year

Annual Savings = ₹2.5 Cr - ₹20 lakh = ₹2.3 Cr/year

ROI = 460% in Year 1


---

## 🔮 Future Enhancements

- [ ] **Deep Learning** — LSTM/Neural networks for time-series fraud patterns
- [ ] **Explainable AI** — SHAP values for individual claim-level explanations
- [ ] **REST API** — Flask/FastAPI integration for production systems
- [ ] **Ensemble Models** — Random Forest + XGBoost + LightGBM stacking
- [ ] **Fraud Network Detection** — Graph analysis for organized fraud rings
- [ ] **Auto-retraining Pipeline** — Monthly model updates on new fraud patterns
- [ ] **Power BI Dashboard** — Business-facing reporting layer

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📧 Contact

**Issha Sethi** — Data Analyst | Insurance Domain | ML Enthusiast

| Platform | Link |
|----------|------|
| 💼 **LinkedIn** | [linkedin.com/in/issha-sethi-744734170](https://www.linkedin.com/in/issha-sethi-744734170/) |
| 🐙 **GitHub** | [@Issha111](https://github.com/Issha111) |
| 🌐 **Portfolio** | [datascienceportfol.io/issha](https://www.datascienceportfol.io/) |
| 📧 **Email** | issha.career@gmail.com |


---

## 🙏 Acknowledgments

- **Dataset:** Kaggle Insurance Fraud Detection
- **ML Framework:** scikit-learn community
- **Deployment:** Streamlit team
- **Inspiration:** Real-world insurance fraud patterns and business challenges

---

<div align="center">

### ⭐ If this project helped you, please give it a star! ⭐

**Built with ❤️ by Issha Sethi**  
*Senior Configuration Analyst → Data Analyst | Building in public*

*Last Updated: April 2026*

</div>


