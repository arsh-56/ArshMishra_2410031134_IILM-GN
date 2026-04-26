# SQL Lab – Experiment 5

## Aim
To use SQL group functions (Aggregate functions) such as SUM, AVG, MAX, MIN, and COUNT to perform calculations on numeric data.

### Query
```sql
-- 1. Find the maximum, minimum, and average salary of all employees
SELECT MAX(SAL) AS MAX_SAL, MIN(SAL) AS MIN_SAL, AVG(SAL) AS AVG_SAL FROM EMPLOYEE;

-- 2. Find the total salary of all employees
SELECT SUM(SAL) AS TOTAL_SALARY FROM EMPLOYEE;

-- 3. Find the maximum salary of all employees and the employee name
SELECT ENAME, SAL FROM EMPLOYEE WHERE SAL = (SELECT MAX(SAL) FROM EMPLOYEE);

-- 4. Find the number of employees in each department
SELECT DEPTNO, COUNT(*) AS EMP_COUNT FROM EMPLOYEE GROUP BY DEPTNO;

-- 5. Find the maximum salary for each job in each department
SELECT DEPTNO, JOB, MAX(SAL) AS MAX_SAL FROM EMPLOYEE GROUP BY DEPTNO, JOB;

-- 6. Display the number of employees for each job
SELECT JOB, COUNT(*) AS JOB_COUNT FROM EMPLOYEE GROUP BY JOB;
```

### Output
**Query 1 (Max, Min, Avg):**
| MAX_SAL | MIN_SAL | AVG_SAL |
| :--- | :--- | :--- |
| 5000 | 800 | 2073.21 |

**Query 3 (Max Salary Employee):**
| ENAME | SAL |
| :--- | :--- |
| KING | 5000 |

**Query 4 (Employees per Dept):**
| DEPTNO | EMP_COUNT |
| :--- | :--- |
| 10 | 3 |
| 20 | 5 |
| 30 | 6 |

**Query 6 (Count for each Job):**
| JOB | JOB_COUNT |
| :--- | :--- |
| CLERK | 4 |
| SALESMAN | 4 |
| ANALYST | 2 |
| MANAGER | 3 |
| PRESIDENT | 1 |
