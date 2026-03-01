###  Seller-Churn-Prediction
Predicting seller churn on an e-commerce platform

🛒 Seller Churn Prediction — E-Commerce Onboarding Analysis

Predicting which sellers are likely to churn during the onboarding journey on an e-commerce platform, using machine learning.

## ⚠️ Important Disclaimer

> This project uses 100% synthetic (artificially generated) data.
> No real company data, seller information, or proprietary records have been used.
> The dataset was generated programmatically to simulate realistic onboarding behavior patterns.
> Any resemblance to real individuals or businesses is purely coincidental.

---

## 📌 Business Context

In e-commerce platforms expanding into emerging markets, **seller acquisition is expensive**. The business generates revenue through seller commissions — meaning every seller who churns represents:

- 💸 Lost future commission revenue
- 📉 Wasted customer acquisition cost (CAC)
- 🏳️ Reduced market share in a competitive, emerging market

A **"zombie seller"** is defined as a seller who has been inactive for **90+ days** at any stage of the onboarding funnel without completing activation.

**The goal of this project** is to predict which sellers are at high risk of churning *before* they disengage — so the onboarding team can intervene early with targeted follow-ups.

---

## 🗺️ The Onboarding Funnel

Sellers go through the following steps before going live on the platform:

```
1️⃣  Company Details
        ↓
2️⃣  Logistics & Shipping Setup
        ↓
3️⃣  Trading License Upload
        ↓
4️⃣  Seller Agreement Signing
        ↓
5️⃣  First Product Upload → ✅ ACTIVATION
```

> Sellers who spend too long at any stage — especially the early ones — are significantly more likely to churn.

---

## 🎯 Project Objectives

- ✅ Identify key onboarding signals that predict seller churn
- ✅ Build a classification model to predict churn probability
- ✅ Compare churn behavior across two markets: **Saudi Arabia 🇸🇦 and UAE 🇦🇪**
- ✅ Evaluate model performance using **F1 Score, Precision, and Recall**
- ✅ Generate actionable insights for the onboarding team

---

## 📊 Dataset Overview

| Column | Description |
|---|---|
| `seller_id` | Unique seller identifier |
| `application_date` | Date the seller entered the system |
| `country` | Saudi Arabia or UAE |
| `days_to_complete_company_details` | Days spent on step 1 |
| `days_to_complete_logistics` | Days spent on step 2 |
| `days_to_upload_license` | Days spent on step 3 |
| `days_to_sign_agreement` | Days spent on step 4 |
| `reached_activation` | Whether seller activated (1 = yes, 0 = no) |
| `total_onboarding_days` | Total days from registration to last activity |
| `followup_count` | Number of follow-ups made by onboarding team |
| `days_since_last_followup` | Days since last contact from onboarding team |
| `churned` | 🎯 Target variable (1 = churned, 0 = active) |

---

## 🔧 Feature Engineering

New features derived from raw data to improve model performance:

| New Feature | How It Was Created | Why It Matters |
|---|---|---|
| `days_since_application` | Today's date − application date | Longer time = higher churn risk |
| `funnel_completion_rate` | Steps completed / total steps | Measures onboarding progress |
| `avg_days_per_step` | Total onboarding days / steps completed | Slow progress = churn signal |
| `followup_effectiveness` | Followup count / total onboarding days | Are follow-ups making a difference? |

---

## 🤖 Methodology

### 1️⃣ Data Generation
Synthetic data generated using Python's `numpy` and `pandas` to simulate realistic onboarding patterns.

### 2️⃣ Exploratory Data Analysis (EDA)
- Summary statistics
- Missing value analysis
- Churn rate by country
- Distribution of onboarding days

### 3️⃣ Data Preprocessing
- Encoding categorical variables (country → 0/1)
- Handling missing values
- Feature scaling using `StandardScaler`

### 4️⃣ Modeling
- **Baseline model:** Logistic Regression
- **Main model:** Random Forest Classifier
- Train/test split: 80/20

### 5️⃣ Evaluation
- Confusion Matrix
- Precision, Recall, F1 Score
- ROC-AUC Curve

---

## 📈 Results

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | TBD | TBD |
| Precision | TBD | TBD |
| Recall | TBD | TBD |
| **F1 Score** | TBD | **TBD** |

> Results will be updated after model training is complete.

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Scikit-Learn](https://img.shields.io/badge/ScikitLearn-1.3-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-yellow)

- **Python** — core programming language
- **pandas** — data manipulation and analysis
- **NumPy** — numerical computations
- **scikit-learn** — machine learning models and evaluation
- **matplotlib / seaborn** — data visualization
- **Jupyter Notebook** — development environment

---

## 📁 Project Structure

```
seller-churn-prediction/
│
├── 📓 notebook.ipynb          # Main Jupyter notebook
├── 📄 README.md               # Project documentation
├── 📊 data/
│   └── synthetic_sellers.csv  # Generated dataset
└── 📈 images/
    └── confusion_matrix.png   # Model evaluation visuals
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone [https://github.com/AHMEDMABROUK1111/seller-churn-prediction.git

# 2. Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn jupyter

# 3. Launch Jupyter Notebook
jupyter notebook notebook.ipynb
```

---

## 💡 Key Business Insights

- 🔴 Sellers who take **more than 30 days** on company details have significantly higher churn rates
- 🟡 Sellers who **never upload a product** churn at nearly 100%
- 🟢 Each additional **follow-up contact** reduces churn probability
- 🌍 Churn patterns differ between **Saudi Arabia and UAE** markets

---

## 👤 Author

**Ahmed Ismail** |
Data Scientist | E-Commerce Operations Specialist
[LinkedIn](https://www.linkedin.com/in/ahmed-ismail-b81471185/) • [GitHub](https://github.com/AHMEDMABROUK1111)

---

*This project was built as part of my data science portfolio to demonstrate end-to-end ML skills including data generation, feature engineering, classification modeling, and business insight generation.*
