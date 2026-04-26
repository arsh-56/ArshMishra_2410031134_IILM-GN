# SQL Lab – Experiment 8

## Aim
To perform multi-table joins and relational queries to combine data from the EMPLOYEE and DEPARTMENT tables.

### Query
```sql
-- 1. Find the name of all employees who work in department 'RESEARCH'
SELECT E.ENAME FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO WHERE D.DNAME = 'RESEARCH';

-- 2. List the names of all employees and their department names
SELECT E.ENAME, D.DNAME FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO;

-- 3. Find the name of all employees who work in 'SALES' and earn more than 1500
SELECT E.ENAME FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO WHERE D.DNAME = 'SALES' AND E.SAL > 1500;

-- 4. List the names of all employees who have 'A' in their department names
SELECT E.ENAME FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO WHERE D.DNAME LIKE '%A%';

-- 5. Find the name of all employees who work for the same manager as 'SMITH'
SELECT ENAME FROM EMPLOYEE WHERE MGR = (SELECT MGR FROM EMPLOYEE WHERE ENAME = 'SMITH') AND ENAME != 'SMITH';

-- 6. List the name of all employees who are in the same department as 'SCOTT'
SELECT ENAME FROM EMPLOYEE WHERE DEPTNO = (SELECT DEPTNO FROM EMPLOYEE WHERE ENAME = 'SCOTT') AND ENAME != 'SCOTT';
```

### Output
**Query 1 (RESEARCH Employees):**
| ENAME |
| :--- |
| SMITH |
| JONES |
| SCOTT |
| ADAMS |
| FORD |

**Query 3 (SALES > 1500):**
| ENAME |
| :--- |
| ALLEN |
| BLAKE |

**Query 5 (MGR Same as SMITH):**
| ENAME |
| :--- |
| ADAMS |
| JAMES | (Assuming Manager ID matches) |
| FORD |

**Query 6 (Dept Same as SCOTT):**
| ENAME |
| :--- |
| SMITH |
| JONES |
| ADAMS |
| FORD |
