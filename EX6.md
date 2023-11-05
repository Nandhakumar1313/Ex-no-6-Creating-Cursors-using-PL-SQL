# Ex. No: 6 Creating Cursors using PL/SQL
### Date:
### AIM: 
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```sql
create table employeee(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
insert into employeee values(1,'john','HR',50000);
insert into employeee values(2,'joe','IT',65000);
insert into employeee values(3,'bob','Finance',55000);
```

### PLSQL Cursor code
```sql
declare
cursor employee_cursor is
select empid,empname,dept,salary
from employee;
empid number;
empname varchar(90);
dept varchar(90);
salary number;
begin
open employee_cursor;
loop
fetch employee_cursor into empid,empname,dept,salary;
exit when employee_cursor%notfound;
dbms_output.put_line('Employee ID: '||empid);
dbms_output.put_line('Employee Name: '||empname);
dbms_output.put_line('Department: '||dept);
dbms_output.put_line('Salary: '||salary);
dbms_output.put_line('------------------------');
end loop;
close employee_cursor;
end;
/

```
### Output:

![271705907-d128b2d0-f16f-4c4e-92d0-1630d0e2f0b8](https://github.com/Nandhakumar1313/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120230694/d70eb140-5806-488e-81d2-504a4c765ed2)


### Result:
The Program has been implemented successfully.
