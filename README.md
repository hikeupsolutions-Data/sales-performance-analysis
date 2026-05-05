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
       SUM(revenue) AS total_revenue
FROM sales
GROUP BY customer_id
ORDER BY total_revenue DESC;
```
