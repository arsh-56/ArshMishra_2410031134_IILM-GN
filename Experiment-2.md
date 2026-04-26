# SQL Lab – Experiment 2

## Aim
To perform DDL and DML operations including creating a table from an existing one, updating records, deleting records, and dropping tables.

### Query
```sql
-- 1. Create Employee_master table with data from EMPLOYEE
CREATE TABLE Employee_master AS SELECT * FROM EMPLOYEE;

-- 2. Delete all records from Employee_master where Deptno is 10
DELETE FROM Employee_master WHERE DEPTNO = 10;

-- 3. Update 10% to the salary of DEPTNO 20 from Employee_Master
UPDATE Employee_master SET SAL = SAL * 1.10 WHERE DEPTNO = 20;

-- 4. Delete all salesman from Employee_Master
DELETE FROM Employee_master WHERE JOB = 'SALESMAN';

-- 5. Drop Employee_master table
DROP TABLE Employee_master;
```

### Output
| Operation | Status |
| :--- | :--- |
| Create Table | Table 'Employee_master' created. |
| Delete (Dept 10) | 3 rows deleted. |
| Update (Dept 20) | 5 rows updated. |
| Delete (Salesman) | 4 rows deleted. |
| Drop Table | Table 'Employee_master' dropped. |
