## Project Overview

**Project Title:** Retail Sales Analysis  
**Level:** Beginner  
**Database:** sales   

### Project Context  
Retail businesses generate thousands of transactions daily, but raw transaction data is not directly useful unless it is properly structured and cleaned. In this project, I worked with retail sales transaction data that needed to be organized into a database and validated for missing/invalid records so that accurate analysis could be performed. The goal was to understand **category performance**, **customer behaviour**, and **time-based sales trends** using SQL.

### Primary Goal  
The primary goal of this project is to analyze retail sales data and uncover actionable insights that can support business decision-making. I focused on identifying sales patterns, revenue drivers, customer segments, and operational time windows (shifts) that can be used for better planning, marketing, and performance tracking.

### Data Foundation (What I Built)  
To build a strong base for analysis, I:
- Created a database (`sales`) and a transaction table (`retail_sales`) containing customer, product, and financial attributes (transaction date/time, customer demographics, category, quantity, unit price, COGS, and total sale).  
- Validated the structure and performed initial checks (sample records, row counts, basic exploration).  
- Performed **data cleaning (Null Handling)** by identifying and removing records with missing values in key business fields to ensure reliable analysis and trustworthy results.

### Exploratory Data Analysis (EDA)  
After cleaning, I performed EDA to understand the dataset at a high level, including:
- Total number of sales transactions available for analysis  
- Number of unique customers in the dataset  
- Product categories present (to understand product diversity and category-level behaviour)

### Business Questions & Analysis Approach  
Once the data foundation was ready, I answered a set of real business questions using SQL. The queries in this project cover:
- Date-based transaction retrieval (to track specific-day performance)
- Category-based filtering and monthly conditions (e.g., Clothing bulk purchases in Nov-2022)
- Category-level performance metrics (total sales and order volume)
- Customer demographic insights (e.g., average age of Beauty customers)
- Identification of high-value transactions (total_sale > 1000)
- Gender × category transaction patterns (to support targeted marketing)
- Monthly trend analysis and identifying the best-performing month each year (using ranking logic)
- Top customer identification (top 5 customers by total spending)
- Unique customers per category (to understand category reach)
- Shift-based order distribution (Morning/Afternoon/Evening) based on sale time (to support staffing and operational planning)

### Key Summary (What the Analysis Shows)  
This project converts raw retail transaction records into meaningful insights such as:
- Overall business scale (transactions, customers, revenue, categories)
- Which categories drive the most revenue vs. the most orders
- Which customer segment appears more active in certain categories
- When demand peaks during the day (shift analysis) and what that means operationally

Overall, this is a complete beginner-friendly SQL case study that demonstrates an end-to-end workflow: **database setup → cleaning → EDA → business question solving → insight generation**.
