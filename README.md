# ❤️ Heart Disease Analysis Using Python

![Language](https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Libraries](https://img.shields.io/badge/Libraries-Pandas%20%7C%20NumPy%20%7C%20Seaborn-orange?style=for-the-badge)
![Tool](https://img.shields.io/badge/Tool-Jupyter%20Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

> A statistical exploratory data analysis (EDA) project investigating heart disease risk factors across four international medical institutions — combining data wrangling, outlier analysis, hypothesis testing, and probability calculations to extract meaningful clinical insights from real patient data.

---

## 📖 Table of Contents

- [About the Project](#about-the-project)
- [Research Questions](#research-questions)
- [Dataset](#dataset)
- [Key Findings](#key-findings)
- [Tech Stack](#tech-stack)
- [Project Workflow](#project-workflow)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Project Structure](#project-structure)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## About the Project

Heart disease is the **leading cause of death globally**, responsible for over 17.9 million deaths annually (WHO). This capstone project performs a rigorous statistical analysis of patient data collected from **four international medical institutions**, examining whether risk factors like age and cholesterol are meaningful predictors of heart disease — and whether those patterns hold consistently across different geographic locations.

This project goes beyond basic EDA — it applies **normality testing (QQ plots)**, **outlier removal**, **two-sample T-tests**, and **conditional probability calculations** to draw statistically grounded conclusions from real-world clinical data.

---

## Research Questions

The analysis investigates three focused questions:

**Question 1 — Location Variation:**
> Does there seem to be an average heart disease risk value shared among all locations, or does one location stand out from the rest?

**Question 2 — Age as a Risk Factor:**
> Does the data reflect an increased risk for heart disease in older patients?

**Question 3 — Cholesterol as a Risk Indicator:**
> How probable is it for a patient with cholesterol levels above 200 mg/dL to have a higher-than-average heart disease risk value?

---

## Dataset

Data was sourced from **four institutions** as part of the UCI Heart Disease Dataset (collected no later than July 1988):

| # | Institution | Location | Records |
|---|---|---|---|
| 1 | Cleveland Clinic Foundation | Cleveland, USA | 303 |
| 2 | Hungarian Institute of Cardiology | Budapest, Hungary | 294 |
| 3 | V.A. Medical Center | Long Beach, CA, USA | 200 |
| 4 | University Hospital | Zurich, Switzerland | 123 |

Each dataset contains **14 clinical attributes** including:

| Attribute | Description |
|---|---|
| `Age` | Patient age |
| `Sex` | Patient sex |
| `cp` | Chest pain type (1–4) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `cholestrol` | Serum cholesterol (mg/dL) |
| `fbs` | Fasting blood sugar > 120 mg/dL |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina |
| `oldpeak` | ST depression from exercise |
| `target` | Heart disease risk value (0 = none, 4 = highest) |

> ⚠️ **Note:** The dataset was curated in 1988 and may not reflect contemporary health trends. Patient selection criteria also varied across institutions, which is considered in the analysis.

---

## Key Findings

**Q1 — Location Variation:**
- All four datasets showed **statistically significant differences** in mean risk values (confirmed via two-sample T-tests with very small p-values, e.g. Cleveland vs Hungary: p = 2.27e-13)
- The **Hungarian Institute diverged most notably**, with a mean risk of just **0.36** vs Switzerland's **1.82** — likely due to binary scoring conventions used at that institution
- Cleveland and Long Beach VA showed similar standard deviations despite different means

**Q2 — Age as a Risk Factor:**
- Scatter plots of Age vs Heart Disease Risk showed **no strong linear trend** across any location
- The Long Beach VA dataset showed a slight concentration of higher risk in older patients, but overall age alone was **not a standout predictor** in this dataset

**Q3 — Cholesterol & Risk Probability:**
| Location | Patients with Cholesterol > 200 mg/dL | Probability of Above-Average Risk |
|---|---|---|
| Cleveland | 253 | **27.7%** |
| Long Beach VA | 117 | **29.9%** |
| Hungary | 216 | **40.7%** |
| Switzerland | N/A | Data unavailable |

- Hungary's higher probability further supports the theory that its risk values were assigned on a binary scale

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core programming language |
| Pandas | Data loading, cleaning, and manipulation |
| NumPy | Statistical calculations and array operations |
| Matplotlib | QQ plots, histograms, scatter plots, box plots |
| SciPy (`ttest_ind`) | Two-sample T-tests for hypothesis testing |
| Jupyter Notebook | Interactive analysis environment |

---

## Project Workflow
```
1. Data Loading
   └── Read 4 CSV files (Cleveland, Long Beach VA, Switzerland, Hungary)
   └── Replace missing values ('?') with 0

2. Normality Testing
   └── QQ Plots of Age data per location
   └── Age histograms to check for skewness

3. Outlier Removal
   └── Box plots to identify outliers
   └── Remove records ±2 standard deviations from mean (Long Beach VA & Switzerland)

4. Question 1 — Location Risk Comparison
   └── Compute mean & std of heart disease risk per location
   └── Run pairwise two-sample T-tests (6 comparisons)
   └── Conclude on statistical significance of differences

5. Question 2 — Age vs Risk
   └── Scatter plots: Age vs Heart Disease Risk Value per location
   └── Visual interpretation of trend (or lack thereof)

6. Question 3 — Cholesterol Probability
   └── Filter patients with cholesterol > 200 mg/dL
   └── Calculate proportion with above-average risk values
   └── Compare results across Cleveland, Long Beach VA, and Hungary
```

---

## Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib scipy jupyter
```

### Installation

1. **Clone the repository**
```bash
   git clone https://github.com/nandita0401/Heart-Disease-Analysis-Using-Python.git
   cd Heart-Disease-Analysis-Using-Python
```

2. **Launch Jupyter Notebook**
```bash
   jupyter notebook
```

3. **Open the notebook and run all cells**
```
   Kernel → Restart & Run All
```

---

## Project Structure
```
Heart-Disease-Analysis-Using-Python/
├── heart_disease_analysis.ipynb   # Main notebook with full analysis
├── cleveland.names.csv            # Cleveland Clinic dataset
├── va.names.csv                   # Long Beach VA dataset
├── switz.names.csv                # Switzerland dataset
├── hungarian.names.csv            # Hungary dataset
└── README.md
```

---

## Future Improvements

- [ ] Add **ML classification models** (Logistic Regression, Random Forest) to predict heart disease presence
- [ ] Build an **interactive dashboard** using Plotly or Streamlit
- [ ] Standardize datasets for a **combined cross-location analysis**
- [ ] Investigate the **binary vs multi-level scoring discrepancy** in the Hungarian dataset
- [ ] Repeat analysis with a **contemporary dataset** to account for post-1988 health trends
- [ ] Add **correlation heatmaps** across all 14 features

---

## Author

**Nandita Bharambe**

[![GitHub](https://img.shields.io/badge/GitHub-nandita0401-181717?style=flat&logo=github)](https://github.com/nandita0401)

---

> 💡 *This project demonstrates that meaningful insights require more than just plotting data — statistical rigor through hypothesis testing and probability analysis is what separates surface-level observation from evidence-based conclusions.*
