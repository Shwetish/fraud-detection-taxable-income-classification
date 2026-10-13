# Financial Fraud Detection & Taxable Income Classification
Classifying financial fraud risk (Risky vs Good) based on taxable income using Decision Tree and Random Forest classifiers.

## 1. Business Problem
### 1.1. What is the business objective?
The objective is to identify financial fraud risk by classifying individuals as 'Risky' or 'Good' based on their taxable income and demographic/financial attributes. Taxable income is discretized (`<= 30000` as 'Risky', others as 'Good') to build an effective binary classification model.
### 1.2. Are there any constraints?
* Handling class imbalance (typically, fraudulent or risky cases are rarer than good cases).
* High cost of false negatives (failing to catch a risky profile) versus false positives.

---

## 2. Data Dictionary
| Feature Name | Data Type | Relevance to Model Building | Description & Reason for Inclusion/Exclusion |
| :--- | :--- | :--- | :--- |
| `Undergrad` | Categorical (Binary) | Relevant | Whether the individual has an undergraduate degree or not. |
| `Marital.Status` | Categorical | Relevant | Marital status (Single, Married, Divorced), influencing tax brackets/filing. |
| `Taxable.Income` | Numerical (Int) | **Source for Target** | Taxable income in local currency; discretized into the binary target variable. |
| `City.Population` | Numerical (Int) | Relevant | Population size of the city where the individual resides. |
| `Work.Experience` | Numerical (Int) | Relevant | Number of years of work experience. |
| `Urban` | Categorical (Binary) | Relevant | Whether the individual resides in an urban or rural setting. |
| `Risk_Category` | Categorical (Binary) | **Target Variable** | Discretized target ('Risky' if Taxable.Income $\le$ 30000, else 'Good'). |

---

## 3. Exploratory Data Analysis (EDA)
* **3.1 Summary:** Overview of demographic distributions, work experience ranges, and population statistics.
* **3.2 Univariate Analysis:** Frequency counts of marital status, urban distribution, and income histograms.
* **3.3 Bivariate Analysis:** Analyzing relationship between work experience, marital status, and fraud risk categories.

---

## 4. Data Pre-processing
* **4.1 Data Cleaning & Feature Engineering:** Discretized `Taxable.Income` into `Risk_Category`. Encoded categorical features (`Undergrad`, `Marital.Status`, `Urban`) using one-hot encoding.

---

## 5. Model Building
* **5.1 Feature Scaling:** Scaled numerical predictors to ensure balanced feature contribution.
* **5.2 Algorithm Application:** Trained **Decision Tree** and **Random Forest** models to classify taxpayer risk.
* **5.3 Training, Testing & Cross-Validation:** Split data into train/test sets, implemented stratified cross-validation, and compared performance metrics (Precision, Recall, F1-score).
* **5.4 Model Output Explanation:** Interpreted tree split rules and Gini impurity reduction to understand key triggers for 'Risky' classifications.

---

## 6. Business Benefits & Impact
* Empowers financial auditors and tax authorities to target high-risk audits efficiently.
* Minimizes revenue loss from fraudulent or underreported tax filings.
