# 📊 IBM HR Analytics — Employee Attrition Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Pages](https://img.shields.io/badge/Pages-3-blue?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-IBM%20HR%20Analytics-orange?style=for-the-badge)

---

## 🗂️ Project Overview

This is a **3-page interactive Power BI Dashboard** built on the IBM HR Analytics Employee Attrition dataset. The dashboard helps HR teams and business leaders identify key drivers of employee attrition, analyze workforce demographics, and make data-driven retention decisions.

> **Goal:** Understand *who* is leaving, *why* they are leaving, and *where* the highest attrition risk lies — across departments, job roles, income levels, and work conditions.

---

## 📸 Dashboard Preview

### Page 1 — Employee Attrition Overview
![Page 1](https://raw.githubusercontent.com/yogeshkumar70628/IBM-HR-Analytics-Employee-Attrition-Dashboard/main/Screenshot%202026-04-18%20171613.png)

### Page 2 — Demographic & Income Insights
![Page 2](https://raw.githubusercontent.com/yogeshkumar70628/IBM-HR-Analytics-Employee-Attrition-Dashboard/main/Screenshot%202026-04-18%20171639.png)

### Page 3 — Employee Detail Table
![Page 3](https://raw.githubusercontent.com/yogeshkumar70628/IBM-HR-Analytics-Employee-Attrition-Dashboard/main/Screenshot%202026-04-18%20171704.png)

---

## 📋 Dashboard Pages Breakdown

### 🔵 Page 1 — Employee Attrition Dashboard (Executive Overview)

**KPI Cards:**
| Metric | Value |
|---|---|
| Total Employees | 1,470 |
| Overall Attrition Rate | 16.12% |
| Avg Monthly Income | 6.50K |
| Overtime Attrition Rate | 30.53% |

**Visuals on this page:**
- **Total Employees by Department and Attrition** — Clustered bar chart comparing attrition vs retention across Research & Development, Sales, and Human Resources
- **Attrition Rate % by JobRole** — Horizontal bar chart showing Sales Representative (40%) as the highest attrition role
- **Sum of AttritionFlag by Gender** — Donut chart showing Male (63.29%) vs Female (36.71%) attrition split
- **Attrition Rate % by OverTime** — Bar chart showing employees doing overtime have 31% attrition vs 10% for non-overtime

**Slicers/Filters:**
- Gender (Female / Male)
- OverTime (Yes / No)
- Department (HR / R&D / Sales)
- Age Group (Under 25, 25–34, 35–44, 45+)
- JobLevel (1–5)
- BusinessTravel
- MaritalStatus

---

### 🟡 Page 2 — Demographic & Income Insights

**Visuals on this page:**
- **Attrition Rate % by MaritalStatus** — Single employees have the highest attrition at 26%, followed by Married (12%) and Divorced (10%)
- **Avg Monthly Income by JobLevel** — Area line chart showing income rises steeply from 3K (Level 1) to 19K (Level 5)
- **Sum of YearsAtCompany by MonthlyIncome** — Scatter plot revealing income-tenure relationship patterns
- **Attrition Rate % by BusinessTravel** — Employees who Travel Frequently have 24.9% attrition vs 8% for Non-Travel

**Slicers/Filters:**
- Gender
- OverTime
- Department
- Age Group

---

### 🟢 Page 3 — Employee Detail Table (Drill-Through View)

**KPI Summary Cards:**
| Metric | Total |
|---|---|
| Sum of EmployeeNumber | 1,506,552 |
| Sum of Age | 54K |
| Sum of MonthlyIncome | 9,559K |
| Sum of YearsAtCompany | 10K |

**Interactive Table** with columns: Department, Gender, Attrition, Job Satisfaction Label, OverTime, Employee Number, Age, Monthly Income, Years at Company, Job Role

**Slicers/Filters:**
- Job Satisfaction (All / High / Low / Medium / Very-High)
- Attrition (Yes / No)
- OverTime (Yes / No)
- Department (HR / R&D / Sales)

---

## 🔍 Key Insights

1. **Sales Representatives** face the highest attrition at **40%** — nearly 1 in 2 leave
2. Employees working **OverTime** are **3× more likely** to leave (31% vs 10%)
3. **Single employees** have significantly higher attrition (26%) vs married (12%)
4. **Frequent business travelers** show 24.9% attrition — almost triple non-travelers (8%)
5. **Junior roles (Level 1–2)** with lower income are most vulnerable to attrition
6. **Research & Development** has the largest workforce but also the highest absolute attrition count

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development & visualization |
| **DAX** | Custom measures and calculated columns |
| **Power Query** | Data transformation and cleaning |
| **IBM HR Dataset** | Source data (1,470 employee records) |

---

## 📁 Project Structure

```
📦 IBM-HR-Analytics-Employee-Attrition-Dashboard
 ┣ 📊 HR_Employee_Attributions.pbix        ← Power BI file
 ┣ 🖼️ Screenshot 2026-04-18 171613.png     ← Page 1 Preview
 ┣ 🖼️ Screenshot 2026-04-18 171639.png     ← Page 2 Preview
 ┣ 🖼️ Screenshot 2026-04-18 171704.png     ← Page 3 Preview
 ┗ 📄 README.md
```

---

## 📊 Dataset Information

- **Source:** [IBM HR Analytics Employee Attrition & Performance — Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Records:** 1,470 employees
- **Features used:** 35 columns including Age, Attrition, BusinessTravel, Department, EducationField, Gender, JobLevel, JobRole, MaritalStatus, MonthlyIncome, OverTime, YearsAtCompany, and more

---

## 🚀 How to Use

1. **Clone this repository**
   ```bash
   git clone https://github.com/yogeshkumar70628/IBM-HR-Analytics-Employee-Attrition-Dashboard.git
   ```

2. **Open the `.pbix` file** in Power BI Desktop (free download from Microsoft)

3. **Interact with the slicers** to filter data by Gender, Department, Age Group, OverTime, JobLevel, and more

4. **Use drill-through** on Page 3 for employee-level detail analysis

---

## 💡 DAX Measures Used

> All measures are built on the table `WA_Fn-UseC_-HR-Employee-Attrition`

```dax
-- 1. Total Employees
Total Employees =
COUNTROWS('WA_Fn-UseC_-HR-Employee-Attrition')

-- 2. Total Attrition
Total Attrition =
SUM('WA_Fn-UseC_-HR-Employee-Attrition'[AttritionFlag])

-- 3. Attrition Rate %
Attrition Rate % =
DIVIDE([Total Attrition], [Total Employees], 0) * 100

-- 4. Retention Rate %
Retention Rate % =
100 - [Attrition Rate %]

-- 5. Avg Age
Avg Age =
AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[Age])

-- 6. Avg Monthly Income
Avg Monthly Income =
AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[MonthlyIncome])

-- 7. Avg Years At Company
Avg Years At Company =
AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[YearsAtCompany])

-- 8. Overtime Attrition Rate
Overtime Attrition Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS('WA_Fn-UseC_-HR-Employee-Attrition'),
        'WA_Fn-UseC_-HR-Employee-Attrition'[Attrition] = "Yes",
        'WA_Fn-UseC_-HR-Employee-Attrition'[OverTime] = "Yes"
    ),
    CALCULATE(
        COUNTROWS('WA_Fn-UseC_-HR-Employee-Attrition'),
        'WA_Fn-UseC_-HR-Employee-Attrition'[OverTime] = "Yes"
    ),
    0
) * 100

-- 9. Dept Attrition vs Avg
Dept Attrition vs Avg =
[Attrition Rate %] - CALCULATE(
    [Attrition Rate %],
    ALL('WA_Fn-UseC_-HR-Employee-Attrition'[Department])
)

-- 10. High Risk Employees
High Risk Employees =
CALCULATE(
    [Total Employees],
    'WA_Fn-UseC_-HR-Employee-Attrition'[OverTime] = "Yes",
    'WA_Fn-UseC_-HR-Employee-Attrition'[JobSatisfaction] <= 2,
    'WA_Fn-UseC_-HR-Employee-Attrition'[WorkLifeBalance] <= 2
)

-- 11. Income Gap Male vs Female
Income Gap Male vs Female =
CALCULATE(
    [Avg Monthly Income],
    'WA_Fn-UseC_-HR-Employee-Attrition'[Gender] = "Male"
)
- CALCULATE(
    [Avg Monthly Income],
    'WA_Fn-UseC_-HR-Employee-Attrition'[Gender] = "Female"
)
```

---

## 🎨 Theme & Design

- **Primary color:** Navy Blue (`#1A2A5E`)
- **Accent:** Golden Yellow (`#F2C811`)
- **Alert:** Coral Red for high attrition indicators
- **Font:** Segoe UI (Power BI default)
- **Style:** Clean corporate theme with consistent card borders and slicer panels

---

## 👤 Author

**YogeshKumar**
- 🔗 LinkedIn: https://www.linkedin.com/in/yogeshkumar-data-analyst/
- 💼 GitHub: https://github.com/yogeshkumar70628
- 📧 Email: yugalarya70628@gmail.com

---

## ⭐ Show Your Support

If you found this project helpful, please consider giving it a **⭐ star** on GitHub — it motivates me to build more!

---

*Made with ❤️ using Power BI*
