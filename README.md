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
![Page 1](screenshots/page1.png)

### Page 2 — Demographic & Income Insights
![Page 2](screenshots/page2.png)

### Page 3 — Employee Detail Table
![Page 3](screenshots/page3.png)

---

## 📋 Dashboard Pages Breakdown

### 🔵 Page 1 — Employee Attrition Dashboard (Executive Overview)

**KPI Cards:**
| Metric | Value |
|---|---|
| Total Employees | 1,470 |
| Overall Attrition Rate | 16.12% |
| Avg Monthly Income | $6.50K |
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
- **Avg Monthly Income by JobLevel** — Area line chart showing income rises steeply from ₹3K (Level 1) to ₹19K (Level 5)
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
📦 HR-Employee-Attrition-Dashboard
 ┣ 📊 HR_Employee_Attributions.pbix     ← Power BI file
 ┣ 📂 screenshots/
 ┃ ┣ 🖼️ page1.png                       ← Executive Overview
 ┃ ┣ 🖼️ page2.png                       ← Demographics & Income
 ┃ ┗ 🖼️ page3.png                       ← Detail Table
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
   git clone https://github.com/yourusername/HR-Employee-Attrition-Dashboard.git
   ```

2. **Open the `.pbix` file** in Power BI Desktop (free download from Microsoft)

3. **Interact with the slicers** to filter data by Gender, Department, Age Group, OverTime, JobLevel, and more

4. **Use drill-through** on Page 3 for employee-level detail analysis

---

## 💡 DAX Measures Used

```dax
-- Attrition Rate %
Attrition Rate % = 
DIVIDE(
    CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "Yes"),
    COUNT(HR_Data[Attrition]),
    0
) * 100

-- Avg Monthly Income
Avg Monthly Income = AVERAGE(HR_Data[MonthlyIncome])

-- Overtime Attrition Rate
Overtime Attrition Rate = 
CALCULATE([Attrition Rate %], HR_Data[OverTime] = "Yes")
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
