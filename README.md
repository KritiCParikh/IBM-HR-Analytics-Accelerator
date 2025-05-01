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

## What I Built

| Task | Details |
|------|---------|
| **Normalization** | Applied 1NF, 2NF, and 3NF to split the dataset into 8 logically related tables |
| **Data Modeling** | Designed a relational schema to reflect real-world HR structure |
| **ER Diagram** | Visualized all tables and relationships with PK-FK integrity |
| **Indexing Strategy** | Indexed key columns (`EmployeeNumber`, `JobRole`, `PerformanceRating`) to optimize joins |
| **Partitioning** | Simulated partitioning of Wages by salary bands to improve compensation queries |
| **CTEs & Window Functions** | Used CTEs for query modularity and layered analytics, and window functions like `RANK()` and `AVG() OVER()` to analyze pay gaps, rank employees by income within roles, and compare satisfaction scores across departments |
| **Query Optimization** | Rewrote complex joins, added filters early, removed subqueries |
| **Business Logic Queries** | Created analytics queries to evaluate gender pay gaps, attrition trends, travel frequency, and performance distribution |

---

## Schema Overview (8 Tables)
- `employee_demographics`
- `employee_education`
- `jobrole`
- `wages`
- `performance`
- `current_company_details`
- `work_history`
- `company_benefits`

![Entity Relationship Diagram](https://github.com/KritiCParikh/IBM-HR-Analytics-Accelerator/blob/main/IBM_HR_ERD.jpg?raw=true)

---

## Outcomes
- Reduced average query response time by **50%**
- Enabled **real-time, relational HR analytics**
- Created a **scalable foundation** for future HR dashboards and ML-driven attrition risk scoring

---

## Future Enhancements

### Connect to BI Tools
Link the database to a visualization tool to build live dashboards, including:
- Attrition heatmaps  
- Retention trends by age or role  
- Salary comparisons across education levels  

### Make the Database Portable with Docker
Package the SQL database in a Docker container so others can spin it up easily without manual setup.

### Try a Star Schema (Optional)
Reshape the current relational structure into a dimensional star schema with fact and dimension tables for optimized reporting.

### Build Lightweight API Endpoints (Stretch Goal)
Use Flask or FastAPI to serve selected HR metrics and analytics through internal APIs or dashboards.

### Predict Attrition Using Machine Learning
Feed the cleaned, structured data into ML models such as Logistic Regression or XGBoost to identify employees at higher risk of leaving.

### Make It Interactive
Deploy an interactive interface using tools like Streamlit or Flask so HR teams can:
- Get real-time attrition predictions  
- Explore key drivers with SHAP for model explainability  
- Navigate salary or satisfaction trends through dynamic dashboards  

--

Thank You. Let’s keep learning and growing together!
