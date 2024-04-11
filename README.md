# Sales_insights_Data_Analysis_Project

## Problem Statement

An Indian Hardware Company deals in the business of delivering computer hardware and peripheral parts, and has several branches throughput India.The Sales Director of the company is in a dilemma in understanding business performance and reasons for gradual sales decline. Upon enquiring with the respective regional managers, he is provided with the numercial data in excel files.

## Objective

The Sales Director proposed for the creation of an intutive Power BI dashboard for converting raw numercial data into visual representation enabling them to make informed data-driven decisions.

## Solution Approach

1. Using MySQL the data is retrieved from the database and loaded into Power BI.
2. Data Cleaning and ETL(Extract, Transform and Load) in power query.
3. Data modelling (star schema).
4. Created metrics and utilised them in creating appropriate visualisations.

## Data Analysis queries using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001)

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai.

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars.

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table.

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020and transactions.market_code="Mark001";`


## Learning Outcomes

1. Handling real-life business datasets
2. Learned how to use MySQL in performing data analysis tasks
3. Importing from database to Power BI
4. Data cleaning and preparation for creating visualisations
5. Learned about some major practical DAX functions and measures.

## Final Dashboard
Check out the [dashboard](https://www.novypro.com/project/hardware-business-sales-insights)
<p align="center"><img width="100%" alt="Screenshot 2024-01-24 211508" src="https://github.com/sgpreetam/Sales_insights_Data_Analysis_Project/assets/139052998/32b073b5-d921-4b5c-90d4-0c659eeb6a3d"></p>p>

<p align="center"><img width="100%" alt="Screenshot 2024-01-24 211545" src="https://github.com/sgpreetam/Sales_insights_Data_Analysis_Project/assets/139052998/aa4e6786-7462-4c09-af29-b33544bee234"></p>
