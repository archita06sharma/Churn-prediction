# 📊 Customer Churn Prediction using Machine Learning

This project builds a **machine learning model to predict customer churn** using the **Telco Customer Churn dataset**.
The goal is to analyze customer behavior and identify factors that lead customers to leave a telecom service.

Predicting churn helps companies **retain customers, reduce revenue loss, and improve customer satisfaction**.

---

# 🚀 Project Overview

Customer churn prediction is a **binary classification problem** where the model predicts whether a customer will:

* **Stay with the company (0)**
* **Leave the company (1)**

This project includes:

* Data cleaning and preprocessing
* Feature engineering
* Exploratory data analysis (EDA)
* Model comparison
* Hyperparameter tuning
* Model evaluation and interpretation

---

# 📂 Dataset

Dataset used: **Telco Customer Churn Dataset**

Total Records: **7043 customers**
Total Features: **21 original features**

### Key Features

* `tenure` – Number of months the customer has stayed
* `MonthlyCharges` – Monthly billing amount
* `TotalCharges` – Total amount charged
* `Contract` – Type of contract
* `InternetService` – Internet service provider
* `OnlineSecurity`, `TechSupport`, etc.
* `Churn` – Target variable (Yes/No)

---

# ⚙️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Missingno
* Scikit-learn

---

# 🧹 Data Preprocessing

Steps performed:

1. **Handled Missing Values**

   * Converted empty strings to `NaN`
   * Replaced missing `TotalCharges` values with median

2. **Converted Data Types**

   * `TotalCharges` converted to numeric

3. **Encoded Target Variable**

```
Yes → 1
No → 0
```

4. **Dropped unnecessary column**

```
customerID
```

---

# 🔧 Feature Engineering

New features were created to improve model performance:

### Tenure Group

Customers grouped by subscription duration.

```
0–1 year
1–2 years
2–4 years
4–5 years
5+ years
```

### Average Monthly Spend

```
AvgMonthlySpend = TotalCharges / (tenure + 1)
```

### Service Count

Counts how many services a customer uses.

### Support Tickets

Simulated number of support requests using Poisson distribution.

### High Complaint Flag

Indicates customers with many support tickets.

---

# 📊 Exploratory Data Analysis

The following visualizations were created:

* Distribution of **Tenure**
* Distribution of **Monthly Charges**
* Distribution of **Total Charges**
* **Churn Count Plot**
* **Boxplots** for churn vs key features
* **Correlation Heatmap**

These helped identify patterns related to churn.

---

# 🔄 Data Processing

Categorical variables were converted to numerical values using **Label Encoding**.

Dataset split:

```
Training Data : 80%
Testing Data  : 20%
```

Using stratified sampling to maintain churn distribution.

---

# 🤖 Machine Learning Models

Three models were evaluated:

| Model               | Accuracy  |
| ------------------- | --------- |
| Logistic Regression | **0.815** |
| Random Forest       | 0.793     |
| Decision Tree       | 0.736     |

Logistic Regression performed best initially.

However, **Random Forest was further optimized** due to its strong ability to capture complex relationships.

---

# 🌲 Random Forest Model

Random Forest was trained with parameters:

```
n_estimators = 500
max_depth = 10
class_weight = balanced
```

Evaluation metrics:

Accuracy: **0.79**

Confusion Matrix:

```
TN = 850
FP = 185
FN = 108
TP = 266
```

ROC-AUC Score:

**0.85**

---

# 📈 Feature Importance

Top factors affecting churn:

1️⃣ Contract Type
2️⃣ Monthly Charges
3️⃣ Total Charges
4️⃣ Average Monthly Spend
5️⃣ Tenure
6️⃣ Online Security
7️⃣ Tech Support
8️⃣ Payment Method

Customers with **short contracts, higher monthly charges, and fewer services** are more likely to churn.

---

# 🔍 Model Calibration

A **calibration curve** was plotted to compare predicted probabilities with actual outcomes.

This helps evaluate whether predicted churn probabilities are reliable.

---

# 🧪 Live Prediction Example

The trained model can predict churn for a new customer:

```
Prediction: Customer will NOT Churn
Churn Probability: 0.15%
```

---

# ⚡ Hyperparameter Tuning

Random Forest was optimized using **GridSearchCV**.

Best parameters:

```
max_depth = 10
min_samples_split = 5
n_estimators = 200
```

Final model accuracy remained around **79%**, but recall for churn customers improved.

---

# 📌 Key Insights

* Customers with **month-to-month contracts churn more frequently**
* **Higher monthly charges increase churn risk**
* Customers using **security and support services churn less**
* **Long tenure strongly reduces churn probability**

---

# 📁 Project Structure

```
Customer-Churn-Prediction
│
├── churn_prediction.ipynb
├── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── README.md
└── images/
```

---

# 📊 Future Improvements

Possible enhancements:

* Try **XGBoost or LightGBM**
* Add **SMOTE for class imbalance**
* Build a **customer churn dashboard**
* Deploy model using **Streamlit**

---

# 👩‍💻 Author

Archita Sharma

---

⭐ If you found this project useful, consider giving the repository a **star on GitHub**.
