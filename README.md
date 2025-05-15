# Pizza Sales SQL Analysis

This project is a SQL-based data analysis of a fictional pizza sales dataset. The goal is to explore sales performance, popular pizza types, customer order behavior, and generate insights to help improve business decisions.

## Project Files

- Pizza_sales_pdf_compressed_final.pdf – Project report or summary in PDF format.
- order_details.xlsx – Contains details about each order item including pizza type and quantity.
- orders (1).csv – Order metadata including order ID and date.
- pizza_types.xlsx – Lists different pizza types and their categories/ingredients.
- pizzas.xlsx – Information about each pizza including type, size, and price.

## Objectives

- Clean and prepare data for SQL queries.
- Join multiple tables to perform in-depth sales analysis.
- Identify top-selling pizzas by revenue and quantity.
- Analyze sales trends by time (day, week, month).
- Generate insights to recommend business improvements.

## Tools Used

- SQL (MySQL / PostgreSQL / SQLite)
- Excel / CSV for data source
- Power BI / Tableau (if visualization used)

## How to Use

1. Import the .xlsx and .csv files into your SQL environment.
2. Use JOINs to combine tables and run your analysis.
3. Check the PDF report for sample queries and results.

## Sample SQL Query

```sql
SELECT pt.category, SUM(od.quantity * p.price) AS total_revenue
FROM order_details od
JOIN pizzas p ON od.pizza_id = p.pizza_id
JOIN pizza_types pt ON p.pizza_type_id = pt.pizza_type_id
GROUP BY pt.category
ORDER BY total_revenue DESC;
