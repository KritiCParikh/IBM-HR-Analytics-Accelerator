# IBM-HR-Analytics-Accelerator - Attrition Prediction Database Design

## Overview
This project transforms IBM’s flat employee attrition dataset into a **fully normalized, analytics-optimized HR database** designed for workforce planning, compensation insights, and attrition risk modeling.

---

## Problem Statement
The original HR dataset (`HR-Employee-Attrition.csv`) consisted of over 1,400 unstructured employee records. While suitable for basic modeling, the lack of normalization made it inefficient for advanced analytics, leading to:

- Redundant data and inconsistent updates
- Difficulty performing multi-dimensional HR analysis
- Slow query performance due to poor relational structure

---

## 🛠️ What I Built

| Task | Details |
|------|---------|
| **Normalization** | Applied 1NF, 2NF, and 3NF to split the dataset into 8 logically related tables |
| **Data Modeling** | Designed a relational schema to reflect real-world HR structure |
| **ER Diagram** | Visualized all tables and relationships with PK-FK integrity |
| **Indexing Strategy** | Indexed key columns (`EmployeeNumber`, `JobRole`, `PerformanceRating`) to optimize joins |
| **Partitioning** | Partitioned the `Wages` table by salary range for efficient compensation queries |
| **CTEs & Window Functions** | Used CTEs for query modularity and layered analytics, and window functions like `RANK()` and `AVG() OVER()` to analyze pay gaps, rank employees by income within roles, and compare satisfaction scores across departments |
| **Query Optimization** | Rewrote complex joins, added filters early, removed subqueries |
| **Business Logic Queries** | Created analytics queries to evaluate gender pay gaps, attrition trends, travel frequency, and performance distribution |

---

## 🧾 Schema Overview (8 Tables)
- `employee_demographics`
- `employee_education`
- `jobrole`
- `wages`
- `performance`
- `current_company_details`
- `work_history`
- `company_benefits`

Please view  for the full diagram.

---

## Outcomes
- Reduced average query response time by **50%**
- Enabled **real-time, relational HR analytics**
- Created a **scalable foundation** for future HR dashboards and ML-driven attrition risk scoring

---

## 📁 Files in This Repo

| File/Folder | Description |
|-------------|-------------|
| `HR-Employee-Attrition.csv` | Cleaned original dataset |
| `IBM_Attrition_DB.sql` | Full DDL with table creation and constraints |
| `IBM_HR_ERD.jpg` | Entity-Relationship Diagram (ERD) |

---

## 🚀 Future Enhancements

1. **Add Sample Queries File**
   - Provide SQL scripts for real-world HR use cases:  
     `avg salary by role`, `attrition by department`, `promotion vs performance`.

2. **Integrate with BI Tools**
   - Connect database to Tableau or Power BI for live dashboards:  
     `Attrition heatmap`, `Retention trends`, `Salary breakdown`.

3. **Deploy via Docker**
   - Containerize the SQL database for easy reproducibility and sharing.

4. **Convert to Star Schema (Optional)**
   - Create a dimensional model optimized for HR data warehousing.

5. **Build API Endpoints (Stretch Goal)**
   - Use Flask or FastAPI to serve HR insights via an internal dashboard.

6. **Attrition Prediction Pipeline**
   - Use this cleaned and relational data to power predictive models (Logistic Regression, XGBoost).

7. - Deploy model with Streamlit or Flask for HR team to interact with
- Add SHAP visualizations for model interpretability
- Create dashboards with Tableau or Power BI

---

## 📜 License
MIT License
