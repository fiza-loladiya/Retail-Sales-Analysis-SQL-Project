# SQL Retail Sales Analysis (MySQL)

## Project Overview
This is my first SQL portfolio project where I worked with retail transaction data and used **MySQL** to build a clean database, perform **data cleaning**, run **EDA (Exploratory Data Analysis)**, and answer real business questions through SQL queries.

The goal was simple: take raw retail sales data and turn it into insights that can support better decisions around **category performance, customer behavior, and time-based trends**.

---

## Objectives
- Create a structured database + table for retail transactions
- Check data quality and remove incomplete records (NULL handling)
- Perform EDA to understand dataset scale, customers, and categories
- Solve business questions using SQL (filters, aggregation, CTEs, window functions)
- Summarize key KPIs and insights for decision-making

---

## Tech Stack
- **MySQL (8.0+)**  
  > Window functions (`RANK() OVER`) and CTE (`WITH`) require MySQL 8+

---

## Database & Table
**Database:** `sales`  
**Table:** `retail_sales`

### Schema
- `transaction_id` (PK)
- `sale_date`, `sale_time`
- `customer_id`, `gender`, `age`
- `category`, `quantity`
- `price_per_unit`, `cogs`, `total_sale`

---

## Data Cleaning (NULL Handling)
I checked missing values in key columns and removed incomplete records to ensure analysis is based only on valid transactions.

Key steps:
- Identify NULLs using a `WHERE ... IS NULL` check
- Temporarily disable safe updates
- Delete incomplete rows
- Re-enable safe updates

---

## EDA (Exploratory Data Analysis)
I ran quick exploration queries to understand:
- total number of transactions
- unique customers
- distinct product categories

---

## Business Questions Answered (Q1–Q10)
This project answers 10 business-focused questions, including:
1. Sales on a specific date (e.g., 2022-11-05)
2. Clothing bulk purchases in Nov 2022
3. Category-wise total sales + order count
4. Avg age of Beauty customers
5. High-value transactions (total_sale > 1000)
6. Gender-wise category transactions
7. Best-selling month per year (avg sale using window function)
8. Top 5 customers by total sales
9. Unique customers per category
10. Shift analysis (Morning/Afternoon/Evening) using CTE

---

## Key KPIs (From the final cleaned dataset)
- **Total Transactions:** 1,987  
- **Total Revenue:** 908.23K  
- **Unique Customers:** 155  
- **Product Categories:** 3 (Clothing, Beauty, Electronics)

---

## Key Insights
- **Electronics** contributes the highest revenue, while **Clothing** generates the highest number of orders (different pricing vs volume strategy).
- Beauty category attracts a more mature customer group (avg age ≈ 40).
- High-value orders (total_sale > 1000) form a smaller portion of transactions but contribute heavily to revenue.
- **Evening shift** has the highest order volume (peak demand), compared to Morning and Afternoon.

---

## Recommendations
Based on the patterns observed:
- Prioritize inventory planning for key categories (especially during high-demand months)
- Increase staffing focus during Afternoon/Evening peak hours
- Run targeted campaigns in weaker months to reduce seasonal dips
- Create loyalty / personalized offers for high-value customers

---

## Limitations
- Dataset is limited in size and not real-time
- No store/location field → can’t compare regional performance
- Profit insights are limited (COGS exists, but discounts/ops costs not detailed)
- No customer history → retention/LTV analysis not possible

---

## How to Run
1. Create database and table
2. Load/insert the dataset into `retail_sales`
3. Run queries in this order:
   - setup & schema
   - cleaning
   - EDA
   - business questions Q1–Q10
   - KPI summary

---


