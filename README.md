# Sales-Analytics

## About the project
The aim of this project is to help deduce key insights from the business data and suggest recommendations to help achieve an improved business performance.

![PowerBI Blinkit Sales Report](blinkit-sales-report.PNG)
![BlinkIT Sales Dashboard](https://github.com/user-attachments/assets/ae53a55b-fab3-41be-9854-e4210b95cde5)


## Table of Contents
1. [Problem Statement.](#problem-statement)
2. [KPI.](#kpi)
3. [Tools.](#tools)
4. [Steps.](#steps)
5. [Insights.](#insights)
6. [Challenges and Solutions.](#challenges-and-solutions)
7. [Recommendations.](#recommendations)
   
## Problem Statement.
A customer has requested a comprehensive analysis of their sales performance, customer satisfaction and outlet performance from the start of their business till date.

## KPI.
- <b>Total sales:</b> This is the sum of revenue generated from sales.
- <b>Average Sales:</b> Average revenue per sale.
- <b>Number of Items:</b> This is the total count of item currently sold by the business.
- <b>Average Rating:</b> The average of customer satisfaction on a scale of 0 -10 where 0 means totally dissatisfied, and 10 means very satisfied.

## Tools.
- Microsoft SQL.
- MS Excel.
- Power BI.

## Steps.
1.	<b>Data connection:</b> Our first step is to perform data extraction, Transformation and Load (ETL) Using Microsoft SQL server. Here we extracted the data from the database to Excel.
2.	<b>Data Cleaning/Data quality check:</b> Here we identified columns of interest, ensured there are no missing entries and spell checked to ensure data quality using SQL and Excel.
3.	<b>Data Modelling Or Data Preprocessing:</b> Here we analyze and define all the different data types in our dataset an create relationships between tables.
4.	<b>Dax Calculations:</b> In this step, we calculated key performance metrics to relating to the business requirements with the aid of DAX in Power BI.
5.	<b>Dashboarding:</b> This puts together steps 7, 8 and 9 in our table of content. Here we created visuals and reports to help visualize these KPI’s which we calculated in step 4 using DAX.

### Sql codes
 ```CREATE DATABASE sales
UPDATE BlinkIT_sales SET ItemFatContent = 'Regular' WHERE ItemFatContent = 'Regualr'
UPDATE BlinkIT_sales SET ItemFatContent = 'Low Fat' WHERE ItemFatContent = 'low fat'
UPDATE BlinkIT_sales SET 
```
### Quick data analysis in SQL
```
 SELECT Outlet_Type, SUM(Sales)  as sum_of_sales_by_outlettypes,
sum(sales) * 100.0 / (SELECT SUM(Sales) from BlinkIT_sales) as outlettype_pct_sales from BlinkIT_sales GROUP BY outlet_type

To select top sales in the data.
SELECT TOP 5 Item_Type, Sales FROM BlinkIT_sales ORDER BY Sales DESC

Analyzing Total Sales by Item_type ordered in a descending order
SELECT Item_Type, SUM(Sales) as item_sales from BlinkIT_sales GROUP BY Item_Type ORDER BY item_sales DESC;

```
### Power BI

## Insights.
Based on our analysis, we have been able to deduce the following from the data.
- The business has so far generated a total of 1,20€Million.
-	Super market Type1 outlet generated a total of 787,550€ which represents approx. 66% of outlet type.
-	Medium sized outlets contributed 42.27% which makes it the highest revenue generator compared to other outlets sizes.
-	The Business currently has a total of 8,523 distinct items they sell. 
-	On average, customers spend 140€ across all outlet types.
-	The customer rating of this business is (4 out of 10) low. Which means customers are largely dissatisfied with this business.

## Challenges and solutions.
From the dataset provided, we notice some years were missing, which makes it difficult to calculate changes in sale performance on a yearly or quarterly basis.
A solution to this challenge would be to meet the business’ data team to provide us with a comprehensive data with no year gaps. This would enable us make a comprehensive report on the business' performance.

## Recommendations.
Seek ways to improve customer satisfaction either by improving customer relationship, getting customer reviews, improving product quality, or price improvement.



