# 🧠 Derivable Judgement: Statistical Analysis & Hypothesis Testing on Healthcare Data

A complete **Theory + Practical Statistics Project** that applies inferential statistical techniques to a real-world healthcare dataset containing **500 patient records**.

The project explores key concepts of **Hypothesis Testing, Confidence Intervals, Chi-Square Test, ANOVA, t-Test, Correlation Analysis, Covariance Analysis, Critical Values, and p-value Interpretation** to derive meaningful conclusions from health-related data.

All statistical analyses are implemented using **Python (Jupyter Notebook)** and supported with detailed interpretations, visual outputs, and business-style conclusions.

---

# 📋 Project Details

| Field      | Details                                                      |
| ---------- | ------------------------------------------------------------ |
| Title      | Derivable Judgement: Statistical Analysis of Healthcare Data |
| Duration   | 4–6 Hours                                                    |
| Type       | Theory + Practical                                           |
| Domain     | Statistics & Healthcare Analytics                            |
| Tools Used | Python · Excel · Jupyter Notebook                            |
| Libraries  | Pandas · NumPy · SciPy · Matplotlib                          |

---

# 🎯 Objective

Imagine you are working as a **Healthcare Data Analyst** for a medical research organization.

Your task is to analyze patient health records and apply statistical techniques to answer important questions such as:

* Does smoking influence diabetes prevalence?
* Does exercise frequency affect BMI?
* Are male and female BMI levels significantly different?
* Do age groups show different disease rates?
* Is there a relationship between age and BMI?

The project demonstrates how statistical methods can transform raw healthcare data into meaningful insights for decision-making.

---

# 📂 Project Structure

```text
Derivable-Judgement/
│
├── 📓 Derivable_Judgement.ipynb
├── 📊 health_records_dataset_500.xlsx
├── 📄 Statistical_Insights_Report.docx
├── 📷 images/
├── 📄 README.md
│
└── requirements.txt
```

---

# 🗂️ Dataset Information

### Dataset Size

* 500 Patient Records
* Healthcare-based synthetic dataset

### Dataset Columns

| Column Name        | Description                     |
| ------------------ | ------------------------------- |
| Patient_ID         | Unique Identifier               |
| Age                | Patient Age                     |
| Gender             | Male / Female                   |
| Weight             | Weight (kg)                     |
| BMI                | Body Mass Index                 |
| Blood_Pressure     | Blood Pressure Reading          |
| Smoking_Status     | Smoking Habit                   |
| Exercise_Frequency | Daily / Weekly / Rarely / Never |
| Diabetes           | Yes / No                        |
| Cholesterol        | Cholesterol Level               |

---

# 🛠️ Technologies Used

## Python Libraries

```python
import pandas as pd
import numpy as np

from scipy.stats import (
    chi2_contingency,
    chi2,
    t,
    f
)

import matplotlib.pyplot as plt
```

---

# 📚 Statistical Concepts Covered

## 1️⃣ Hypothesis Testing

Formulated and tested statistical hypotheses.

### Example

### H₀ (Null Hypothesis)

Smoking status has no effect on diabetes prevalence.

### H₁ (Alternative Hypothesis)

Smoking status affects diabetes prevalence.

### Python Code

```python
table = pd.crosstab(
    df["smoking_status"],
    df["diabetes"]
)

chi2_stat, p_value, dof, expected = chi2_contingency(table)

print("Chi Square:", chi2_stat)
print("P Value:", p_value)
```

### Result

| Metric     | Value |
| ---------- | ----- |
| Chi-Square | 0.71  |
| p-value    | 0.701 |

### Insight

Smoking status and diabetes prevalence were found to be statistically independent in this dataset.

---

# 2️⃣ Confidence Intervals

Calculated confidence intervals for:

* Age
* Weight
* Blood Pressure

### Formula

[
CI = \bar{x} \pm z \left( \frac{\sigma}{\sqrt{n}} \right)
]

### Python Code

```python
mean_age = df["age"].mean()

std_age = df["age"].std()

n = len(df)

margin_error = 1.96 * (std_age / np.sqrt(n))

lower = mean_age - margin_error
upper = mean_age + margin_error
```

### Insight

95% confidence intervals provide reliable estimates of population characteristics.

---

# 3️⃣ Critical Value & p-value Analysis

Compared:

* Test Statistic
* Critical Value
* p-value

### Decision Rule

```text
If p-value < 0.05
Reject H₀

Else
Accept H₀
```

### Insight

Critical value and p-value approaches lead to the same statistical conclusion.

---

# 4️⃣ Independent Sample t-Test

Compared BMI between:

* Male Patients
* Female Patients

### Formula

[
t =
\frac{\bar{x}_1-\bar{x}_2}
{\sqrt{\frac{s_1^2}{n_1}+\frac{s_2^2}{n_2}}}
]

### Python Code

