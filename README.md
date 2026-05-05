# sales-performance-analysis
SQL analysis of sales data using BigQuery
### Overview
This project analyses sales data to identify top customers, product performance, and monthly revenue trends.
### Tools Used
SQL, Google BigQuery
### Key Insights
- Which customers generated the most revenue
- Which products were underperforming
- How sales trended month to month
```sql
SELECT customer_id, 
       SUM(quantity * price) AS Revenue
FROM sales
GROUP BY customer_id
ORDER BY total_revenue DESC;
```
This query identifies the top customers by total revenue - helping a business understand who their most valuable customers are.
```sql
SELECT
 EXTRACT(YEAR FROM order_date) AS year,
 EXTRACT(MONTH FROM order_date) As month,
 SUM (quantity * price) AS Revenue
FROM sales
GROUP BY 
       year, month
ORDER BY
  REVENUE DESC
```
This query show the monthly revenue trend.
