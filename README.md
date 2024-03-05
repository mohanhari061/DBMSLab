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
