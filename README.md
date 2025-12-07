# SQL-Chailogy
SQL Chailogy is a data analytics project built to analyze sales and customer behavior across chai outlets. Using joins, CTEs, window functions, and aggregations, it identifies best-selling items, peak hours, repeat customers, and overall store performance to support business decisions.

_____________________________________________________________________________________________________

📌 Project Overview
Tea outlets generate thousands of daily transactions. Without proper analysis, valuable patterns remain hidden.
This project transforms raw sales data into actionable insights like:
🔹 Best-selling items
🔹 Peak order hours
🔹 High-value & repeat customers
🔹 Store-wise performance
🔹 Category contribution to revenue
The objective is to support data-driven decision making for marketing, operations, and menu optimization.
_____________________________________________________________________________________________________

🗂 Dataset Details
The project contains multiple tables (examples):

Table Name	                      Description
customers	                        Customer profile with demographics
orders	                          Order header data with timestamps
order_items	                      Line-level purchases
products	                        Menu items and pricing
stores	                          Chai outlet locations

_____________________________________________________________________________________________________

❓ Business Questions Solved
Some key analyses performed:

Query	                            Business Insight
Total revenue & order count	      Overall performance
Best-selling items	              Inventory planning
Top customers by spend	          Loyalty & retention
Peak ordering hours	              Workforce scheduling
Store-wise ranking	              Branch performance

_____________________________________________________________________________________________________
🧠 Core SQL Skills Used
SQL Concept	              Usage
Joins	                    Combine multiple tables
CTEs	                    Clean step-wise transformations
Subqueries	              Layered calculations
Window Functions	        Ranking & cumulative revenue
CASE	                    Rule-based classification
Grouping & Aggregation	  Revenue metrics

_____________________________________________________________________________________________________

📊 Sample SQL Queries
🔹 Best-selling products
SELECT p.product_name, SUM(oi.quantity) AS total_sold
FROM order_items oi
JOIN products p ON oi.product_id = p.product_id
GROUP BY p.product_name
ORDER BY total_sold DESC;

🔹 Peak order hours
SELECT EXTRACT(HOUR FROM order_time) AS hour, COUNT(*) AS order_count
FROM orders
GROUP BY hour
ORDER BY order_count DESC;

🔹 Repeat customers
SELECT customer_id, COUNT(order_id) AS total_orders
FROM orders
GROUP BY customer_id
HAVING COUNT(order_id) > 1;

_____________________________________________________________________________________________________

🚀 Insights Summary

✔ Dessert Chai & Kulhad Chai are the highest revenue-generating items
✔ Peak transaction time: 6 PM – 9 PM
✔ Customers aged 18–30 form the largest spending segment
✔ Store-3 contributes the highest revenue due to urban footfall
✔ 41% of revenue comes from repeat customers

🧰 Tech Stack
Layer	          Tools
Database	      MySQL / PostgreSQL
Analysis	      Advanced SQL
Visualization	  Excel / Power BI (optional export)

_____________________________________________________________________________________________________

