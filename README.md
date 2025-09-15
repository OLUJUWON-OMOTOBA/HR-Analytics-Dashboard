# HR Analytics Dashboard
<img width="1277" height="714" alt="image" src="https://github.com/user-attachments/assets/195587c9-e175-41f5-9a55-51b32d989e18" />




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