```python
from scipy.stats import ttest_ind

male = df[df["gender"]=="Male"]["bmi"]
female = df[df["gender"]=="Female"]["bmi"]

t_stat,p = ttest_ind(male,female)

print(t_stat,p)
```

### Result

| Metric  | Value |
| ------- | ----- |
| t-value | 1.67  |
| p-value | 0.095 |

### Insight

BMI differences between males and females were not statistically significant.

---

# 5️⃣ Chi-Square Test of Independence

Analyzed relationship between:

* Smoking Habit
* Diabetes Status

### Formula

[
\chi^2=
\sum
\frac{(O-E)^2}{E}
]

### Python Code

```python
table = pd.crosstab(
    df["smoking_status"],
    df["diabetes"]
)

chi2_stat,p,dof,expected = chi2_contingency(table)
```

### Conclusion

Smoking habit and diabetes occurrence appear statistically independent.

---

# 6️⃣ ANOVA Test

Compared BMI across:

* Daily Exercise
* Weekly Exercise
* Rarely Exercise
* Never Exercise

### Formula

[
F=
\frac{\text{Between Group Variance}}
{\text{Within Group Variance}}
]

### Python Code

```python
from scipy.stats import f_oneway

daily = df[df["exercise_frequency"]=="Daily"]["bmi"]
weekly = df[df["exercise_frequency"]=="Weekly"]["bmi"]
rarely = df[df["exercise_frequency"]=="Rarely"]["bmi"]
never = df[df["exercise_frequency"]=="Never"]["bmi"]

F,p = f_oneway(
    daily,
    weekly,
    rarely,
    never
)

print(F,p)
```

### Result

| Metric  | Value |
| ------- | ----- |
| F-value | 0.87  |
| p-value | 0.458 |

### Insight

Exercise frequency did not significantly influence BMI in the dataset.

---

# 7️⃣ Age Group Disease Analysis

Investigated whether disease prevalence changes significantly across age groups.

### Method

ANOVA on age-group disease rates.

### Result

| Metric  | Value |
| ------- | ----- |
| F-value | 1.50  |
| p-value | 0.201 |

### Insight

Disease prevalence remains relatively consistent across age categories.

---

# 8️⃣ Correlation & Covariance Analysis

Studied relationship between:

* Age
* BMI

### Correlation Formula

[
r=
\frac{Cov(X,Y)}
{\sigma_x \sigma_y}
]

### Python Code

```python
correlation = df["age"].corr(df["bmi"])

covariance = df["age"].cov(df["bmi"])

print(correlation)
print(covariance)
```

### Result

| Metric          | Value              |
| --------------- | ------------------ |
| Correlation (r) | 0.109              |
| Relationship    | Very Weak Positive |

### Insight

Age shows almost no meaningful relationship with BMI.

---

# 📊 Key Findings

✔️ Smoking status showed no significant association with diabetes.

✔️ Exercise frequency did not significantly affect BMI.

✔️ Male and female BMI values were statistically similar.

✔️ Age groups did not significantly differ in disease prevalence.

✔️ Confidence intervals provided reliable estimates of population characteristics.

✔️ Correlation between Age and BMI was extremely weak.

✔️ Hypothesis testing confirmed multiple healthcare assumptions using statistical evidence.

✔️ p-value interpretation played a central role in decision making.

---

# 📈 Sample Statistical Workflow

```python
alpha = 0.05

if p_value < alpha:
    print("Reject H0")
else:
    print("Accept H0")
```

---

# 🚀 How to Run

### Clone Repository

```bash
git clone https://github.com/yourusername/Derivable-Judgement.git
```

### Install Dependencies

```bash
pip install pandas numpy scipy matplotlib openpyxl
```

### Run Notebook

```bash
jupyter notebook
```

Open:

```text
Derivable_Judgement.ipynb
```

Run all cells sequentially.

---

# 🌟 Future Enhancements

* Add Data Visualization Dashboard
* Implement Logistic Regression
* Perform Multiple Linear Regression
* Add Machine Learning Predictions
* Include Power Analysis
* Create Interactive Streamlit Application
* Expand Dataset Beyond 1000 Records
* Add Advanced Statistical Modeling

---

# ✅ Submission Checklist

✔️ Hypothesis Testing

✔️ Confidence Interval Analysis

✔️ Critical Value Interpretation

✔️ p-value Analysis

✔️ Chi-Square Test

✔️ Independent t-Test

✔️ ANOVA Test

✔️ Correlation Analysis

✔️ Covariance Analysis

✔️ Statistical Conclusions

✔️ Dataset Included

✔️ Jupyter Notebook Included

✔️ README Documentation Included

---

# 👩‍💻 Shruti Bhawsar

📍 Ahmedabad, Gujarat, India

### Statistical Thinking • Data-Driven Decisions • Evidence-Based Conclusions

⭐ If you found this project useful, consider giving it a star and contributing to future improvements.
