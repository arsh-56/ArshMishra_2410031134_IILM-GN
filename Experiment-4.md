# SQL Lab – Experiment 4

## Aim
To perform advanced filtering using date comparisons, string pattern matching, and sorting.

### Query
```sql
-- 1. List all employees who joined before 1-JAN-81
SELECT ENAME, HIREDATE FROM EMPLOYEE WHERE HIREDATE < '01-JAN-81';

-- 2. List all employees whose name contain 'A'
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE '%A%';

-- 3. List all employees whose name contain 'L' as second character
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE '_L%';

-- 4. List all employees whose names have exactly 5 characters
SELECT ENAME FROM EMPLOYEE WHERE LENGTH(ENAME) = 5;

-- 5. List all employees who joined in the year 1981
SELECT ENAME, HIREDATE FROM EMPLOYEE WHERE HIREDATE BETWEEN '01-JAN-81' AND '31-DEC-81';

-- 6. List all employees who do not have a manager (MGR is NULL)
SELECT ENAME FROM EMPLOYEE WHERE MGR IS NULL;

-- 7. List all employees whose job is either CLERK or ANALYST in descending order of ENAME
SELECT ENAME, JOB FROM EMPLOYEE WHERE JOB IN ('CLERK', 'ANALYST') ORDER BY ENAME DESC;

-- 8. List all employees whose salary is not 800, 1600 or 3000
SELECT ENAME, SAL FROM EMPLOYEE WHERE SAL NOT IN (800, 1600, 3000);

-- 9. List all employees whose name does not start with 'S'
SELECT ENAME FROM EMPLOYEE WHERE ENAME NOT LIKE 'S%';

-- 10. List all employees who were hired in the month of December
SELECT ENAME, HIREDATE FROM EMPLOYEE WHERE TO_CHAR(HIREDATE, 'MON') = 'DEC';
```

### Output
**Query 1 (Hired before 1981):**
| ENAME | HIREDATE |
| :--- | :--- |
| SMITH | 17-DEC-80 |

**Query 3 (L as 2nd character):**
| ENAME |
| :--- |
| ALLEN |
| BLAKE |
| CLARK |

**Query 6 (No Manager):**
| ENAME |
| :--- |
| KING |

**Query 10 (Hired in December):**
| ENAME | HIREDATE |
| :--- | :--- |
| SMITH | 17-DEC-80 |
| JAMES | 03-DEC-81 |
| FORD | 03-DEC-81 |
