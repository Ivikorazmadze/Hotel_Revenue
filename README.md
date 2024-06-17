# Hotel_Revenue

## Table of Contents

- [Project Overview](#project-overview)
- [Tools](#tools)
- [Data Preparation](#data-preparation)
- [Explaratory Data Analysis](#explaratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
- [Limitations](#limitations)

### Project Overview 
---

<img width="601" alt="Project overview" src="https://github.com/Ivikorazmadze/Hotel_Revenue/assets/115480932/d48256c5-47b7-4465-b8b6-9440f0400046">

The report is to show Revenue according the nights spent in a period of 3 years shared by City and Resort hotels along with insights about the sum of car parkings neccessity. 

### Tools
---

- Data Source - Excel [Download Here](https://www.microsoft.com/en-us/microsoft-365/p/excel-home-and-student/CFQ7TTC0HLKR?activetab=pivot:overviewtab)

- Data Cleaning & Analysis - MySQL Workbench [Download Here](https://dev.mysql.com/downloads/workbench/)

- Data Visualization - PowerBI [Download here](https://dev.mysql.com/downloads/workbench/)

 ### Data Preparation
 ---
  
below are mentioned steps to prepare the data for visualisation

1) Data Loading and inspection
  
2) Handling Missing Values
  
3) Data formating

4) Writing Complex queries

5) Exporting From MySQL the table and import to Power BI

### Explaratory Data Analysis
---

EDA involved in the following report to answer key questions, such as:

- SUM of Revenue

- Total Nights occupied

- Average of Daily Rates

- Discount Ratio

- Sum of Revenues by years / hotels 

- Filters by Cities

### Data Analysis
---

Data Analysis featured following syntaxes:

```sql
create database Project
```

```sql
with hotels as (
select * from hotel_2018
union
select * from hotel_2019
union
select * from hotel_2020)
arrival_date_year,
hotel,
round(sum((stays_in_weekend_nights + stays_in_week_nights)*adr),2) as revenue
from hotels group by arrival_date_year, hotel
```

```sql
with hotels as (
select * from hotel_2018
union
select * from hotel_2019
union
select * from hotel_2020)
select * from hotels
left join market_segment
on hotels.market_segment = market_segment.market_segment
left join meal_cost
on hotels.meal = meal_cost.meal
```

### Results/Findings
---

below is shown analysis:
- The most profitable period for the business was 2019 year
- In total Resort Hotels are the more profitable

### Limitations
---

- The daily rates were charged per night
- The Revenue was calculated by the following formula 
  ```sql 
  round(sum((stays_in_weekend_nights + stays_in_week_nights)*adr),2)
  ```
