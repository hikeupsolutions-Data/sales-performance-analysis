# Sales Performance Analysis - SQL (BigQuery)
SQL analysis of sales data using BigQuery
### Overview
This project analyses sales data to identify top customers, product performance, and monthly revenue trends.
### Tools Used
SQL, Google BigQuery
### Key Insights
- Which customers generated the most revenue
- Which products were underperforming
- How sales trended month to month
## Queries 
This query identifies the top customers by total revenue - helping a business understand who their most valuable customers are.
```sql
SELECT
 customer_id, 
 SUM(quantity * price) AS Revenue
FROM sales
GROUP BY
 customer_id
ORDER BY
 Revenue DESC;
```
This query show the monthly revenue trend with the best perfroming month at the top. 
```sql
SELECT
 EXTRACT(YEAR FROM order_date) AS year,
 EXTRACT(MONTH FROM order_date) As month,
 SUM (quantity * price) AS Revenue
FROM sales
GROUP BY 
       year, month
ORDER BY
  Revenue DESC
```
This query shows the total revenue by category with the best performing category at the top. 
```sql
SELECT
 category,
 SUM(quantity * price) AS Revenue
FROM sales
GROUP BY
 category
ORDER BY
Revenue DESC
```
