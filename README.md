# Palmoria-Groups-Salary-Gender-Analysis-Power-BI-Dashboard-
A comprehensive Power BI report visualizing employee salary distribution, gender representation across regions, and bonus payouts within Palmoria Groups. Includes dynamic charts and filters for exploring workforce insights and equity gaps.
# HR Analysis
## Project Topic: Palmoria Groups Gender Analysis
### Brief
The Palmoria Group, a manufacturing company based in Nigeria, was embroiled in issues bordering on gender inequality in its 3 regions. I have been recruited as an HR Analytics expert to analyse the company’sHR data and come up with recommendations for management’s attention. This Power BI dashboard project visualizes gender-based employee insights within Palmoria Groups. It includes regional and departmental breakdowns of salaries, bonuses, performance ratings, and gender distribution. The dashboard highlights key findings such as gender pay gaps, regional disparities, and performance trends, aiding decision-making toward diversity and inclusion.
### Data Source
-- comma seperated value
- [Palmoria Group emp-data.csv](https://github.com/Yinka0567/Palmoria-Groups-Salary-Gender-Analysis-Power-BI-Dashboard-/blob/a972dab87ab5dded58841ad1f8c4914cfafb2df4/Palmoria%20Group%20emp-data.csv)
- Dataset: Employee data with demographics, salaries, ratings
### Tools Used
- Power BI: Data Cleaning and Preprocessing, Visualization and dashboard creation.
### Objective
#### Required
- Generally, there are two genders in the organization. However, some employees 
refused to disclose their gender. You would need to assign a generic gender status 
to these employees
- Some employees are without a salary because they are no longer with the company. 
You will need to take those employees out
- Lastly, some departments are indicated as “NULL”. These departments would also 
need to be taken out.
- Drive inclusive compensation and HR insights
    - Analyze gender distribution across regions and departments.
    - Evaluate salary averages and pay gaps between genders.
    - Identify departments and regions with the highest/lowest compensation.
    - Track employee performance ratings by gender.
    -  Highlight bonus distributions by location.
    -  Detect employees earning below the minimum salary threshold.
### Repository Structure
```

Palmoria-Gender-Analysis/
│
├── Dashboard\_Screenshot.jpg        # Full dashboard visual
├── README.md                       # Project description and insights
├── dataset\_cleaned.xlsx            # Cleaned dataset (optional/private)
└── PowerBI\_Dashboard.pbix          # Power BI dashboard file (optional/private)

```
### Dataset Fields 
- `Employee Name`
- `Gender`
- `Region`
- `Department`
- `Salary`
- `Performance Rating`
- `Bonus`
- `Minimum Salary Check`
### Data Summary & Insights
This dashboard provides a comprehensive gender-based analysis of employee distribution, salary structure, performance ratings, and bonus allocation across departments and regions within Palmoria Groups.
View interactive visuals and insights in the full dashboard screenshots provided below:
![palmorial visualization] (https://github.com/Yinka0567/Palmoria-Groups-Salary-Gender-Analysis-Power-BI-Dashboard-/blob/1bb41047982b4b420b485779c246412159bf419b/Dashboard%20Palmoria%20Group.PNG)

#### Some Dax Calcuation
```
Gender Count = COUNT('Employee'[Gender])
- Gender Percentage = DIVIDE(CALCULATE(COUNT('Employee'[Gender])), CALCULATE(COUNT('Employee'[Gender]), ALL('Employee'[Gender])))
```
```
Rating Count by Gender = COUNT('Employee'[Rating])
```
```
 Average Salary by Gender = AVERAGE('Employee'[Salary])
- Salary Count by Department and Region = COUNT('Employee'[Salary])
```
```
Employees Below Minimum Salary = COUNTX(FILTER('Employee', 'Employee'[Salary] < 90000), 'Employee'[Salary])
```
```
Bonus Amount = IF('Employee'[Rating] > 3, 'Employee'[Salary] * 0.1, 0)
- Total Amount to be Paid = 'Employee'[Salary] + 'Bonus Amount'
```
#### Top-Level Metrics
- Total Number of Employers: 946
- Total Salary Paid : 70M
- Employees Below Minimum Salary: 654
- Average Salary: 73.70K
- Total Amount to be Paid: 74.78M
- Total Bonus: 5.05M
#### Visualizations
Interactive charts showing deeper patterns:
- Rating Count by Gender: A bar chart categorizing performance ratings (Very Poor    -> Very Good) split by gender.
- Gender Distribution by Region: Bar chart for Kaduna, Abuja, and Lagos, split between Male and Female.
- Overall Gender Pie Chart: Shows 53.3% Female vs. 46.6% Male.
- Employees Below Minimum Salary: Bar chart broken down by region.
- Bonus Payout by Region: Bonus distribution visualized across the three regions.
#### Table View
- Employee names with total amount to be paid per person — a detailed breakdown.
#### Filter / Slicers
- Options to refine by Gender, Department, and Location, enhancing interactivity.
### Recommendations
- Gender Pay Gap Awareness

 - Despite women forming the majority of the workforce, males consistently earn more across job roles and regions.

 - This disparity warrants a formal equity review to ensure fair compensation practices and address potential biases.

- Incomplete Data & Gender Disclosure

   - “N/A” entries in gender and pay fields indicate data quality issues. Based on internal reports, some employees opted not to disclose their gender.

   - Management should investigate this trend, especially considering the potential impact on salary fairness and policy formation.
- Sub-Minimum Salary Concerns
    - Over 650 employees earn below the organization's established minimum salary threshold.
    - This anomaly should be explored—are these interns, contractors, or part-time workers? Or does it reflect gaps in policy enforcement?
- Performance Review Calibration
  - A significant proportion of employees received an “Average” rating.
  - This could point to a lack of differentiation in evaluations or a need for stronger performance review frameworks that recognize excellence and support growth.
## Author
**Enoch Amoo**
_Data Scientist_
[GitHub Profile](https://github.com/Yinka0567)
[linkedIn Profile](https://www.linkedin.com/in/amoo-enoch-b4515b24a/)
