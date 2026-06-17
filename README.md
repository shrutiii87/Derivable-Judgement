<div align="center"> <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=180&section=header&text=Derivable%20Judgement&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=32&desc=Statistics%20Analysis%20%7C%20BI%20Hypothesis%20%7C%20Testing%20on Health care data&descAlignY=55&descSize=18" /> </div>


# 📊 Derivable Judgement: Statistical Analysis & Hypothesis Testing on Healthcare Data

A complete **Theory + Practical Statistics Project** that applies **Inferential Statistics** and **Hypothesis Testing** techniques to a real-world healthcare dataset containing **500 patient records**.

The project explores statistical concepts including **Hypothesis Testing, Confidence Intervals, Critical Values, p-values, Independent Sample t-Test, Chi-Square Test, ANOVA, Correlation Analysis, and Covariance Analysis** to derive meaningful insights from healthcare data.

The entire analysis is implemented using **Python (Jupyter Notebook)** and supported with detailed interpretations, statistical calculations, visualizations, and evidence-based conclusions.


---

# 🎯 Objective

<img width="1024" height="576" alt="WhatsApp Image 2026-06-17 at 10 23 40 AM" src="https://github.com/user-attachments/assets/75255168-e907-417a-9021-aaa366055640" />

---

# 🗂️ Project Files

| File | Description |
|---------|---------|
| 📓 Derivable_Judgement.ipynb | Complete statistical analysis notebook |
| 📊 health_records_dataset_500.xlsx | Healthcare dataset containing 500 records |
| 📄 Derivable_Judgement_Theory.pdf | Theoretical explanations and formulas |
| 📄 Statistical_Insights_Report.docx | Detailed project interpretations |
| 📘 README.md | Project documentation |

---

