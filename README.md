# DBMS

## Exp:5

#### Q1
```sql
select deptno from emp038 union select deptno from dept038;
```
#### Q2
```sql
select deptno from emp038 union all select deptno from dept038;
```
#### Q3
```sql
select deptno from emp038 intersect select deptno from dept038;
```
#### Q4
```sql
select deptno from dept038 minus select deptno from emp038;
```
#### Q5
```sql
create view manager_details038 as select * from emp038 where job='Manager';
select * from manager_details038;
```
#### Q6
```sql
create view employee_details038 as select e.empno,e.ename,e.deptno,d.dname from emp038 e join dept038 d on e.deptno=d.deptno;
select * from employee_details038;
```
#### Q7
```sql
create view emp_basic038 as select e.empno,e.ename,e.deptno,e.sal,d.dname from emp038 e inner join dept038 d on e.deptno=d.deptno where job not
 in ('President','Manager');
select * from emp_basic038;
```
#### Q8
```sql
select view_name from user_views;
```
#### Q9
```sql

```
#### Q10
```sql
create view dummy038 as select empno,ename from emp038;
select * from dummy;
drop view dummy038;

```


# DBMS

## Exp:6

#### Program 6.1:write a pl/sql program to swap two numbers without taking third variable
```sql
declare num1 number := 10;
num2 number := 11;
begin dbms_output.put_line('Before');
dbms_output.put_line('num1=' || num1 || ' num2=' || num2);
num1 := num1 + num2;
num2 := num1 - num2;
num1 := num1 - num2;
dbms_output.put_line('After');
dbms_output.put_line('num1=' || num1 || ' num2=' || num2);
end;
/
```
#### Program 6.2:write a pl/sql program to swap two numbers by taking third variable
```sql
declare num1 number := 10;
num2 number := 11;
temp number;
begin dbms_output.put_line('Before');
dbms_output.put_line('num1=' || num1 || ' num2=' || num2);
temp := num1;
num1 := num2;
num2 := temp;
dbms_output.put_line('After');
dbms_output.put_line('num1=' || num1 || ' num2=' || num2);
end;
/
```
#### Program 6.3:Write a pl/sql program to find the largest of two numbers
```sql
declare num1 number := 10;
num2 number := 11;
begin if(num1 > num2) then dbms_output.put_line('Number ' || num1 || ' is largest');
else dbms_output.put_line('Number ' || num2 || ' is largest');
end if;
end;
/
```
#### Program 6.4:write a pl/sql program to find the total and average of 6 subjects and display the grade
```sql
declare num1 number := 80;
num2 number := 71;
num3 number := 87;
num4 number := 98;
num5 number := 84;
num6 number := 45;
s number;
grade varchar2(1);
avgr number;
begin s :=(num1 + num2 + num3 + num4 + num5 + num6);
avgr :=(s)/ 6;
if avgr >= 90 then grade := 'A';
elsif avgr >= 80 then grade := 'B';
elsif avgr >= 70 then grade := 'C';
elsif avgr >= 60 then grade := 'D';
elsif avgr >= 50 then grade := 'E';
else grade := 'F';
end if;
dbms_output.put_line('Grade is = ' || grade);
end;
/
```
#### Program 6.5: Write a pl/sql program to find the sum of digits in a given number
```sql
declare num1 number;
d number;
sm number := 0;
begin num1 :=& num1;
while num1 > 0 loop d := mod(num1, 10);
sm := sm + d;
num1 := trunc(num1 / 10);
end loop;
dbms_output.put_line('Sum of digits is : ' || sm);
end;
/
```
#### Program 6.6:write a pl/sql program to display the number in reverse order
```sql
declare num1 number;
num2 number := 0;
d number;
begin num1 :=& num1;
while num1 > 0 loop d := mod(num1, 10);
num2 := num2 * 10 + d;
num1 := trunc(num1 / 10);
end loop;
dbms_output.put_line('Reverse of digits is : ' || num2);
end;
/
```
#### Program 6.7:Write a pl/sql program to check whether the given number is prime or not
```sql
declare num1 number;
flag number := 1;
d number;
begin num1 :=& num1;
d := 2;
while d < num1 loop if mod(num1, d)= 0 then flag := 0;
end if;
d := d + 1;
end loop;
if flag = 1 then dbms_output.put_line('Yes, It is a prime number ' || num1);
else dbms_output.put_line('NO, It is NOT a prime number ');
end if;
end;
/
```
#### Program 6.8:Write a pl/sql program to find the factorial of a given number
```sql
declare num1 number;
fact number := 1;
d number;
begin num1 :=& num1;
d := 1;
while d <= num1 loop fact := fact * d;
d := d + 1;
end loop;
dbms_output.put_line('Factorial : ' || fact);
end;
/
```
#### Program 6.9:write a pl/sql code block to calculate the area of a circle for a value of radius varying from 3 to 7.Store the radius and the corresponding values of calculated area in an empty table named areas ,consisting of two columns radius & area
```sql
create table area038(radius number, area number(5, 2));
declare rad number;
a number := 1;
begin rad := 3;
while rad <= 7 loop a := 3.14 * power(rad, 2);
insert into area038
values (rad, a);
rad := rad + 1;
end loop;
end;
/
select * from area038;
```
#### Program 6.10:write a pl/sql code block that will accept an account number from the user,check if the users balance is less than minimum balance,only then deduct rs.100/- from the balance.this process is fired on the acct table.
```sql
create table acct038(acc number(4) primary key,bal number(5));
insert into acct038
values (1001, 300);
insert into acct038
values (1002, 80);

declare accn number;
bl number := 1;
begin accn :=& accn;
select bal into bl
from acct038
where accn = acc;
if bl < 100 then dbms_output.put_line('Not sufficient amount');
else dbms_output.put_line('INR 100 debited');
bl := bl - 100;
update acct038
set bal = bl
where accn = acc;
end if;
end;
/
```

