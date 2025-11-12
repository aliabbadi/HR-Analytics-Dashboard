# 💼 HR Analytics Dashboard – Power BI Project

## 📊 Project Overview
This project aims to analyze employee data to uncover insights about attrition, workforce demographics, job satisfaction, and other key HR metrics.  
The goal is to help the HR department make data-driven decisions to reduce employee turnover and improve retention strategies.

---

## 🎯 Objectives
- Identify the main factors contributing to employee attrition.
- Understand the distribution of employees by department, role, and experience level.
- Compare attrition rates across genders, age groups, and job roles.
- Analyze salary trends, work-life balance, and years of service.

---

## 🧠 Key Insights
- Higher attrition was observed among **new employees (< 3 years)**.
- **Sales and R&D** departments showed the highest turnover rates.
- **Younger employees** and **lower job satisfaction scores** were correlated with higher attrition.
- **Work-life balance** and **monthly income** appeared as significant retention factors.

---

## 🧰 Tools & Technologies
- **Power BI** → Data Cleaning, Modeling, DAX Measures, Visualization  
- **Excel / CSV Dataset** → Data Source  
- **DAX (Data Analysis Expressions)** → Custom measures and KPIs

---

## ⚙️ Data Cleaning & Preparation
Performed in Power BI using Power Query:
- Removed null and duplicate records.
- Standardized column names and data types.
- Created calculated columns for analysis:
  - `YearsAtCompanyCategory` (New / Mid-level / Experienced)
- Added measures:
  - `Total Employees`
  - `Employees Left`
  - `Attrition Rate`
  - `Average Salary`
  - `Female Ratio`

---

## 📐 Data Model
- Single table: `HR Data`
- Relationships not required (denormalized dataset)
- Measures created using DAX for flexible analysis

---

## 📈 Dashboard Features
- **KPI Cards** → Total Employees, Employees Left, Attrition Rate  
- **Bar Chart** → Attrition by Department  
- **Pie Chart** → Attrition by Gender  
- **Column Chart** → Attrition by Experience Level  
- **Line Chart** → Attrition vs Age  
- **Slicers** → Department, Gender, Job Role, Education  

---

## 🪄 DAX Formulas (Examples)
```DAX
-- Total Employees
Total Employees = COUNTROWS('hr')

-- Employees Left
Employees Left = CALCULATE(COUNTROWS('hr'), 'hr'[Attrition] = "left")

-- Attrition Rate
Attrition Rate = DIVIDE([Employees Left], [Total Employees])

-- Average Salary
Average Salary = AVERAGE('hr'[MonthlyIncome])

-- Female Ratio
Female Ratio = DIVIDE(
    CALCULATE(COUNTROWS('hr'), 'hr'[Gender] = "Female"),
    [Total Employees]
)
