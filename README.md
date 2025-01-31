# Delayed-Oil-Project
## PROJECT OVERVIEW
**Objective**
This project investigates the root causes of delays in the oil transfer process and proposes a strategic solution plan. Analyzing operational workflows, resource allocation, and process efficiency, it seeks to identify trends and key areas for improvement.

**Scope**

The analysis covers:
* Current transfer and handling protocols
* Staffing and equipment utilization patterns
* Service delay patterns and external influencing factors
* Operational bottlenecks and improvement opportunities

**Methodology**
- Data Collection: Gathering logs, staffing data, equipment status, and service records.
- Analysis: Identifying delay trends and correlating them with operational factors.
- Root Cause Analysis: Diagnosing main delay contributors.
- Solution Proposal: Recommending solutions, such as process optimization and resource allocation.

---

### DATA SOURCE
The data set was provided by the client as a CSV file, which was downloaded and processed for analysis.

**Tools**
- Microsoft Excel: Utilized for preliminary data correction and initial review of the dataset.
- SQL Server: Employed for data cleaning and in-depth analysis to extract meaningful insights.
- Power BI: Used to visualize insights and provide detailed, interactive reports.

### EXPLORATORY DATA ANALYSIS (EDA)
In this EDA phase, we will examine the human resource dataset to address key operational questions that can impact the efficiency and reliability of oil transfer services. These insights will help identify potential areas for improvement and facilitate data-driven decision-making.

---

**Key Questions to Address:**
1. Total Number of Truck Drivers
  - Determine the number of truck drivers to assess if current staffing meets operational demands.
2. Number of Efficient Trucks
  - Identify the count of trucks classified as efficient to understand fleet reliability and potential operational constraints.
3. Coverage Areas (Distances in Kilometers)
  - Analyze distances covered to evaluate the geographic reach and the adequacy of logistical support across areas served.
4. Truck Breakdown and Maintenance Frequency
  - Assess the frequency of truck breakdowns and scheduled maintenance to pinpoint areas needing additional support or preventive measures.

These insights from EDA will contribute to optimizing workforce planning, improving fleet management, and enhancing the overall efficiency of oil transfer services.

---

### USED USED SQL CODES

SQL
```SELECT COUNT(*) AS TotalTruckDrivers
FROM employees
WHERE job_title = 'Truck Driver';
SELECT COUNT(*) AS EfficientTrucks FROM trucks WHERE efficiency_status = 'Efficient';
SELECT truck_id, SUM(distance_in_km) AS TotalDistanceCovered FROM deliveries GROUP BY truck_id;
SELECT truck_id, COUNT(*) AS BreakdownCount FROM maintenance_log WHERE maintenance_type = 'Breakdown' GROUP BY truck_id;
SELECT truck_id, COUNT(*) AS MaintenanceCount FROM maintenance_log GROUP BY truck_id;
SELECT COUNT(*) AS EmployeesHiredInLastYear FROM employees WHERE hire_date >= DATE_SUB(CURDATE(), INTERVAL 1 YEAR);
SELECT YEAR(hire_date) AS Year, MONTH(hire_date) AS Month, COUNT(*) AS EmployeesHired FROM employees GROUP BY YEAR(hire_date), MONTH(hire_date) ORDER BY YEAR(hire_date) DESC, MONTH(hire_date) DESC;

---

### RECOMMENDATIONS

Based on the Exploratory Data Analysis (EDA) and insights derived from the SQL queries, here are some recommendations to improve the efficiency and reliability of the oil transfer service:
1. Optimize Workforce Allocation
    - Recommendation: Based on the total number of truck drivers, assess if the current workforce is sufficient to meet demand, especially during peak periods. If there are shortages, consider hiring additional drivers or redistributing work hours to avoid delays.
    - Actionable Steps:
      1. Evaluate whether the number of drivers matches the number of trucks and expected delivery volumes.
      2. Consider flexible staffing models, such as on-demand or seasonal hires, to meet peak service needs.
2. Fleet Management and Maintenance Optimization
•	Recommendation: Analyze the number of efficient trucks and the breakdown/maintenance frequency. If a significant percentage of trucks are not efficient, or if maintenance is frequent, consider upgrading or replacing older trucks.
•	Actionable Steps:
o	Perform a detailed analysis of trucks' age, usage patterns, and maintenance logs to identify inefficiencies.
o	Develop a preventive maintenance schedule to reduce breakdowns, including replacing parts before they fail.
o	Investigate leasing or acquiring newer, more efficient trucks if maintenance costs are too high for older ones.
3. Geographic Coverage and Operational Efficiency
•	Recommendation: Based on the distance covered by each truck, assess whether the current fleet is optimized for service areas. If some trucks consistently cover longer distances, consider redistributing workloads or investing in more fuel-efficient trucks for these routes.
•	Actionable Steps:
o	Optimize truck routing to reduce fuel consumption and minimize downtime.
o	Consider geographic clustering of routes to reduce truck wear and travel time.
4. Address Breakdown and Maintenance Trends
•	Recommendation: If certain trucks experience frequent breakdowns, investigate the root causes, whether they are due to maintenance lapses, truck age, or poor driving habits. Trucks with the highest breakdown frequency may need to be replaced or undergo more frequent checks.
•	Actionable Steps:
o	Analyze the breakdown history of trucks and schedule preventive maintenance for those with high breakdown rates.
o	Ensure maintenance logs are regularly updated and that any recurring issues are addressed promptly.
5. Monitor Employee Hiring Trends
•	Recommendation: If the data shows a trend of increasing hires in the past year, analyze whether this increase is aligned with the business growth or driven by turnover. If the increase is due to high turnover, consider implementing retention strategies.
•	Actionable Steps:
o	Focus on improving employee engagement and job satisfaction to reduce turnover, particularly among drivers.
o	Introduce training programs to enhance employee skills and retention.
o	If hiring is aligned with business growth, ensure adequate onboarding and integration of new staff into operations.
6. Enhance Long-Term Staffing Plans
•	Recommendation: Analyze the trend of employee hiring over time to identify patterns or gaps. If hiring surges during specific months, develop staffing plans that anticipate these needs and ensure adequate resources during peak periods.
•	Actionable Steps:
o	Use historical hiring data to forecast future staffing needs and prepare for seasonal demand.
o	Build a pool of part-time or temporary employees to ensure flexibility during high-demand periods.



