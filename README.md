# Online Sales Analysis

This project focuses on analyzing the online sales data to generate insights such as monthly revenue and order volume. The data includes order details like order date, amount, and product ID.

## Dataset

The dataset, named `online_sales_data`, contains the following columns:

- `order_date`: Date of the order.
- `amount`: The total amount for the order.
- `product_id`: The ID of the product sold.

### Sample Data

| order_date | amount | product_id |
|------------|--------|------------|
| 2023-01-10 | 150.00 | 101        |
| 2023-01-15 | 200.00 | 102        |
| 2023-02-01 | 120.00 | 103        |
| 2023-02-20 | 180.00 | 104        |
| 2023-03-05 | 250.00 | 105        |
| 2023-03-15 | 300.00 | 106        |
| 2023-03-18 | 220.00 | 107        |
| 2023-04-10 | 350.00 | 108        |
| 2023-04-25 | 400.00 | 109        |

## Analysis

- **Monthly Revenue**: Total revenue for each month.
- **Order Volume**: Number of distinct products sold each month.

### SQL Query Example

To analyze monthly revenue and order volume:

```sql
SELECT
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(*) AS order_volume
FROM
    online_sales_data
GROUP BY
    EXTRACT(YEAR FROM order_date),
    EXTRACT(MONTH FROM order_date)
ORDER BY
    year, month;
