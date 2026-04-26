# SQL Lab – Experiment 6

## Aim
To perform miscellaneous operations including using the DECODE function for conditional mapping and performing date arithmetic.

### Query
```sql
-- 1. Use DECODE to display department names based on DEPTNO
SELECT ENAME, DECODE(DEPTNO, 10, 'ACCOUNTING', 20, 'RESEARCH', 30, 'SALES', 40, 'OPERATIONS', 'UNKNOWN') AS DEPT_NAME FROM EMPLOYEE;

-- 2. Calculate the age of each employee in years (based on current date)
SELECT ENAME, TRUNC(MONTHS_BETWEEN(SYSDATE, HIREDATE) / 12) AS YEARS_WORKED FROM EMPLOYEE;

-- 3. Display name and salary after a 15% increase
SELECT ENAME, SAL, (SAL * 1.15) AS NEW_SALARY FROM EMPLOYEE;

-- 4. Display the hire date and the day of the week on which they were hired
SELECT ENAME, HIREDATE, TO_CHAR(HIREDATE, 'DAY') AS HIRE_DAY FROM EMPLOYEE;

-- 5. Display the number of months each employee has worked
SELECT ENAME, TRUNC(MONTHS_BETWEEN(SYSDATE, HIREDATE)) AS MONTHS_WORKED FROM EMPLOYEE;

-- 6. Display the date 3 months from the hire date
SELECT ENAME, HIREDATE, ADD_MONTHS(HIREDATE, 3) AS REVIEW_DATE FROM EMPLOYEE;
```

### Output
**Query 1 (DECODE Results):**
| ENAME | DEPT_NAME |
| :--- | :--- |
| SMITH | RESEARCH |
| ALLEN | SALES |
| WARD | SALES |
| JONES | RESEARCH |

**Query 4 (Hire Day Example):**
| ENAME | HIREDATE | HIRE_DAY |
| :--- | :--- | :--- |
| SMITH | 17-DEC-80 | WEDNESDAY |
| ALLEN | 20-FEB-81 | FRIDAY |

**Query 3 (15% Increase Example):**
| ENAME | SAL | NEW_SALARY |
| :--- | :--- | :--- |
| SMITH | 800 | 920 |
| ALLEN | 1600 | 1840 |
| WARD | 1250 | 1437.5 |
| KING | 5000 | 5750 |
