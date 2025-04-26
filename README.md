# Superstore-Analysis
This dataset contains sales data for a spare store giant, covering product categories, customer segments and geographical regions. our analysis aims to provide insights on target markets and optimize sales performance.

### Data Sources
The analysis is based on a “sample superstore.csv dataset” containing sales data from 2014 to 2017.
(https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

### Tool used
-  Excel : Data Cleaning
-  SQL Server : Data Analysis
-  Power BI : Data Visualization

-  ### Data Cleaning/Pre-Processing
Data cleaning and preprocessing were carried out at the intial stage to ensure the quality of data,Thus;
- Data loading and inspection
- Handling duplicates
- Fixing the un-standardized date format
- Data Cleaning and Formatting

  ###  Exploratory data analysis (EDA)
The EDA process involves understanding data, identifying patterns and detecting anomalies to inform futher analysis(like answering key questions);

1. SALES TREND OVER TIME?
2. Who are our top 10 customers?
3. Top 10 performing categories by profits?
4. Sales by city and states?
5. Sales by region(ship-mode)?

   ### DATA Analysis
Data analysis was done in SQL

 ~~~sql
SALES TREND OVER TIME
 SELECT Order_Date, Ship_Date, sales
 from [Sample - Superstore]
 where Order_Date BETWEEN '2014-01-01' and '2017-12-31'
 and Ship_Date between ' 2014-01-01' and '2017-12-31'
 order by Order_Date, Ship_Date ASC;
-- who are our top 10 customers
select top 10 customer_name,product_id, sum(sales) as total_purchase
from [dbo].[Sample - Superstore]
group by customer_name, product_id
order by total_purchase DESC
-- Top 10 performing categories by profits

select top 10 category, sum(profit) as total_profit
from [Sample - Superstore]
group by Category
order by total_profit DESC
--sales by city and states

select top 10 state,city, sum(sales) as sales_by_location
from [Sample - Superstore]
group by state, city
order by sales_by_location DESC
--sales by region(ship-mode)

select ship_mode, sum(sales) as sales_by_shipmode
from [Sample - Superstore]
group by Ship_Mode
order by sales_by_shipmode DESC
~~~


![](![img1](https://github.com/user-attachments/assets/993c2192-ab08-49ae-9ce7-a3e35bcb059d)




### Results/Findings


Sales Trend
- Sales have increased significantly over the past four years, indicating a positive growth trend.

Top-Performing Subcategories
- The top 10 subcategories driving sales are:
    1. Phones
    2. Chairs
    3. Storage
    4. Tables
    5. Binders
    6. Machines
    7. Accessories
    8. Copiers
    9. Bookcases
    10. Appliances

Shipping Preferences
- The most commonly used shipping mode is Standard Class.

Regional Sales Performance
- The West region generates the most sales, followed by:
    1. East
    2. Central
    3. South

#### Customer Insights
- The top customer has spent over $25,000.
- 
### Recommendations
Based on my  findings, here are some recommendations to improve sales;

1. Focus on top-performing subcategories: Allocate more resources to promote and expand product lines in top categories (phones, chairs, storage, tables, etc.).
2. Analyze low-performing subcategories: Identify areas for improvement or potential discontinuation.
3. Develop loyalty programs: Reward top customers with exclusive offers, discounts, or early access to new products.
4. Focus on West and East regions: Allocate more resources to these high-performing regions.
5. Develop targeted marketing campaigns: For Central and South regions to drive growth.
6.  Continuously monitor sales trends: Analyze sales data to identify areas for improvement.


 
### Limitations

1. Data-driven insights may not capture qualitative factors: The analysis is based on quantitative data and may not account for qualitative factors like customer satisfaction, product quality, or brand reputation.

2. Lack of competitor analysis: The analysis focuses on internal sales data, but doesn't consider competitor sales, market share, or strategies that could impact business performance.









