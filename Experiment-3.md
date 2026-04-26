# SQL Lab – Experiment 3

## Aim
To retrieve specific data from the EMPLOYEE table using various filtering, sorting, and pattern matching techniques.

### Query
```sql
-- 1. List all employees and jobs in Department 30 in descending order by salary
SELECT ENAME, JOB, SAL FROM EMPLOYEE WHERE DEPTNO = 30 ORDER BY SAL DESC;

-- 2. List job and Department Number of employees whose name are five letters long begin with 'A' and end with 'N'
SELECT JOB, DEPTNO FROM EMPLOYEE WHERE ENAME LIKE 'A___N';

-- 3. Display the name of employees whose name start with alphabet S
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE 'S%';

-- 4. Display the names of employees whose name ends with alphabet S
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE '%S';

-- 5. Display names of employees working in department 10, 20, or 40 OR working as CLERKS, SALESMAN, or ANALYST
SELECT ENAME FROM EMPLOYEE WHERE DEPTNO IN (10, 20, 40) OR JOB IN ('CLERK', 'SALESMAN', 'ANALYST');

-- 6. Display employee number and names for employees who earn commission
SELECT EMPNO, ENAME FROM EMPLOYEE WHERE COMM IS NOT NULL AND COMM > 0;

-- 7. Display employee number and total salary (SAL + COMM) for each employee
SELECT EMPNO, ENAME, (SAL + NVL(COMM, 0)) AS TOTAL_SALARY FROM EMPLOYEE;

-- 8. List the Employee name, Employee numbers and department of all clerks
SELECT ENAME, EMPNO, DEPTNO FROM EMPLOYEE WHERE JOB = 'CLERK';

-- 9. Find all managers not in department 30
SELECT ENAME FROM EMPLOYEE WHERE JOB = 'MANAGER' AND DEPTNO != 30;

-- 10. List information about all Employees in department 10 who are not manager or clerks
SELECT * FROM EMPLOYEE WHERE DEPTNO = 10 AND JOB NOT IN ('MANAGER', 'CLERK');

-- 11. Find Employees and jobs earning between 1200 and 1400
SELECT ENAME, JOB FROM EMPLOYEE WHERE SAL BETWEEN 1200 AND 1400;

-- 12. List Name and Department Number of employee who are clerks, analyst or salesman
SELECT ENAME, DEPTNO FROM EMPLOYEE WHERE JOB IN ('CLERK', 'ANALYST', 'SALESMAN');

-- 13. List Name and Department Number of employee whose names began with M
SELECT ENAME, DEPTNO FROM EMPLOYEE WHERE ENAME LIKE 'M%';

-- 14. Find all employees who earn more than 2000
SELECT ENAME FROM EMPLOYEE WHERE SAL > 2000;
```

### Output
**Query 1 (Dept 30, Desc Salary):**
| ENAME | JOB | SAL |
| :--- | :--- | :--- |
| BLAKE | MANAGER | 2850 |
| ALLEN | SALESMAN | 1600 |
| TURNER | SALESMAN | 1500 |
| WARD | SALESMAN | 1250 |
| MARTIN | SALESMAN | 1250 |
| JAMES | CLERK | 950 |

**Query 2 (A___N):**
| JOB | DEPTNO |
| :--- | :--- |
| SALESMAN | 30 |

**Query 6 (Commission Earners):**
| EMPNO | ENAME |
| :--- | :--- |
| 7499 | ALLEN |
| 7521 | WARD |
| 7654 | MARTIN |

**Query 8 (All Clerks):**
| ENAME | EMPNO | DEPTNO |
| :--- | :--- | :--- |
| SMITH | 7369 | 20 |
| ADAMS | 7876 | 20 |
| JAMES | 7900 | 30 |
| MILLER | 7934 | 10 |
