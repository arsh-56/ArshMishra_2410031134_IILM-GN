# Database Management Systems (DBMS) Lab Portfolio

This repository contains the complete laboratory coursework for the Database Management Systems (DBMS) practical sessions. It documents a series of SQL experiments, ranging from basic table creation to advanced queries involving complex joins, subqueries, and aggregate functions.

## 📖 Overview

The experiments are primarily based on the classic Oracle `EMPLOYEE`, `DEPARTMENT`, and `SALGRADE` relational schemas. Each experiment file (`Experiment-X.md`) includes:
- The **Aim** of the experiment.
- The precise **SQL Queries** used to solve the given problem statements.
- The expected **Tabular Output** representing the data returned by the queries.

## 🗄️ Database Schema

The core schema used throughout the laboratory assignments revolves around the following tables:
1. **DEPARTMENT**: Stores department details (`DEPTNO`, `DNAME`, `LOC`).
2. **EMPLOYEE**: Stores employee records (`EMPNO`, `ENAME`, `JOB`, `MGR`, `HIREDATE`, `SAL`, `COMM`, `DEPTNO`) with a foreign key relation to `DEPARTMENT`.
3. **SALGRADE**: Stores salary grade ranges for employee categorization (`GRADE`, `LOSAL`, `HISAL`).

## 🧪 Experiments Index

| Experiment | Focus Area | Description |
| :--- | :--- | :--- |
| **[Experiment 1](./Experiment-1.md)** | DDL & DML Basics | Table creation with constraints (Primary/Foreign keys) and data insertion. |
| **[Experiment 2](./Experiment-2.md)** | Simple Data Retrieval | Basic `SELECT` queries, `WHERE` clause filtering, and aliases. |
| **[Experiment 3](./Experiment-3.md)** | Sorting & Filtering | Using `ORDER BY`, `IN`, `LIKE`, and relational operators. |
| **[Experiment 4](./Experiment-4.md)** | Built-in Functions | Applying single-row string, numeric, and date functions. |
| **[Experiment 5](./Experiment-5.md)** | Aggregate Functions | Using `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, and `GROUP BY`. |
| **[Experiment 6](./Experiment-6.md)** | Advanced Grouping | Implementation of `HAVING` clause alongside grouping constraints. |
| **[Experiment 7](./Experiment-7.md)** | Joins Fundamentals | Inner joins, outer joins, and self-joins for cross-table data. |
| **[Experiment 8](./Experiment-8.md)** | Set Operations | Using `UNION`, `INTERSECT`, and `MINUS`. |
| **[Experiment 9](./Experiment-9.md)** | Basic Subqueries | Implementing single-row and multiple-row subqueries. |
| **[Experiment 10](./Experiment-10.md)** | Complex Subqueries & `ANY`/`ALL` | Deep nesting, using `ANY`, `ALL` operators, and manager hierarchy retrieval. |
| **[Experiment 11](./Experiment-11.md)** | Data Analysis & Conditional Deletions | Finding top earners, cross-referencing averages, and nested data manipulation. |
| **[Experiment 12](./Experiment-12.md)** | Advanced Structural Queries | Handling correlated subqueries, non-existence conditions (`NOT IN`), and string lengths. |

## 💻 Environment
- **Language**: SQL
- **Dialect**: Oracle SQL (Compatible with standard relational engines)
- **Format**: Markdown Documentation

---
*Developed as part of the collegiate DBMS Laboratory coursework.*
