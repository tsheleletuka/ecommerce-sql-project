# ECommerceDB SQL Project

This project sets up a basic **E-Commerce Database** schema using SQL Server. It simulates a simplified e-commerce system involving customers, products, orders, and order items, along with a set of insightful analytical queries.

## 📦 Project Overview

The goal of this project is to:
- Model a simple e-commerce transactional system.
- Insert sample data for testing and analysis.
- Write SQL queries to extract meaningful insights such as total sales, customer behavior, and top-performing products.

## 🗂️ Database Schema

The database consists of four main tables:

1. **Customers** – Stores customer details.
2. **Products** – Stores product information.
3. **Orders** – Stores customer order details.
4. **Order_Items** – Links products to orders with quantity and pricing.

### ERD (Entity Relationship Diagram)
- `Customers` ⟶ `Orders` (1:M)
- `Orders` ⟶ `Order_Items` (1:M)
- `Products` ⟶ `Order_Items` (1:M)

## 🧾 SQL Features Covered

- `CREATE DATABASE`, `CREATE TABLE` statements
- `PRIMARY KEY`, `FOREIGN KEY` constraints
- `INSERT INTO` for seeding data
- `JOIN`, `GROUP BY`, `HAVING`, `ORDER BY`
- Aggregate functions: `SUM`, `AVG`, `COUNT`
- Filtering top results using `TOP`

## 📊 Key Analytical Queries

| Query Description                      | Output |
|---------------------------------------|--------|
| 💰 Total sales by category            | Sales grouped by product category |
| 🔥 Most purchased product             | Product with highest total quantity sold |
| 👑 Top 5 spending customers           | Customers who spent the most |
| 📈 Monthly sales trend                | Revenue trend over time |
| 💵 Average order value                | Mean value of all orders |
| 🔁 Repeat customers                   | Customers with multiple orders |
| 🥇 Top-selling category by revenue    | Best performing product category |
| 🏆 Best month in revenue              | Highest earning month |
| 📦 Number of orders per customer      | Customer engagement level |

## 🛠️ Installation

To run this project:
1. Open SQL Server Management Studio (SSMS) or your preferred SQL client.
2. Run the script step-by-step or as a batch.
3. Explore and modify the queries for deeper analysis.

> ⚠️ Note: There's a **syntax error** in the `Products` table — a comma at the end of the `price` line needs to be removed.

## ✅ Sample Fix for the Products Table

```sql
CREATE TABLE Products (
    product_id      INT PRIMARY KEY,
    product_name    VARCHAR(100),
    category        VARCHAR(50),
    price           DECIMAL(10, 2)  -- ✅ Removed trailing comma
);
