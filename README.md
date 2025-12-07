# E-Commerce Data Analysis Project
- By: Olusesan Samuel
- Data Source: [Here](https://datadna.onyxdata.co.uk/challenges/november-2025-datadna-ecommerce-analytics-challenge/)

# Project Overview
This project analyzes customer behavior, product performance, and sales patterns using Power BI and Power Query. It is part of the DataDNA Dataset Challenge, where the goal is to uncover insights that support data-driven decision-making for an e-commerce business.

# Datasets Used
- Products Table — 101 product records
- Customers Table — 4,000 customers
- Events Table — 48,000 customer events

# Tools & Skills Applied
- Power BI: Data visualization, relationship modeling, dashboard creation
- Power Query: Data cleaning, transformation, merging
- DAX: Calculated columns & measures
- Data Analysis: Customer segmentation, product performance ranking, sales trend evaluation

# Data Preparation
- Using Power Query, the dataset was cleaned by:
- Removing duplicates
- Replace numbers with actual words using the data dictionary 
- Standardizing text fields
- Extracting Country Currency with their average country price 
- Formatting each column to it datatype
<img width="2514" height="872" alt="Raw Data Image" src="https://github.com/user-attachments/assets/6e380a0e-9d91-497b-89be-0c18375c00fc" />

# Data Analysis Expressions
### The average price in each country
- `DAX = AVERAGE(Events[unit_price_local])`
- `Total Price with Symbol = 
    VAR Curr = SELECTEDVALUE(Events[currency])
    VAR Amount = [ASP]
        RETURN
        IF(ISBLANK(Curr),"--",
            Curr & " " & FORMAT(Amount,"0.0")
           )  `
### To count the no. of customers, events, products, refunds
- `Customer_Count = COUNT(Customers[customer_id])`
- `No. of events = COUNT(Events[event_id])`
- `Total_Products = COUNT(Products[product_id])`
- `Refunds_Counts = CALCULATE(COUNTROWS(Events),Events[is_refunded] = TRUE)`
### To calculate the sum of revenue
- `Net_Revenue = SUM(Events[net_revenue_usd])`
### To design the sparkline on my card
- `Net_Revenue = SUM(Events[net_revenue_usd])`
  

# Objectives
- Analyze customer engagement patterns
- Identify best-selling and underperforming products
- Evaluate how events (views, carts, purchases) translate into sales
- Build an interactive dashboard for business insights

 # Key Insights (Summary)
- High customer engagement but low conversion for certain categories
- Specific products drive most revenue
- Customer behavior varies by time and product type
- Opportunities exist to improve marketing and product visibility

# Recommendations
- Improve conversion on high-view, low-purchase products
- Increase marketing effort on top-performing products
- Boost underperforming product categories with targeted promotions
- Optimize the customer journey from view → cart → purchase
- Schedule ads and promotions during peak purchase hours
- Implement personalized product recommendations
- Introduce loyalty and retention programs for existing customers
<img width="1512" height="866" alt="Page 1" src="https://github.com/user-attachments/assets/2364f2c5-0c75-4082-af60-167e1b008334" />
<img width="1524" height="863" alt="Page 2" src="https://github.com/user-attachments/assets/558e9a12-b8b9-4677-b3e5-4d2c8e2fab81" />
<img width="1522" height="866" alt="Page 3" src="https://github.com/user-attachments/assets/c22a334d-ac6d-40fb-83cf-e7d2d6c2f6b7" />




# About the Author
Olusesan Samuel is a data-driven aspiring data analyst skilled in Power BI, Excel, and data storytelling.

# Support
If you find this project helpful, kindly give it a star on GitHub.
