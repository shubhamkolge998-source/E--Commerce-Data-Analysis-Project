🛍️ Olist E-Commerce Data Analysis Project

This project focuses on analyzing the Brazilian Olist E-Commerce Dataset to uncover key insights into sales performance, customer behavior, delivery performance, and product reviews.

The end-to-end data pipeline involves data cleaning in Excel, data transformation using Power Query, data analysis with PostgreSQL, and dashboard visualization using Power BI.

📊 Project Overview
🎯 Objective

To perform data analysis on Olist's e-commerce data to understand sales trends, customer behavior, delivery performance, and review patterns.

🧰 Tools Used

📝 Excel – Initial data cleaning and formatting

⚡ Power Query – Data transformation and loading

🗃️ PostgreSQL – Writing and executing SQL queries for in-depth analysis

📈 Power BI – Building interactive dashboards for visualization

🧱 Dataset Structure

The project uses multiple CSV tables from the Olist dataset:

Table Name	Description
olist_customers_dataset	Customer details such as city, state, and unique IDs
geolocation_dataset	Location coordinates (lat/lng) mapped to zip codes
olist_order_items_dataset	Products per order, price, freight value
olist_order_payments_dataset	Payment details including type, value, installments
olist_order_reviews_dataset	Customer reviews and scores
olist_orders_dataset	Order lifecycle details and timestamps
olist_products_dataset	Product metadata including weight, dimensions
olist_sellers_dataset	Seller details such as location
olist_product_category_name_translation	Translation of product category names to English
🛠️ Data Cleaning & Preparation
📝 Excel

Removed duplicates and null values

Standardized column names

Fixed data type issues (e.g., numeric vs. text)

⚡ Power Query

Combined multiple Excel files where needed

Cleaned inconsistent category names

Prepared data for PostgreSQL import

🗃️ PostgreSQL

Created tables with appropriate data types

Imported CSV data into the tables using COPY commands

Applied constraints and indexing where necessary

📌 SQL Analysis

All analysis was performed using PostgreSQL.
Below are some key queries used in the project:

🧮 Sales Analysis
📅 Yearly Total Sales
SELECT EXTRACT(YEAR FROM o.order_purchase_timestamp) AS year, 
       SUM(p.payment_value) AS total_sales 
FROM olist_orders_dataset o 
JOIN olist_order_payments_dataset p 
ON o.order_id = p.order_id 
GROUP BY year 
ORDER BY total_sales;

🛍️ Sales by Product Category
SELECT p.product_category_name, 
       SUM(o.price) AS total_sales, 
       COUNT(o.order_item_id) AS total_orders 
FROM olist_products_dataset p 
JOIN olist_order_items_dataset o 
ON p.product_id = o.product_id 
GROUP BY p.product_category_name 
ORDER BY total_sales DESC;


🏙️ Top 10 Cities by Purchase Value

🧾 Top 10 Sellers by Revenue

💳 Top Payment Types

🚚 Delivery Performance

📦 On-time vs Delayed Orders

⏰ Average Delivery Time by State

📊 Percentage of Delayed vs On-Time Deliveries

👥 Customer & Review Insights

🧍 Unique Customers per City

🔁 Repeat Customers Count

⭐ Average Review Score by Product Category

👎 Top 10 Categories with Lowest Ratings

📊 Power BI Dashboard
📌 Key Dashboard Pages

🧭 Overview – High-level KPIs like Total Sales, Orders, Revenue Trend, and Payment Breakdown.

🏙️ Geographical View – Total payment value by state & city on interactive map visual.

📦 Product & Seller Performance – Revenue by category, Top sellers, Average price & freight per seller.

⏰ Delivery Analysis – On-time vs delayed orders, average shipping times, top slow-delivery states.

⭐ Customer Reviews – Average review scores, top & bottom-rated categories.

✨ Features Used

Slicers for dynamic filtering (Year, State, Category)

KPI Cards for quick metrics

Bar & Line charts for trends

Maps using Latitude/Longitude fields

Tooltips for detailed drill-down

🧠 Key Insights

📆 2018 recorded the highest total sales compared to other years.

🏙️ Top cities and states contribute a significant portion of total revenue.

💳 Credit Card was the most commonly used payment method.

🚚 A notable percentage of orders were delivered later than estimated.

⭐ Categories like electronics and furniture had lower average review scores compared to books and clothing.

🚀 How to Use This Project

Clone the repository

Import datasets into PostgreSQL

Run SQL queries for analysis

Open the Power BI dashboard file for interactive visualizations

🧑‍💻 Author

Shubham Kolge
📍 Data Analyst | Power BI | SQL | Advance Excel
💼 LinkedIn: https://www.linkedin.com/in/shubham-kolge-67a332211

📧 Contact: Kolgeshubham14@gmail.com

📝 License

This project is licensed under the MIT License — feel free to use and modify.

✅ Tags

#PowerBI #PostgreSQL #SQL #Excel #DataAnalysis #Dashboard #Ecommercexcel #DataAnalysis #Dashboard #Ecommercealysis #Dashboard #Ecommerce
