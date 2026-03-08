# University Student Analytics Dashboard

## Project Overview

This project analyzes a university student dataset to understand academic performance, dropout risk, and career outcomes. The goal is to transform raw student data into actionable insights through data cleaning, data quality validation, and interactive business intelligence dashboards.

The dataset contains **3,000 student records and 40 attributes** covering academic performance, financial background, student engagement, and employment outcomes.

The final output of the project is an **interactive Tableau dashboard** supported by **Python-based data preparation and analysis**.

---
# Tools and Technologies

The following tools were used in this project:

### Python
Libraries used include:
- Pandas
- NumPy

Used for data preparation and analysis.

### Jupyter Notebook

### Tableau

Used to build the **interactive analytics dashboard**, including:

---

# Project Workflow

The project was completed in the following stages:

## 1. Data Exploration

Initial data profiling was performed to understand the dataset structure.

Dataset characteristics:

- 3,000 student records
- 40 columns
- 22 numeric variables
- 18 categorical variables
- 11 columns contained missing values

The dataset represents the **student lifecycle**, including:

- Academic performance
- Engagement activities
- Financial background
- Wellbeing indicators
- Career outcomes

Each row represents **one student**.

---

# 2. Data Cleaning and Preparation (Python)

Data cleaning was performed using **Python in a Jupyter Notebook**.

### Missing Value Handling

11 columns contained missing values. Different imputation strategies were applied depending on the variable type.

Techniques used:

- **Median Imputation**
  - Used for numeric columns with skewed distributions  
  - Example: SAT Score, Family Income, Study Hours

- **Mode Imputation**
  - Used for categorical variables  
  - Example: Parental Education Level

- **Conditional Imputation**
  - Applied when the value logically depends on another column  
  - Example:
    - If `Employment_Offer = No` → `Starting_Salary = 0`
    - If `Scholarship_Status = No` → `Scholarship_Amount = 0`

After cleaning:

- Missing values reduced from **2,796 cells to 0**

---

# 3. Outlier Detection and Treatment

Outliers were detected using the **Interquartile Range (IQR) method**.

Affected columns:

- Study Hours Per Week
- Weekly Work Hours
- Family Income

Instead of removing records, **Winsorization (capping)** was applied:

- Extreme values were capped at the IQR upper bound
- This preserved valid student records while reducing statistical distortion.

---

# 4. Data Quality Validation

A full **Data Quality Assessment** was conducted across the dataset.

The following dimensions were validated:

- Completeness
- Accuracy
- Consistency
- Validity
- Uniqueness
- Integrity
- Timeliness

Results:

- No duplicate records
- All 40 columns have valid data types
- No remaining missing values
- Dataset confirmed ready for analysis

---

# 5. Dashboard Development (Tableau)

An interactive dashboard was developed using **Tableau** to visualize key metrics and insights.

The dashboard consists of **three main analytical tabs**.

### Executive Overview

Provides a high-level institutional snapshot including:

![Dashboard](1.png)

---

### Academic Performance

Analyzes academic behavior and performance including:

![Dashboard](2.png)

---

### Career Outcomes

Focuses on employment and career readiness.
  
![Dashboard](3.png)

---

# Key Insights

Several important insights were discovered during the analysis.

- GPA Does Not Strongly Predict Employment
- SAT Scores Do Not Predict University GPA
- Internship Participation Did Not Increase Employment Rate
- AI Program Students Have the Highest Dropout Risk
- Final-Year Students Have the Highest Dropout Risk



# Repository Structure

```
project/
│
├── data/
│   └── university_dataset.csv
│   └── cleand_university_dataset.csv
│
├── notebooks/
│   └── data_cleaning.ipynb
│
├── dashboard/
│   └── university_dashboard.twb
│
├── report/
│   └── University_BI_Report.pdf
│
└── README.md
