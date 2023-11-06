# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

## Date:

## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
update manager set salary=(salary*0.10)+salary;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/857d7167-f899-450d-af64-b2ffc6e3eae9)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
delete from manager where salary<2750;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/87e8d13a-b646-4d1f-8477-fe5a80cb099c)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
SQL> SELECT
  2  ename AS "Name",
  3  salary * 12 AS "Annual Salary"
  4  FROM
  5  manager;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/c23a380a-0e6a-49a0-bec7-05116989b2a6)


### Q5)	List the names of Clerks from emp table.


### QUERY:
 select ename from manager where designation='clerk';

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/d2c1ab28-c9b0-4831-9be9-d512585ddd23)


### Q6)	List the names of employee who are not Managers.


### QUERY:
select ename from manager where designation <> 'manager';

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/3cfa41be-59f4-4be9-b56d-82847564d1e6)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
select ename from manager where commission=0;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/39444749-d639-4f95-b1d8-ef070f95f593)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
select ename from manager where ename like '%s' or ename like 's%';

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/cddd6db4-e650-4032-9e85-71f377c06b0a)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/045aa0b6-97e2-4c77-a531-4dded9d91f3e)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/f6ec5df3-bc4b-4f8a-9c2d-51bcfe0c1a51)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
select ename,deptno,salary from manager order by deptno asc,salary desc;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/0a294b89-ad95-4482-b370-ad298249f0d8)


### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
select ename from manager where deptno not in (30,40,10);

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/55660ff4-3e25-4dfb-9c51-35c5a52a9239)


### Q13) Find number of rows in the table EMP

### QUERY:
 select count(*) from manager;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/8dd520b6-3138-480e-91b4-0640d14622db)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
 select max(salary) from manager;
 select min(salary) from manager;
 select avg(salary) from manager;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/c8302d9c-79ee-4612-8ceb-470461793c7b)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;

### OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118610231/efbd9d50-791f-4ac4-a6b2-bcaba4325634)

## RESULT:
To create a manager database and execute DML queries using SQL is executed successfully.
