1. Data Filtering (f)
The WHERE clause is applied first to Limit Results for Specific Time Periods. This acts as a scope-setter, ensuring that only data relevant to your target date range (e.g., Quarter 2 of 2019: BETWEEN '2019-04-01' AND '2019-06-30') is processed in the subsequent steps, which significantly improves efficiency and focuses the analysis.
2. Chronological Grouping (a, b)
I established the analytical framework using EXTRACT(YEAR FROM "Order Date") and EXTRACT(MONTH FROM "Order Date").
The GROUP BY Year, Month clause then organizes all filtered transactions into distinct monthly buckets. Every calculation that follows is performed independently for each of these buckets.
3. Key Metric Aggregation (c, d)
Revenue Calculation (c): Using SUM("Quantity Ordered" * "Price Each") AS Total_Revenue, you calculated the total gross income generated for each month. This is the ultimate measure of the monetary value delivered by the sales team.
Volume Calculation (d): Using COUNT(DISTINCT "Order ID") AS Volume, you calculated the number of unique transactions, or customer orders, placed each month. This metric is crucial for understanding sales activity and customer engagement, independent of the sales value.
4. Output Presentation (e)
The final ORDER BY Year, Month clause ensures the resulting report is presented in a logical, chronological sequence. This is vital for quickly identifying trends, seasonality, and month-over-month growth or decline in your sales performance.
