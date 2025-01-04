 Q1. Create a table EMPLOYEE as follows:
```sql
create database gsce;
use gsce;
create table employee (
    sno int,
    Name varchar(40),
    Designation varchar(40),
    Branch varchar (40)
)
```
a)assign s.no as primary key.
```sql
ALTER TABLE EMPLOYEE ADD PRIMARY KEY (S.No);
```


b)alter table by adding a column SALARY.
```sql
ALTER TABLE EMPLOYEE ADD SALARY DECIMAL(10, 2);
```

c)alter table by modifying column name NAME.
```sql
ALTER TABLE EMPLOYEE CHANGE name NAME VARCHAR(255);

```

d)describe table employee.
```sql
DESCRIBE EMPLOYEE;
desc employee;

```


e)insert 5 records in employee table.
```sql
insert into employee(sno,name,Designation,branch,salary)
values(1, 'Misha', 'Manager', 'Delhi', 75000),
(2, 'Disha', 'Supervisor', 'Mumbai', 50000),
(3, 'Nisha', 'Assistant', 'Chennai', 40000),
(4, 'Risha', 'Clerk', 'Kolkata', 30000),
(5, 'Tisha', 'Manager', 'Pune', 80000);

```


f)delete 3rd record from table.
```sql
delete from employee where sno=3;
```


g)update salary of employee with s.no 1.
```sql
update employee set salary=1000 where sno=1;
```


h) update salary of employee with branch Mumbai.
```sql
update employee set salary=salary+10000 where branch="Mumbai"
```
i)alter table by adding column contact_no.
```sql
alter table employee add contact_no varchar(12);

```
j)alter table by adding column aadhar_no.
```sql
alter table employee add aadhar_no varchar(12);
```
k)update values in column aadhar_no.
```sql
update employee set aadhar_no="123456789013" where sno>0;
update employee set aadhar_no=aadhar_no+sno where sno>0;
```
l)modify domain of column aadhar_no to varchar.
```sql
alter table employee modify aadhar_no varchar(12);
```
m)drop column contact_no.
```sql
alter table employee drop column contact_no;
```
n)display highest salary from table employee.
```sql
select max(salary) as highest_salary from employee;
```
o)update the record with lowest salary by 5000.
```sql
UPDATE employee 
SET salary = salary + 5000
WHERE salary = (
    SELECT min_salary
    FROM (SELECT MIN(salary) AS min_salary FROM employee) AS temp
);

```
p)display records in descending order of salary using order by clause.
```sql
select * form employee order be desc;
```

2.Write SQL syntax with examples of 10 String functions.
String Functions
Examples with syntax:

CONCAT:
```sql

SELECT CONCAT('Hello', ' World') AS Greeting;
```


LENGTH:
 ```sql
SELECT LENGTH('Database') AS Length;
```
UPPER:
```sql

SELECT UPPER('database') AS UpperCase;
```
LOWER:
```sql

SELECT LOWER('DATABASE') AS LowerCase;
```
SUBSTRING:
```sql

SELECT SUBSTRING('Database Management', 1, 8) AS SubString;
```
REPLACE:
```sql

SELECT REPLACE('Hello World', 'World', 'DBMS') AS ReplacedString;
```
TRIM:
```sql

SELECT TRIM('  Hello  ') AS TrimmedString;
```
RIGHT:
```sql

SELECT RIGHT('Database', 4) AS RightPart;
```
LEFT:
```sql

SELECT LEFT('Database', 4) AS LeftPart;
```
INSTR:
```sql

SELECT INSTR('Database', 'base') AS Position;
```


3. Mathematical Functions
Examples with syntax:

ABS:
```sql

SELECT ABS(-10) AS AbsoluteValue;
```
CEIL:
```sql

SELECT CEIL(10.5) AS CeilValue;
```
FLOOR:
```sql

SELECT FLOOR(10.5) AS FloorValue;
```
ROUND:
```sql

SELECT ROUND(10.567, 2) AS RoundedValue;
```
MOD:
```sql

SELECT MOD(10, 3) AS ModValue;
```
POWER:
```sql

SELECT POWER(2, 3) AS PowerValue;
```
SQRT:
```sql

SELECT SQRT(25) AS SquareRoot;
```
EXP:
```sql

SELECT EXP(1) AS ExponentialValue;
```
LN:
```sql

SELECT LN(10) AS NaturalLog;
```
TRUNCATE:
```sql

SELECT TRUNCATE(10.567, 2) AS TruncatedValue;
```






4. Queries for EMPLOYEE_DETAILS
a. Assign S.No as Primary Key:


```sql

ALTER TABLE EMPLOYEE_DETAILS ADD PRIMARY KEY (S.No);
```
b. Insert 5 records:


```sql

INSERT INTO EMPLOYEE_DETAILS (S.No, Emp_Name, Acc_No, Balance)
VALUES
(1, 'Misha', 1234, 10000),
(2, 'Disha', 5678, 12000),
(3, 'Nisha', 9101, 15000),
(4, 'Risha', 1112, 20000),
(5, 'Tisha', 1314, 25000);
```
c. Describe the EMPLOYEE_DETAILS table:


```sql

DESCRIBE EMPLOYEE_DETAILS;
```
d. Connect EMPLOYEE_DETAILS with EMPLOYEE using a foreign key:


```sql

ALTER TABLE EMPLOYEE_DETAILS ADD CONSTRAINT fk_employee
FOREIGN KEY (S.No) REFERENCES EMPLOYEE(S.No);
```
e. Display records by connecting both tables:


```sql

SELECT e.S.No, e.EMP_NAME, ed.Acc_No, ed.Balance 
FROM EMPLOYEE e 
JOIN EMPLOYEE_DETAILS ed ON e.S.No = ed.S.No;
```
5. JOIN Operations
Natural Join:


```sql

FROM EMPLOYEE e 
NATURAL JOIN EMPLOYEE_DETAILS ed;

```
Left Join:


```sql
SELECT e.S.No, e.EMP_NAME, ed.Acc_No, ed.Balance 
FROM EMPLOYEE e 
LEFT JOIN EMPLOYEE_DETAILS ed ON e.S.No = ed.S.No;

```
Right Join:


```sql

SELECT e.S.No, e.EMP_NAME, ed.Acc_No, ed.Balance 
FROM EMPLOYEE e 
RIGHT JOIN EMPLOYEE_DETAILS ed ON e.S.No = ed.S.No;
```