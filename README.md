# Sales-Insights-using-PowerBI-SQL

SQL Commands used are:

1. **Show all customer records**

`SELECT * FROM customers;`

2. **Show the total number of customers**

`SELECT COUNT(*) AS total_customers FROM customers;`

3. **Show transactions for the Chennai market (market code for Chennai is Mark001):**

`SELECT * FROM transactions WHERE market_code = 'Mark001';`

4. **Show distinct product codes that were sold in Chennai:**

`SELECT DISTINCT product_code FROM transactions WHERE market_code = 'Mark001';`

5. **Show transactions where the currency is US dollars:**

`SELECT * FROM transactions WHERE currency = 'USD';`

6. **Show transactions in 2020 joined by the date table:**

`SELECT t.*, d.*`

`FROM transactions t`

`INNER JOIN date d ON t.order_date = d.date`

`WHERE d.year = 2020;`

7. **Show total revenue in the year 2020:**

`SELECT SUM(t.sales_amount) AS total_revenue`

`FROM transactions t`

`INNER JOIN date d ON t.order_date = d.date`

`WHERE d.year = 2020`

`AND (t.currency = 'INR' OR t.currency = 'USD');`

8. **Show total revenue in January 2020:**

`SELECT SUM(t.sales_amount) AS january_revenue`

`FROM transactions t`

`INNER JOIN date d ON t.order_date = d.date`

`WHERE d.year = 2020`

`AND d.month_name = 'January'`

`AND (t.currency = 'INR' OR t.currency = 'USD');`

9. **Show total revenue in Chennai for the year 2020:**

`SELECT SUM(t.sales_amount) AS chennai_revenue`

`FROM transactions t`

`INNER JOIN date d ON t.order_date = d.date`

`WHERE d.year = 2020`

`AND t.market_code = 'Mark001';`
