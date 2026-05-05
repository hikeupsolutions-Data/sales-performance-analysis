# sales-performance-analysis
SQL analysis of sales data using BigQuery
## Screenshots
![ SQL Query] (SQL-Example.pdf)
## Sales Performance Analysis – SQL (BigQuery)
### Overview
This project analyses sales data to identify top customers, product performance, and monthly revenue trends.
### Tools Used
SQL, Google BigQuery
### Key Insights
- Which customers generated the most revenue
- Which products were underperforming
- How sales trended month to month
SQL
SELECT
  customer_id,
  SUM (quantity * price) AS Total_Revenue
FROM
  Sales.Store_sales
GROUP BY
  customer_id
ORDER BY
  SUM (quantity * price) AS Total_Revenue DESC
