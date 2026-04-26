# SQL Lab – Experiment 7

## Aim
To use specialized date and numeric functions to extract complex information such as remaining days in a year, specific weekdays, and formatted dates.

### Query
```sql
-- 1. Find the number of days remaining in the current year
SELECT TO_DATE('31-DEC-' || TO_CHAR(SYSDATE, 'YYYY'), 'DD-MON-YYYY') - TRUNC(SYSDATE) AS DAYS_REMAINING FROM DUAL;

-- 2. Find the date of the last Friday of the current month
SELECT NEXT_DAY(LAST_DAY(SYSDATE) - 7, 'FRIDAY') AS LAST_FRIDAY FROM DUAL;

-- 3. Display the hire date of all employees in the format 'DD-MON-YYYY'
SELECT ENAME, TO_CHAR(HIREDATE, 'DD-MON-YYYY') AS FORMATTED_HIREDATE FROM EMPLOYEE;

-- 4. List the employees who have worked more than 40 years
SELECT ENAME, HIREDATE FROM EMPLOYEE WHERE MONTHS_BETWEEN(SYSDATE, HIREDATE) / 12 > 40;

-- 5. Display the name and salary of employees whose salary is not divisible by 100
SELECT ENAME, SAL FROM EMPLOYEE WHERE MOD(SAL, 100) != 0;

-- 6. Display the name and salary of employees who earn more than their managers
SELECT E.ENAME, E.SAL, M.ENAME AS MGR_NAME, M.SAL AS MGR_SAL FROM EMPLOYEE E JOIN EMPLOYEE M ON E.MGR = M.EMPNO WHERE E.SAL > M.SAL;
```

### Output
**Query 1 (Days Remaining):**
| DAYS_REMAINING |
| :--- |
| 277 | (Calculated for March 29, 2026) |

**Query 3 (Formatted Dates):**
| ENAME | FORMATTED_HIREDATE |
| :--- | :--- |
| SMITH | 17-DEC-1980 |
| ALLEN | 20-FEB-1981 |
| WARD | 22-FEB-1981 |

**Query 5 (Salary not divisible by 100):**
| ENAME | SAL |
| :--- | :--- |
| JONES | 2975 |
| BLAKE | 2850 |
| CLARK | 2450 |

**Query 6 (Earn more than Manager):**
| ENAME | SAL | MGR_NAME | MGR_SAL |
| :--- | :--- | :--- | :--- |
| SCOTT | 3000 | JONES | 2975 |
| FORD | 3000 | JONES | 2975 |