# 🛠️ Tools Used

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![Statistics](https://img.shields.io/badge/Statistics-FF6B6B?style=for-the-badge)
![Hypothesis_Testing](https://img.shields.io/badge/Hypothesis_Testing-6A5ACD?style=for-the-badge)
![ANOVA](https://img.shields.io/badge/ANOVA-FF9800?style=for-the-badge)
![Chi_Square](https://img.shields.io/badge/Chi--Square_Test-4CAF50?style=for-the-badge)
![T_Test](https://img.shields.io/badge/T--Test-009688?style=for-the-badge)
![Correlation](https://img.shields.io/badge/Correlation_Analysis-E91E63?style=for-the-badge)

---

# 🎬 Project Demo

[![Watch Demo](https://img.shields.io/badge/▶️%20Watch%20Demo-Google%20Drive-blue?style=for-the-badge&logo=google-drive)](YOUR_LINK_HERE)

📹 Click the badge above to watch the complete project demonstration.

---

# Diagrams (PART :- A) Theory


## Q1. What is inferential statistics?
   
   <img width="400" height="300" alt="— Q1" src="https://github.com/user-attachments/assets/ba95dc0d-4660-4429-ba28-4e3f16b9ef12" />

## Q2. What is hypothesis testing and its components?

  <img width="400" height="300" alt="Q2" src="https://github.com/user-attachments/assets/dfb6f334-b4d1-4df2-b879-dd5a21c5e326" />
  
 ## Q3. Explain confidence interval and critical value.
  
   <img width="400" height="330" alt="Q3" src="https://github.com/user-attachments/assets/cfc34ac7-2fbd-4057-80be-b708ae1c9aa7" />

 ## Q4. Define p-value.

   <img width="400" height="300" alt="Q4" src="https://github.com/user-attachments/assets/5cbbbe69-ad99-4646-9e90-34e77e3b0b37" />

 ## Q5. Differentiate Type I and Type II errors.

   <img width="400" height="300" alt="Q5" src="https://github.com/user-attachments/assets/eb252f7f-186e-49db-b70e-29c159e61557" />


 ## Q6. Brief descriptions of z-test, t-test, chi-square test, and ANOVA test.

   <img width="430" height="300" alt="Q6" src="https://github.com/user-attachments/assets/96028120-3a79-41c6-9fcd-8ada1666d09e" />


 ## Q7. What is Covariance?

   <img width="400" height="300" alt="Q7" src="https://github.com/user-attachments/assets/be06dded-dfa6-4a83-9d8b-75164021e158" />


 ## Q8. What is Correlation?

   <img width="400" height="300" alt="Q8" src="https://github.com/user-attachments/assets/34855111-07ce-4f1f-8ba2-d9c02df78d5f" />

---

# 📗 Statistical Topics Covered

---

## 🔬 Q1 — Hypothesis Testing

### Research Question

Does smoking status influence diabetes prevalence?

### Hypotheses

**H₀:** Smoking has no effect on diabetes prevalence.

**H₁:** Smoking affects diabetes prevalence.

### Python Code

```python
table = pd.crosstab(
    df["Smoking_Status"],
    df["Diabetes"]
)

chi2_stat, p_value, dof, expected = chi2_contingency(table)

print("Chi-Square =", chi2_stat)
print("P-Value =", p_value)
```

### Results

| Metric | Value |
|----------|----------|
| Chi-Square Statistic | 0.71 |
| p-value | 0.701 |
| Critical Value | 5.99 |

📌 **Interpretation:** The p-value is much greater than 0.05 and the test statistic is below the critical value.

📌 **Conclusion:** Smoking status and diabetes prevalence are statistically independent.

---

## 📊 Q2 — Confidence Interval Analysis

### Formula

\[
CI = \bar{x} \pm Z \times \frac{\sigma}{\sqrt{n}}
\]

### Results

| Variable | 95% Confidence Interval |
|----------|------------------------|
| Age | 47.24 – 50.48 |
| Weight | 79.42 – 83.37 |
| Blood Pressure | 135.42 – 139.56 |

### Python Code

```python
mean_age = df["Age"].mean()

std_age = df["Age"].std()

n = len(df)

margin = 1.96 * (std_age / np.sqrt(n))

lower = mean_age - margin
upper = mean_age + margin
```

📌 **Interpretation:** The intervals provide a likely range for the true population means.

📌 **Conclusion:** Population estimates are reliable and precise.

---

## 📈 Q3 — Critical Value & p-value

### Decision Rule

```text
If p-value < 0.05 → Reject H₀

If p-value ≥ 0.05 → Fail to Reject H₀
```

### Interpretation

Both critical value and p-value approaches produced the same statistical decision.

### Conclusion

Statistical significance decisions remain consistent regardless of approach.

---

## 👨‍⚕️ Q4 — Independent Sample t-Test

### Objective

Compare BMI between male and female patients.

### Formula

\[
t =
\frac{\bar{x}_1-\bar{x}_2}
{\sqrt{\frac{s_1^2}{n_1}+\frac{s_2^2}{n_2}}}
\]

### Results

| Metric | Value |
|----------|----------|
| t-value | 1.67 |
| p-value | 0.095 |
| Critical Value | 1.97 |

### Python Code

```python
from scipy.stats import ttest_ind

male = df[df["Gender"]=="Male"]["BMI"]
female = df[df["Gender"]=="Female"]["BMI"]

t_stat,p = ttest_ind(male,female)

print(t_stat,p)
```

📌 **Interpretation:** Although males show a slightly higher BMI, the difference is not statistically significant.

📌 **Conclusion:** Male and female BMI distributions are statistically similar.

---

## 🔗 Q5 — Chi-Square Test

### Objective

Determine whether smoking status and diabetes are related.

### Formula

\[
\chi^2=
\sum
\frac{(O-E)^2}{E}
\]

### Results

| Metric | Value |
|----------|----------|
| Chi-Square | 0.71 |
| p-value | 0.701 |

📌 **Interpretation:** Observed differences are likely due to random variation.

📌 **Conclusion:** No significant association exists between smoking status and diabetes prevalence.

---

## 📊 Q6 — ANOVA Test

### Objective

Compare BMI among exercise groups.

### Groups

- Daily
- Weekly
- Rarely
- Never

### Formula

\[
F=
\frac{\text{Between Group Variance}}
{\text{Within Group Variance}}
\]

### Results

| Metric | Value |
|----------|----------|
| F-value | 0.87 |
| p-value | 0.458 |
| Critical Value | 2.62 |

### Python Code

```python
from scipy.stats import f_oneway

F,p = f_oneway(
    daily,
    weekly,
    rarely,
    never
)
```

📌 **Interpretation:** BMI differences among exercise groups are not statistically significant.

📌 **Conclusion:** Exercise frequency does not significantly affect BMI.

---

## 👥 — ANOVA Across Age Groups

### Objective

Evaluate diabetes prevalence across age groups.

### Results

| Metric | Value |
|----------|----------|
| F-value | 1.50 |
| p-value | 0.201 |
| Critical Value | 2.39 |

📌 **Interpretation:** Diabetes prevalence varies slightly but not significantly across age groups.

📌 **Conclusion:** Age groups do not differ significantly in diabetes prevalence.

---

## 📈 Q7 — Correlation & Covariance Analysis

### Objective

Analyze relationship between Age and BMI.

### Formula

\[
r=
\frac{Cov(X,Y)}
{\sigma_x\sigma_y}
\]

### Results

| Metric | Value |
|----------|----------|
| Correlation (r) | 0.109 |
| Relationship | Very Weak Positive |

### Python Code

```python
correlation = df["Age"].corr(df["BMI"])

covariance = df["Age"].cov(df["BMI"])

print(correlation)
print(covariance)
```

📌 **Interpretation:** Age explains only about 1% of BMI variation.

📌 **Conclusion:** Age is not a meaningful predictor of BMI.

---

# 📊 Key Findings

✔️ Smoking status and diabetes prevalence were statistically independent.

✔️ Exercise frequency showed no statistically significant effect on BMI.

✔️ Male and female BMI distributions were statistically similar.

✔️ Confidence intervals provided reliable population estimates.

✔️ Diabetes prevalence did not significantly differ across age groups.

✔️ Age and BMI exhibited only a very weak positive correlation.

✔️ Correlation analysis showed age explains only about 1% of BMI variation.

✔️ Inferential statistics transformed healthcare data into actionable insights.

---

# 🎯 Final Conclusion

Derivable Judgement successfully applied inferential statistics and hypothesis testing techniques to a healthcare dataset of 500 patient records. Statistical analyses including Chi-Square Test, ANOVA, Confidence Intervals, t-Test, Correlation, and Covariance were used to evaluate healthcare-related hypotheses.

The results showed that smoking status had no significant association with diabetes, exercise frequency did not significantly affect BMI, and male and female BMI levels were statistically similar. Additionally, age showed only a very weak relationship with BMI, while confidence intervals provided reliable estimates of population parameters.

Overall, the project demonstrates how statistical methods can transform healthcare data into evidence-based insights and support informed decision-making.

---

# 🚀 How to Run

```bash
pip install pandas numpy scipy matplotlib openpyxl
```

Open:

```bash
jupyter notebook
```

Run:

```text
Derivable_Judgement.ipynb
```
---

# ✅ Submission Checklist

- Hypothesis Testing
- Confidence Intervals
- Critical Values
- p-value Analysis
- Independent Sample t-Test
- Chi-Square Test
- ANOVA
- Correlation Analysis
- Covariance Analysis
- Statistical Interpretations
- Dataset Included
- Jupyter Notebook Included
- Theory Report Included
- README Documentation Included

---

## 👩‍💻 Shruti Bhawsar

📍 Ahmedabad, Gujarat, India

⭐ If you found this project helpful, give it a star and feel free to fork!

### 📊 Data-Driven Decisions · Statistical Thinking · Evidence-Based Conclusions
