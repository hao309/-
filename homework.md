```姓名：陈宗豪 学号：17061507```

# 第一次作业
## 1.创建一个数据库
```sql
create database diyicizuoye;
Query OK, 1 row affected (0.01 sec)
```
## 2.查看数据库
```sql
show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| diyicizuoye        |
| mysql              |
| performance_schema |
| sys                |
| xuexi              |
+--------------------+
6 rows in set (0.00 sec)
```
## 3.选择数据库
```sql
use diyicizuoye;
Database changed
```
## 4.删除数据库
```sql
 drop database diyicizuoye;
Query OK, 0 rows affected (0.02 sec)
```
# 第二次作业
## 1.create table 操作
```sql
use xuexi;
Database changed
create table diercizuoye(
    -> xingming varchar(20),
    -> xuehao int);
Query OK, 0 rows affected (0.04 sec)
```
## 2.alter table操作
### (1).修改表名
```sql
alter table diercizuoye rename zuoye2;
Query OK, 0 rows affected (0.03 sec)
```
### (2).在表的最后一个位置增加字段
```sql
alter table zuoye2
    -> add sex varchar(20);
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)
```
### (3).在表的第一个位置增加字段
```sql
  alter table zuoye2
    -> add age int first;
Query OK, 0 rows affected (0.07 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| age      | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```
### (4).在表的指定字段后增加字段
```sql
 alter table zuoye2
    -> add birtuday int
    -> after age;
Query OK, 0 rows affected (0.08 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| age      | int(11)     | YES  |     | NULL    |       |
| birtuday | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
5 rows in set (0.00 sec)
```
### (5).删除字段
```sql
alter table zuoye2
    -> drop sex;
Query OK, 0 rows affected (0.07 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| age      | int(11)     | YES  |     | NULL    |       |
| birtuday | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```
### (6).修改字段的数据类型
```sql
alter table zuoye2
    -> modify age varchar(20);
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| age      | varchar(20) | YES  |     | NULL    |       |
| birtuday | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.01 sec)
```
### (7).修改字段名字
```sql
 alter table zuoye2
    -> change age nianling varchar(20);
Query OK, 0 rows affected (0.03 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| nianling | varchar(20) | YES  |     | NULL    |       |
| birtuday | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```
### (8).同时修改字段的名字和属性
```sql
 alter table zuoye2
    -> change nianling age int;
Query OK, 0 rows affected (0.08 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| age      | int(11)     | YES  |     | NULL    |       |
| birtuday | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.01 sec)
```
### (9).修改字段顺序
```sql
 alter table zuoye2
    -> modify age int after xuehao;
Query OK, 0 rows affected (0.08 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| birtuday | int(11)     | YES  |     | NULL    |       |
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
| age      | int(11)     | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```
## 3.删除表
```sql
drop table zuoye2;
Query OK, 0 rows affected (0.01 sec)

mysql> desc zuoye2;
ERROR 1146 (42S02): Table 'xuexi.zuoye2' doesn't exist
```
## 4.NOT NULL操作
```sql
create table zuoye2(
    -> xingming varchar(20) not null,
    -> xuehao int,
    -> sex    varchar(20));
Query OK, 0 rows affected (0.04 sec)

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| xingming | varchar(20) | NO   |     | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)
```
## 5.UNIQUE操作
```sql
create table zuoye2(
    -> xingming varchar(20),
    -> xuehao int unique,
    -> sex varchar(20));
Query OK, 0 rows affected (0.04 sec)

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| xingming | varchar(20) | YES  |     | NULL    |       |
| xuehao   | int(11)     | YES  | UNI | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)
```
## 6.primary key操作
### (1).单字段主键
```sql
create table zuoye2(
    -> xingming varchar(20) primary key,
    -> xuehao int,
    -> sex varchar(20));
Query OK, 0 rows affected (0.04 sec)

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| xingming | varchar(20) | NO   | PRI | NULL    |       |
| xuehao   | int(11)     | YES  |     | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)
```
### (2).多字段主键
```sql
create table zuoye2(
    -> xingming varchar(20),
    -> xuehao int,
    -> sex varchar(20),
    -> constraint pk_xingming_xuehao primary key(xingming,xuehao));
Query OK, 0 rows affected (0.04 sec)

mysql> desc zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| xingming | varchar(20) | NO   | PRI | NULL    |       |
| xuehao   | int(11)     | NO   | PRI | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)
```
## 7.SHOW TABLES操作
```sql
show tables;
+-----------------+
| Tables_in_xuexi |
+-----------------+
| guyuan1         |
| v_test          |
| v_test1         |
| xuexiji         |
| zuoye2          |
+-----------------+
5 rows in set (0.00 sec)
```
## 8.DESCRIBE TABLE操作
```sql
describe zuoye2;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| xingming | varchar(20) | NO   | PRI | NULL    |       |
| xuehao   | int(11)     | NO   | PRI | NULL    |       |
| sex      | varchar(20) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)
```
# 第三次作业
## 输出我、我的老板、我的老板的老板
```sql
select '我','我的老板','我的老板的老板';
+----+----------+----------------+
| 我 | 我的老板 | 我的老板的老板 |
+----+----------+----------------+
| 我 | 我的老板 | 我的老板的老板 |
+----+----------+----------------+
1 row in set (0.00 sec)
```
# 第四次作业
## 1.select * from t_employee WHERE sal > (select sal from t_employee WHERE ename='SMITH');使用inner join 表示
```sql
select*from t_employee;
+--------+-------+--------+-----------+------+------------+------+------+
| deptno | empno | ename  | job       | MGR  | Hiredate   | sal  | comm |
+--------+-------+--------+-----------+------+------------+------+------+
|     20 |  7369 | SMITH  | CLERK     | 7902 | 1981-03-12 |  800 | NULL |
|     30 |  7499 | ALLEN  | SALESMAN  | 7698 | 1982-03-12 | 1600 |  300 |
|     30 |  7521 | WARD   | SALESMAN  | 7698 | 1838-03-12 | 1250 |  500 |
|     20 |  7566 | JONES  | MANAGER   | 7839 | 1981-03-12 | 2975 | NULL |
|     30 |  7654 | MARTIN | SALESMAN  | 7698 | 1981-01-12 | 1250 | 1400 |
|     10 |  7698 | BLAKE  | MANAGER   | 7839 | 1985-03-12 | 2450 | NULL |
|     20 |  7788 | SCOTT  | ANALYST   | 7566 | 1981-03-12 | 3000 | NULL |
|     10 |  7839 | KING   | PRESIDENT | NULL | 1981-03-12 | 5000 | NULL |
|     30 |  7844 | TURNER | SALESMAN  | 7689 | 1981-03-12 | 1500 |    0 |
|     20 |  7878 | ADAMS  | CLERK     | 7788 | 1981-03-12 | 1100 | NULL |
|     30 |  7900 | JAMES  | CLERK     | 7698 | 1981-03-12 |  950 | NULL |
|     20 |  7902 | FORD   | ANALYST   | 7566 | 1981-03-12 | 3000 | NULL |
|     10 |  7934 | MILLER | CLERK     | 7782 | 1981-03-12 | 1300 | NULL |
+--------+-------+--------+-----------+------+------------+------+------+
13 rows in set (0.00 sec)

mysql> select t1.deptno,t1.empno,t1.ename,t1.job,t1.mgr,t1.Hiredate,t1.sal,t1.comm
    -> from t_employee t1 inner join t_employee t2
    ->  on t1.sal>t2.sal and (t2.ename='smith');
+--------+-------+--------+-----------+------+------------+------+------+
| deptno | empno | ename  | job       | mgr  | Hiredate   | sal  | comm |
+--------+-------+--------+-----------+------+------------+------+------+
|     30 |  7499 | ALLEN  | SALESMAN  | 7698 | 1982-03-12 | 1600 |  300 |
|     30 |  7521 | WARD   | SALESMAN  | 7698 | 1838-03-12 | 1250 |  500 |
|     20 |  7566 | JONES  | MANAGER   | 7839 | 1981-03-12 | 2975 | NULL |
|     30 |  7654 | MARTIN | SALESMAN  | 7698 | 1981-01-12 | 1250 | 1400 |
|     10 |  7698 | BLAKE  | MANAGER   | 7839 | 1985-03-12 | 2450 | NULL |
|     20 |  7788 | SCOTT  | ANALYST   | 7566 | 1981-03-12 | 3000 | NULL |
|     10 |  7839 | KING   | PRESIDENT | NULL | 1981-03-12 | 5000 | NULL |
|     30 |  7844 | TURNER | SALESMAN  | 7689 | 1981-03-12 | 1500 |    0 |
|     20 |  7878 | ADAMS  | CLERK     | 7788 | 1981-03-12 | 1100 | NULL |
|     30 |  7900 | JAMES  | CLERK     | 7698 | 1981-03-12 |  950 | NULL |
|     20 |  7902 | FORD   | ANALYST   | 7566 | 1981-03-12 | 3000 | NULL |
|     10 |  7934 | MILLER | CLERK     | 7782 | 1981-03-12 | 1300 | NULL |
+--------+-------+--------+-----------+------+------------+------+------+
12 rows in set (0.00 sec)
```
## 2.select * from t_employee WHERE (sal, job) = (select sal,job from t_employee where ename = 'smith');用inner join 表示
```sql
select*from t_employee;
+--------+-------+--------+-----------+------+------------+------+------+
| deptno | empno | ename  | job       | MGR  | Hiredate   | sal  | comm |
+--------+-------+--------+-----------+------+------------+------+------+
|     20 |  7369 | SMITH  | CLERK     | 7902 | 1981-03-12 |  800 | NULL |
|     30 |  7499 | ALLEN  | SALESMAN  | 7698 | 1982-03-12 | 1600 |  300 |
|     30 |  7521 | WARD   | SALESMAN  | 7698 | 1838-03-12 | 1250 |  500 |
|     20 |  7566 | JONES  | MANAGER   | 7839 | 1981-03-12 | 2975 | NULL |
|     30 |  7654 | MARTIN | SALESMAN  | 7698 | 1981-01-12 | 1250 | 1400 |
|     10 |  7698 | BLAKE  | MANAGER   | 7839 | 1985-03-12 | 2450 | NULL |
|     20 |  7788 | SCOTT  | ANALYST   | 7566 | 1981-03-12 | 3000 | NULL |
|     10 |  7839 | KING   | PRESIDENT | NULL | 1981-03-12 | 5000 | NULL |
|     30 |  7844 | TURNER | SALESMAN  | 7689 | 1981-03-12 | 1500 |    0 |
|     20 |  7878 | ADAMS  | CLERK     | 7788 | 1981-03-12 | 1100 | NULL |
|     30 |  7900 | JAMES  | CLERK     | 7698 | 1981-03-12 |  950 | NULL |
|     20 |  7902 | FORD   | ANALYST   | 7566 | 1981-03-12 | 3000 | NULL |
|     10 |  7934 | MILLER | CLERK     | 7782 | 1981-03-12 | 1300 | NULL |
+--------+-------+--------+-----------+------+------------+------+------+
13 rows in set (0.00 sec)

mysql> select t1.deptno,t1.empno,t1.ename,t1.job,t1.mgr,t1.Hiredate,t1.sal,t1.comm
    -> from t_employee t1 inner join t_employee t2
    -> on t1.sal=t2.sal and t1.job=t2.job and(t2.ename='smith');
+--------+-------+-------+-------+------+------------+------+------+
| deptno | empno | ename | job   | mgr  | Hiredate   | sal  | comm |
+--------+-------+-------+-------+------+------------+------+------+
|     20 |  7369 | SMITH | CLERK | 7902 | 1981-03-12 |  800 | NULL |
+--------+-------+-------+-------+------+------------+------+------+
1 row in set (0.00 sec)
```
# 第五次作业
## 1.运行存储过程
```sql
DELIMITER $$
mysql> CREATE PROCEDURE proce_employee_sal1 ()
    -> BEGIN
    ->     SELECT sal
    -> FROM t_employee;
    -> END$$
Query OK, 0 rows affected (0.00 sec)

mysql> DELIMITER ;
mysql> CALL proce_employee_sal1();
+------+
| sal  |
+------+
|  800 |
| 1600 |
| 1250 |
| 2975 |
| 1250 |
| 2450 |
| 3000 |
| 5000 |
| 1500 |
| 1100 |
|  950 |
| 3000 |
| 1300 |
+------+
13 rows in set (0.01 sec)

Query OK, 0 rows affected (0.06 sec)
```
## 2.函数
```sql
DELIMITER $$
mysql> CREATE FUNCTION func_employee_sal (empno INT)
    -> RETURNS DOUBLE
    -> BEGIN
    ->     RETURN (SELECT sal FROM t_employee WHERE t_employee.empno = empno);
    -> END$$
Query OK, 0 rows affected (0.00 sec)

mysql> DELIMITER ;
mysql> SELECT func_employee_sal(7369);
+-------------------------+
| func_employee_sal(7369) |
+-------------------------+
|                     800 |
+-------------------------+
1 row in set (0.00 sec)
```
