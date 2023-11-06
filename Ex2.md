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
```sql
UPDATE manager
SET SALARY = SALARY + (SALARY *10/100);
```
### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/42ed982e-54e3-4435-ae1c-2bd407af9ef2)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```sql
delete from manager
 where salary<2750;
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/4eac6c11-69c9-4cda-9205-0a932bc7de19)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```sql
 select ename as "Name",salary*12 as "Annual Salary" from manager;
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/07f25f7f-2803-41dc-86cf-8f064984c19c)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```sql
select ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/00866b76-9581-4a10-9f15-cf08e1aee625)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/80ef0f3a-9702-4598-b612-bda0bfcf6a4b)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/820d8893-b58b-4b0d-a904-4d5b097f3450)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/7d5a8f5b-4718-4278-95b5-4a79831ea307)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
 select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:

![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/ba425fdf-9d3d-44c1-b060-1fa7ba72da11)

### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/67367693-da4c-440a-a8ea-9e5f85426ced)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/1671b9e8-fe6b-48e1-a1c0-885c167e91fe)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:

![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/65e21a97-b3c5-4bc4-9e38-060e3a7bdd0e)

### Q13) Find number of rows in the table EMP

### QUERY:
```sql
select count(*) from manager;
```

### OUTPUT:

![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/c3a5f6e8-1986-4238-8041-2a56c2e5a5e3)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```sql
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
```

### OUTPUT:

![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/8d2cef70-233a-446f-8d27-eadc96718aed)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
 SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:

![image](https://github.com/Nethraa24/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121215786/0c2e5384-eaf1-482f-bce4-dc27894e6391)
