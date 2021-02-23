数据库命令要用分号结尾

1. show databases; // 显示数据库
mysql> show databases; 
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| test               |
+--------------------+
4 rows in set (0.01 sec) // 有四个库

2. mysql> use test; // 打开一个数据库
Database changed
mysql> show tables;
Empty set (0.00 sec)

3. mysql> show tables from mysql; // 显示某个库中的表
mysql> show tables;
+----------------+
| Tables_in_test |
+----------------+
| stuinfo        |
+----------------+
1 row in set (0.00 sec)

4. mysql> select database(); // 显示目前所在的库
+------------+
| database() |
+------------+
| test       |
+------------+  // 当前库为test库
1 row in set (0.00 sec)

5. mysql> select version(); // 显示版本
+-----------+
| version() |
+-----------+
| 5.5.62    |
+-----------+
1 row in set (0.00 sec)

C:\WINDOWS\system32>mysql --version
mysql  Ver 14.14 Distrib 5.5.62, for Win64 (AMD64)

C:\WINDOWS\system32>mysql -V
mysql  Ver 14.14 Distrib 5.5.62, for Win64 (AMD64)

C:\WINDOWS\system32>

6. mysql> create table stuinfo( // 创建表： 表名字（列名 类型，列名 类型）；
    -> id int,
    -> name varchar(20));
Query OK, 0 rows affected (0.01 sec)

7. mysql> desc stuinfo;  // 查看表的描述信息: desc 表名
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | YES  |     | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)
mysql> select * from stuinfo; // 查看表的内容：select * from 表名
Empty set (0.00 sec)

8. mysql> insert into stuinfo (id, name) value(2, 'jack'); // 插入一项数据
Query OK, 1 row affected (0.00 sec)

mysql> select * from stuinfo;
+------+------+
| id   | name |
+------+------+
|    1 | john |
|    2 | jack |
+------+------+
2 rows in set (0.00 sec)

mysql> update stuinfo set name='lilei' where id=1 
    -> ;  // 更新数据项
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from stuinfo;
+------+-------+
| id   | name  |
+------+-------+
|    1 | lilei |
|    2 | jack  |
+------+-------+
2 rows in set (0.00 sec)
mysql> delete from stuinfo where id=1
    -> ; // 删除一项
Query OK, 1 row affected (0.01 sec)

mysql> select * from stuinfo;
+------+------+
| id   | name |
+------+------+
|    2 | jack |
+------+------+
1 row in set (0.00 sec)

9. mysql> exit  // 退出mysql
Bye

C:\WINDOWS\system32>
