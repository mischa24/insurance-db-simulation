# Insurance Database Simulation – SQL Project

![License: MIT](https://img.shields.io/badge/License-MIT-green)
![Built with SQL](https://img.shields.io/badge/Built%20with-SQL-blue)
![Database: MySQL](https://img.shields.io/badge/Database-MySQL-lightgrey)
![Tool: phpMyAdmin](https://img.shields.io/badge/Tested%20on-phpMyAdmin-orange)

This repository contains a relational database simulation designed to represent an insurance scenario, where **cars** and **customers** are tracked. Developed in MySQL and tested in **phpMyAdmin**, the project includes a complete SQL dump and a variety of queries to explore data extraction and logic functions.

---

## 📁 Files

- `insurance.sql` / `insurance.txt`: Full dump of the insurance database with table creation and inserts
- `erg_2_sql.txt`, `erg_2_sql_21_3.txt`: Core SQL queries using filters, aggregate functions and pattern matching
- `new 1.txt`, `telos_enot_2_sql_peirama.txt`: Extended queries for practice
- `erg_2.docx`: Report or documentation of the queries in textual form

---

## 📊 Database Structure

### Table: `car`
- `car_id` (PK), `plate`, `price`, `color`, `year`, `customer_id` (FK)

### Table: `customer`
- `customer_id` (PK), `first_name`, `last_name`, `age`, `email`, `phone`

---

## 📌 Sample Queries Demonstrated

- Filtering with `WHERE`, `LIKE`, `IN`, comparison operators
- Aggregate functions: `SUM`, `AVG`, `MIN`, `MAX`, `COUNT`
- String manipulation: `CONCAT`, `CONCAT_WS`, `AS aliasing`
- Foreign key usage and relational logic

---

## ⚠️ Notes

- The database includes repetitive entries intentionally, for query testing and filtering exercises.
- Files with different names may have similar content due to versioning during academic development.

---

## 🎓 Credits

Developed for academic use, 2025.

