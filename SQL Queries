-- SQL Retail Sales Analysis 

CREATE DATABASE sales;
USE sales;
DROP TABLE IF EXISTS retail_sales;

-- Create TABLE

CREATE TABLE retail_sales
(
	transaction_id INT PRIMARY KEY,	
	sale_date DATE,	 
	sale_time TIME,	
	customer_id	INT,
	gender	VARCHAR(15),
	age	INT,
	category VARCHAR(15),	
	quantity	INT,
	price_per_unit FLOAT,	
	cogs	FLOAT,
	total_sale FLOAT
);

SELECT * FROM retail_sales;

SELECT * FROM retail_sales limit 10;

SELECT COUNT(*) FROM retail_sales;

-- Data Cleaning

SELECT * FROM retail_sales
WHERE 
    transaction_id IS NULL
    OR
    sale_date IS NULL
    OR 
    sale_time IS NULL
    OR
    gender IS NULL
    OR
    category IS NULL
    OR
    quantity IS NULL
    OR
    cogs IS NULL
    OR
    total_sale IS NULL;


SET SQL_SAFE_UPDATES = 0;
    
DELETE FROM retail_sales
WHERE 
    transaction_id IS NULL
    OR
    sale_date IS NULL
    OR 
    sale_time IS NULL
    OR
    gender IS NULL
    OR
    category IS NULL
    OR
    quantity IS NULL
    OR
    cogs IS NULL
    OR
    total_sale IS NULL;   

SET SQL_SAFE_UPDATES = 1;

SELECT * FROM retail_sales;

-- Data Exploration

-- How many sales we have?

SELECT COUNT(*) AS total_records FROM retail_sales;

-- How many uniuque customers we have ?

SELECT COUNT(DISTINCT customer_id) as unique_customer FROM retail_sales;

-- Write a query to find all unique product categories.

SELECT DISTINCT category FROM retail_sales;

-- Data Analysis & Business Key Problems & Answers

-- My Analysis & Findings

SELECT * FROM retail_sales;

-- Q.1 Write a SQL query to retrieve all columns for sales made on '2022-11-05'.

SELECT * 
FROM retail_sales 
WHERE sale_date = '2022-11-05';

/* Q.2 Write a SQL query to retrieve all transactions where the category is 'Clothing' and the quantity 
sold is more than 3 in the month of Nov-2022 */

SELECT * FROM retail_sales 
WHERE category = 'Clothing' 
AND quantity > 3
AND DATE_FORMAT(sale_date, '%Y-%m') = '2022-11';


-- Q.3 Write a SQL query to calculate the total sales (total_sale) for each category.

SELECT 
    category,
    SUM(total_sale) AS total_sales,
    COUNT(*) AS total_orders 
FROM retail_sales 
GROUP BY category;


-- Q.4 Write a SQL query to find the average age of customers who purchased items from the 'Beauty' category.

SELECT category, ROUND(AVG(age),0) AS average_age 
FROM retail_sales 
WHERE category = 'Beauty';

-- Q.5 Write a SQL query to find all transactions where the total_sale is greater than 1000.

SELECT * 
FROM retail_sales 
WHERE total_sale > 1000;

/* Q.6 Write a SQL query to find the total number of transactions (transaction_id) made by each gender in
each category. */

SELECT 
    category, 
    gender, 
    COUNT(transaction_id) AS total_transaction 
FROM retail_sales 
GROUP BY category, gender
ORDER BY 1;

/* Q.7 Write a SQL query to calculate the average sale for each month. Find out best selling 
month in each year */


SELECT * FROM (
    SELECT 
        YEAR(sale_date) as year,
        MONTH(sale_date) as month,
        ROUND(AVG(total_sale), 2) as avg_sale,
        RANK() OVER(PARTITION BY YEAR(sale_date) ORDER BY AVG(total_sale) DESC) as rank_num
    FROM retail_sales
    GROUP BY 1, 2
) as t1
WHERE rank_num = 1;


-- Q.8 Write a SQL query to find the top 5 customers based on the highest total sales 

SELECT 
    customer_id,
	SUM(total_sale) as total_sales
FROM retail_sales
GROUP BY 1
ORDER BY 2 DESC
LIMIT 5;

-- Q.9 Write a SQL query to find the number of unique customers who purchased items from each category.


SELECT 
    category, 
    COUNT(DISTINCT customer_id) AS total_unique_customers 
FROM retail_sales 
GROUP BY category;

-- Q.10 Write a SQL query to create each shift and number of orders 
-- (Example Morning <=12, Afternoon Between 12 & 17, Evening >17)

WITH hourly_sales AS (
    SELECT *,
        CASE
            WHEN HOUR(sale_time) < 12 THEN 'Morning'
            WHEN HOUR(sale_time) BETWEEN 12 AND 17 THEN 'Afternoon'
            ELSE 'Evening'
        END AS shift
    FROM retail_sales
)
SELECT 
    shift,
    COUNT(*) as total_orders    
FROM hourly_sales
GROUP BY shift;

select * from retail_Sales;

DESCRIBE retail_sales;

-- Business Insights (Summary KPIs)

-- Total records (transactions)
SELECT COUNT(*) AS total_transactions
FROM retail_sales;

-- Unique customers
SELECT COUNT(DISTINCT customer_id) AS unique_customers
FROM retail_sales;

-- Total revenue
SELECT ROUND(SUM(total_sale), 2) AS total_revenue
FROM retail_sales;

-- Total categories
SELECT COUNT(DISTINCT category) AS total_categories
FROM retail_sales;

SELECT 
  category,
  ROUND(100 * SUM(total_sale) / (SELECT SUM(total_sale) FROM retail_sales), 1) AS revenue_share_pct
FROM retail_sales
GROUP BY category
ORDER BY revenue_share_pct DESC;



