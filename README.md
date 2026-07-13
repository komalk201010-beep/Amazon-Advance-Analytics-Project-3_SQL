# Amazon Advanced Analytics Project using SQL

## Overview

This project demonstrates how SQL can be leveraged to solve real-world business problems in an Amazon-style e-commerce environment. Instead of focusing solely on database queries, the project applies advanced SQL techniques to analyze customer behavior, sales performance, payment trends, inventory management, shipping operations, and seller performance.

The database simulates an end-to-end e-commerce ecosystem consisting of customers, orders, products, payments, shipping, sellers, and inventory. Using MySQL, the project transforms transactional data into actionable business insights that support data-driven decision making.

---

## Business Objective

Modern e-commerce platforms generate large volumes of transactional data every day. The objective of this project is to analyze this data to answer key business questions such as:

- Which customers generate the highest value?
- Which products contribute the most revenue?
- Which sellers consistently improve performance?
- How do refunds impact net revenue?
- Which products require inventory attention?
- How can customer purchasing behavior be leveraged for better retention?

---

## Database Schema

The project consists of nine interconnected tables representing different components of an e-commerce platform.

| Table | Description |
|--------|-------------|
| Customers | Customer information |
| Orders | Order details |
| Order Items | Products purchased in each order |
| Products | Product catalog |
| Category | Product categories |
| Payments | Payment method and status |
| Shipping | Shipping and return information |
| Sellers | Seller details |
| Inventory | Product stock availability |

The database is designed using **Primary Keys** and **Foreign Keys** to maintain relational integrity and simulate a production-ready transactional database.

---

## Project Workflow

```text
Raw Business Data
        │
        ▼
Database Design
        │
        ▼
Data Validation
        │
        ▼
Advanced SQL Analysis
        │
        ▼
Business Insights
        │
        ▼
Decision Support
```

---

## Business Problems Solved

### Customer Analytics

- Customers who purchased in January but not in February
- Repeat customers placing multiple orders within 30 days
- Customers inactive during the last 30 days
- Customer segmentation based on spending
- Complete RFM (Recency, Frequency, Monetary) analysis
- Average time between consecutive customer orders

---

### Revenue Analytics

- Monthly cumulative revenue trends
- Monthly net revenue after refunds
- Average order value by state
- Category-wise revenue contribution
- Category average order value compared with overall average
- Seller revenue per successful order

---

### Product & Inventory Analytics

- Products sold despite low inventory
- Products never ordered
- Products with high inventory but low sales
- Most frequently returned products
- Warehouse with the highest inventory value

---

### Seller Performance Analytics

- Monthly seller revenue
- Sellers showing continuous revenue growth
- Seller performance ranking

---

### Shipping & Operations Analytics

- Average shipping delay
- Return order analysis
- Delivery status performance

---

## Advanced SQL Concepts Demonstrated

This project showcases intermediate to advanced SQL techniques including:

- Common Table Expressions (CTEs)
- Window Functions
- LAG()
- DENSE_RANK()
- Aggregate Functions
- CASE Statements
- Correlated & Nested Subqueries
- Joins (INNER, LEFT)
- GROUP BY & HAVING
- Date Functions
- Conditional Aggregation
- Customer Segmentation
- Revenue Analysis
- Ranking & Running Totals

---

## Analytical Highlights

This project applies SQL to solve business-oriented analytical problems rather than simple database queries.

Key analytical techniques include:

- Customer retention analysis
- Repeat purchase analysis
- Payment failure analysis
- Revenue trend reporting
- Inventory optimization
- Return analysis
- Seller performance evaluation
- Warehouse inventory analysis
- Customer value segmentation
- RFM customer profiling

---

## Sample Business Query

```sql
-- Find each category's percentage contribution to total revenue

SELECT
    C.CATEGORY_NAME,
    CONCAT(
        ROUND(
            SUM(OI.TOTAL_PRICE) * 100 /
            (SELECT SUM(TOTAL_PRICE) FROM ORDER_ITEMS),
        2),
    '%') AS PERCENTAGE_CONTRIBUTION
FROM ORDER_ITEMS OI
JOIN PRODUCTS P
    ON OI.PRODUCT_ID = P.PRODUCT_ID
JOIN CATEGORY C
    ON C.CATEGORY_ID = P.CATEGORY_ID
GROUP BY C.CATEGORY_NAME
ORDER BY PERCENTAGE_CONTRIBUTION DESC;
```

---

## Skills Demonstrated

- SQL Programming
- Business Analytics
- Data Analysis
- Relational Database Design
- Customer Analytics
- Revenue Analytics
- Inventory Analysis
- Sales Analytics
- Window Functions
- Data Transformation
- Business Intelligence

---

## Technologies Used

- MySQL
- MySQL Workbench
- Git
- GitHub

---

## Repository Structure

```text
Amazon-Advance-Analytics-Project-3_SQL/
│
├── amazon_project.sql
├── README.md
└── Dataset
```

---

## Learning Outcomes

Through this project, I strengthened my ability to:

- Design and query relational databases
- Solve complex business problems using SQL
- Apply advanced analytical SQL techniques
- Build reusable analytical queries
- Convert transactional data into actionable business insights
- Perform customer and revenue analytics for business decision-making

---

## Future Enhancements

- Develop an interactive Power BI dashboard
- Build SQL Views for automated reporting
- Implement Stored Procedures and Triggers
- Add predictive sales forecasting using Python
- Extend customer segmentation with machine learning techniques

---

## About the Project

This project is part of my Business Analytics portfolio and demonstrates the application of SQL to solve real-world analytical problems across customer behavior, revenue optimization, inventory management, logistics, and seller performance in an e-commerce setting.

---

## Author

**Komal**

Business Analytics | SQL | Python | Excel | Power BI
