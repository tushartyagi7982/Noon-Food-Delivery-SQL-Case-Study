# 🍽️ Food Delivery SQL Case Study

## 📌 Overview

This project is a **SQL-based case study** designed to simulate real-world business problems in a **food delivery platform** (similar to Swiggy/Zomato).

The dataset contains order-level information including:

* Customer details
* Order timestamps
* Restaurant & cuisine
* Order status
* Promo usage

The goal is to solve **analytical business questions** using SQL.

---

## 🗂️ Dataset Details

### Table: `orders`

| Column Name     | Description                           |
| --------------- | ------------------------------------- |
| Order_id        | Unique order identifier               |
| Customer_code   | Unique customer ID                    |
| Placed_at       | Order timestamp                       |
| Restaurant_id   | Restaurant identifier                 |
| Cuisine         | Cuisine type                          |
| Order_status    | Status of order (Delivered/Cancelled) |
| Promo_code_Name | Promo code used (if any)              |

---

## 🧠 Business Problems Solved

### 1️⃣ Top Restaurant by Cuisine

**Goal:** Identify the most popular outlet for each cuisine without using `TOP` or `LIMIT`.

**Approach:**

* Aggregate orders by cuisine & restaurant
* Use `ROW_NUMBER()` window function

---

### 2️⃣ Daily New Customer Acquisition

**Goal:** Track how many new customers are acquired each day.

**Approach:**

* Find first order date per customer
* Group by date

---

### 3️⃣ One-Time Customers (Jan 2025)

**Goal:** Identify users who:

* Ordered only once in Jan 2025
* Never ordered again

---

### 4️⃣ Inactive Customers with Promo Acquisition

**Goal:** Find customers who:

* Haven’t ordered in last 7 days (as of 31-Mar-2025)
* Were acquired >1 month ago
* Used a promo on their first order

---

### 5️⃣ Target Customers on Every 3rd Order

**Goal:** Help Growth team trigger campaigns on every 3rd order.

**Approach:**

* Assign order sequence using `ROW_NUMBER()`
* Filter multiples of 3

---

### 6️⃣ Promo-Only Customers

**Goal:** Identify customers who:

* Placed more than 1 order
* Used promo in **all orders**

---

### 7️⃣ Organic Customer Acquisition %

**Goal:** Calculate percentage of customers acquired organically in Jan 2025.

**Definition:**

* Organic = First order without promo code

**Approach:**

* Use window function to find first order
* Compute percentage

---

## 🛠️ SQL Concepts Used

* Common Table Expressions (CTEs)
* Window Functions (`ROW_NUMBER`)
* Aggregations (`COUNT`, `MIN`, `MAX`)
* Date Functions (`DATEADD`, `MONTH`, `YEAR`)
* Conditional Aggregation
* Subqueries

---

## 📊 Key Insights

* Helps understand **customer acquisition & retention**
* Identifies **high-performing restaurants**
* Enables **targeted marketing strategies**
* Tracks **promo effectiveness**

---




