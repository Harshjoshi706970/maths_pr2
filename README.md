# Derivable Judgement: Clinical Health Records Inferential Statistics

A statistical inference and hypothesis testing pipeline analyzing physiological and behavioral health metrics across 500 clinical patient records.

---

## 📌 Project Overview
**Derivable Judgement (PR2)** applies core inferential statistics to extract actionable health insights from patient records. The workflow covers parameter estimation via Student's $t$-distributions, two-sample mean difference testing, contingency analysis via $\chi^2$ independence tests, demographic variance via One-Way ANOVA, and bivariate correlation mapping.

---

## 🚀 Key Modules & Statistical Tests

1. **Parameter Estimation (95% Confidence Intervals)**
   - Estimation of population means using Student's $t$-distribution across continuous features: `age`, `weight`, `bmi`, `blood_pressure`, `cholesterol_level`, and `glucose_level`.

2. **Two-Sample Mean Comparison (Independent $t$-test)**
   - Evaluation of BMI differences between diabetic and non-diabetic cohorts.
   - Rejection of null hypothesis at $\alpha = 0.05$ ($t = 4.9642$, $p = 9.49 \times 10^{-7}$).

3. **Categorical Association ($\chi^2$ Independence Tests)**
   - Cross-tabulation of behavioral traits against chronic conditions:
     - **Smoking vs. Diabetes**: $\chi^2 = 1.7404, p = 0.4189$ (Independent / Fail to reject $H_0$).
     - **Smoking vs. Hypertension**: $\chi^2 = 14.3667, p = 0.0008$ (Dependent / Reject $H_0$).

4. **Multi-Group Variance (One-Way ANOVA)**
   - Assessment of chronic disease rates and blood pressure across age cohorts (`18-25`, `26-35`, `36-45`, `46-60`, `60+`).
   - Demonstration of significant age-dependent progression for both blood pressure ($F = 54.4326, p < 10^{-37}$) and diabetes rates ($F = 7.8005, p = 4.21 \times 10^{-6}$).

5. **Covariance & Correlation Modeling**
   - Assessment of direction and strength of linear and monotonic associations using Pearson and Spearman coefficients.

---

## 📊 Dataset Schema

The underlying dataset (`health_records_dataset.csv`) contains 500 patient records:

| Feature | Data Type | Description |
| :--- | :--- | :--- |
| `record_id` | String | Unique patient visit UUID |
| `age_group` | Categorical | Age bracket (`18-25`, `26-35`, `36-45`, `46-60`, `60+`) |
| `age` | Integer | Patient age (years) |
| `weight` | Float | Patient body weight (kg) |
| `gender` | Categorical | Biological gender (`Male`, `Female`, `Other`) |
| `region` | Categorical | Geographic sector (`North`, `South`, `East`, `West`) |
| `smoking_status` | Categorical | Tobacco use (`Non-Smoker`, `Former Smoker`, `Current Smoker`) |
| `exercise_frequency`| Categorical | Exercise cadence (`Daily`, `Weekly`, `Never`) |
| `bmi` | Float | Body Mass Index (kg/m²) |
| `blood_pressure` | Float | Systolic blood pressure (mmHg) |
| `diabetes` | Boolean | Diagnosed diabetic status (`True` / `False`) |
| `hypertension` | Boolean | Diagnosed hypertension status (`True` / `False`) |
| `cholesterol_level`| Float | Serum cholesterol (mg/dL) |
| `glucose_level` | Float | Fasting blood glucose (mg/dL) |
| `visit_date` | Date | Record timestamp (`YYYY-MM-DD`) |

---

## 🛠️ Tech Stack & Dependencies

- **Language**: Python 3.x
- **Libraries**:
  - `pandas` – Data wrangling and cross-tabulation
  - `numpy` – Numerical operations and array manipulation
  - `scipy` – Inferential test statistics (`t.interval`, `ttest_ind`, `chi2_contingency`, `f_oneway`)
  - `matplotlib` – Diagnostic scatter plots and distributions
