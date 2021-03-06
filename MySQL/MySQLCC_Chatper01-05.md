## Chapter 1 	了解SQL
1.	数据库基础  
数据库database, 数据库软件DBMS  
表table, 模式schema, 列column, 数据类型datatype, 行row, 记录record  
主键primary key: 一列或一组列，其值能为以区分表中每行；不在主键列使用可能更新的值  
2.	什么是SQL (Structured Query Language)  

## Chapter 2 	MySQL简介
1.	什么是MySQL  
2.	MySQL工具  
Mysql -u ben -p -h myserver -p 9999  

## Chapter 3 	使用MySQL
1.	连接
2.	选择数据库
USE crashcourse; //使用crashcourse库
3.	了解数据库和表  
SHOW databases; //返回可用库的列表  
SHOW tables; //获取一个库内的表  
SHOW columns from customers; //MySQL 支持describe作为show columns from的快捷方式  
SHOW status;  
SHOW create database;  
SHOW create table;  
SHOW grants; //显示用户权限  
SHOW errors; SHOW warnings; //显示服务器错误或警告  

## Chapter 4 	检索数据
1.	SELECT语句  
2.	检索单个列  
SELECT prod_name FROM products;  
3.	检索多个列  
SELECT prod_id, prod_name, prod_price FROM products;  
4.	检索所有列  
SELECT * FROM products;  
5.	检索不同的行：DISTINCT
SELECT DISTINCT vend_id FROM products;  
6.	限制结果： LIMIT  
SELECT prod_name FROM products LIMIT 5; //返回<5行  
SELECT prod_name FROM products LIMIT 5,5; //从行5开始的5行，第一行为行0  
MySQL支持LIMIT 4 OFFSET 3; 等用于LIMIT3,4 //从行3开始取4行  
7.	使用完全限定的表名  
SELECT products.prod_name FROM products;  
SELECT products.prod_name FROM crashcourse.products;  

## Chapter 5 	排序检索数据
1.	排序数据: ORDER BY  
SELECT prod_name FROM products ORDER BY prod_name;  
子句 clause  
2.	按多个列排序  
SELECT prod_id, prod_price, prod_name FROM products ORDER BY prod_price, prod_name;  
3.	指定排序方向  
降序DESC，升序ASC（默认）  
SELECT prod_id, prod_price, prod_name FROM products ORDER BY prod_price DESC, prod_name;  
DESC只应用于直接位于其前边的列名，多列上降序要对每列指定DESC  
SELECT prod_price FROM products ORDER BY prod_price DESC LIMIT 1; //结合order by, limit找最高/最低值  
