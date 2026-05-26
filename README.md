# Amazon SQL Analysis Project

## Project Overview
This project is an end-to-end SQL analysis of an Amazon-style e-commerce database.  
The project focuses on solving real-world business problems related to customers, orders, payments, inventory, shipping, and seller performance using MySQL.

---

## Database Design

The database consists of the following tables:

- Customers
- Orders
- Order Items
- Products
- Category
- Payments
- Shipping
- Sellers
- Inventory

The schema was designed using primary keys and foreign key relationships to simulate a real e-commerce ecosystem.

---

## Objectives

The project aims to answer important business questions such as:

- Customer retention analysis
- Repeat customer behavior
- Payment failure analysis
- Revenue trend analysis
- Inventory management insights
- Seller performance evaluation
- Product return analysis
- Customer segmentation using RFM analysis

---

## SQL Concepts Used

This project demonstrates:

- JOINS
- Common Table Expressions (CTEs)
- Window Functions
- Aggregate Functions
- CASE Statements
- Subqueries
- GROUP BY & HAVING
- Date Functions
- Ranking Functions
- Customer Segmentation Logic

---

## Business Problems Solved

### Customer Analytics
- Customers who ordered in January but not February
- Repeat customers within 30 days
- Customers inactive in last 30 days
- RFM customer segmentation

### Revenue Analytics
- Monthly cumulative revenue
- Net revenue after refunds
- Category contribution to revenue
- Average order value analysis

### Product & Inventory Analytics
- Products with low inventory but high sales
- Products never ordered
- Most returned products
- High stock but low sales products

### Seller Analytics
- Seller revenue performance
- Continuous monthly seller growth

### Shipping & Operations Analytics
- Average shipping delays
- Return order analysis

---

## Sample Query
```
-- For each category, compare its average order value with the overall average order value.
SELECT 
      C.CATEGORY_NAME, 
      ROUND(AVG(OI.TOTAL_PRICE), 2) AS AOV
FROM CATEGORY C
  JOIN PRODUCTS P ON C.CATEGORY_ID = P.CATEGORY_ID 
  JOIN ORDER_ITEMS OI ON P.PRODUCT_ID = OI.PRODUCT_ID
WHERE OI.TOTAL_PRICE >= (
		         SELECT AVG(TOTAL_PRICE) AS OVERALL_AOV
                            FROM ORDER_ITEMS
			)
GROUP BY C.CATEGORY_NAME
ORDER BY ROUND(AVG(OI.TOTAL_PRICE), 2) DESC;
```

---

## Key Insights

- Certain payment methods showed higher failure rates.
- Some products experienced high sales despite low inventory.
- Refunds significantly affected monthly net revenue.
- Customer spending patterns helped identify high-value customers.

---

## Tools Used

- MySQL
- MySQL Workbench
- GitHub

---

## Project Structure

```text
amazon-sql-analysis-project/
│
├── amazon_project.sql
├── README.md
└── screenshots/
```

---

## Author

Komal  
Data and Business Analyst