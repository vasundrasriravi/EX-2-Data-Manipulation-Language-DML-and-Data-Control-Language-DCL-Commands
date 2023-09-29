# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
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
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![row](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/9bd4bbc4-6561-4ff5-b0c3-c9ebecaea86b)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![r1](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/a05e4464-9303-42d3-8c2f-5d3d7dfb8926)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![s1](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/977e29d6-91d4-4880-bcb0-1cdb79312c74)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![emp](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/0bdaab5f-cc92-40d9-828d-66adf731196c)

### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![manag](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/f03765c4-f6c4-4419-859f-a1eaec9fa7a5)

### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![commi](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/3d66a046-60d5-4c56-af38-64f458e45a35)

### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![s2](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/ecdaa05d-d40)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![hire](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/6abf23ad-c3f3-43f3-a167-8c247e12c7e7)

### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![h1](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/6f459186-2056-498c-96e6-4bfec95f6164)

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![sal](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/591397df-af07-440d-8c8e-c01999bf7ef2)

### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![dept](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/b259ca89-e52f-418e-bd9e-40b0b60ed4d6)

### Q13) Find number of rows in the table EMP

### QUERY:
```
 select count(*) from manager;
```
### OUTPUT:
![count](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/0cffd337-6c7b-498e-9e23-64a75c8474c5)

### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:

### MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![max](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/d4b68ce5-b1b0-425d-990d-3002c22344eb)

### MINIMUM:
```
select min(salary) from manager;
```
### OUTPUT:
![mini](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/ad0d325f-4fde-47df-9bd9-88c05c3a95f8)

### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![avg](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/6e34d771-1865-4bdd-9b4a-4afba32d71ef)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![job](https://github.com/vasundrasriravi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393983/cb5cbe10-87f3-427f-a792-f1f18f6dda52)

### RESULT:
To create a manager database and execute DML queries using SQL is executed successfully.
