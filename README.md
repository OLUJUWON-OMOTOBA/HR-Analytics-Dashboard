## 3) `HR-Analytics-Dashboard/README.md`


```markdown
# HR Analytics Dashboard


![Power BI](https://img.shields.io/badge/Tool-Power%20BI-blue)
![Dataset](https://img.shields.io/badge/Dataset-Synthetic-green)


## Overview


HR analytics project showcasing workforce composition, attrition, and performance. This dashboard is ideal for demonstrating the ability to uncover people insights and support HR / People Ops decisions.


## What’s included


- `employees.csv` — sample employee dataset (400 rows)
- `hr_queries.sql` — SQL examples for headcount and attrition
- `hr_dax_measures.txt` — suggested DAX to calculate headcount and attrition rate
- `README.md` — this file


## Key features & highlights


- Headcount and attrition metrics by department
- Salary distribution and performance analysis
- Simple predictive signals (flagging high attrition departments)


## Suggested Power BI build steps


1. Import `employees.csv` into Power BI Desktop.
2. Convert `hire_date` to Date and create a Date dimension if needed.
3. Create calculated columns for tenure and high-performer flag (e.g., performance_score >= 4.0).
4. Build visuals:
- Stacked column or donut: headcount by department
- Clustered bar: attrition rate by department
- Scatter plot: performance vs salary
- Boxplot (or distribution) for salary by department


## Example DAX snippets


```dax
Headcount = COUNT(employees[employee_id])
Attrition Count = CALCULATE(COUNT(employees[employee_id]), FILTER(employees, employees[attrition] = 1))
Attrition Rate = DIVIDE([Attrition Count], [Headcount])
Average Salary = AVERAGE(employees[salary])
