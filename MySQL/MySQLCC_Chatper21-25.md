## Chapter 21 	创建表
1.	创建表  
a.	表创建基础  
CREATE TABLE(column_name int NOTNULL AUTO_INCREMENT  
…  
…)  
b.	使用null值  
c.	主键：必须唯一，不允许null；PRIMARY_KEY() 多个列逗号分隔  
d.	使用auto_increment：每个表一个，必须被索引，可手动insert；SELECT last_insert_id()返回最后一个值  
e.	指定默认值：DEFAULT  
f.	引擎类型：innoDB，MEMORY，MyISAM  
2.	更新表 ALTER TABLE  
添加ALTER TABLE table_name ADD new_column type;  
删除ALTER TABLE table_name DROP COLUMN column_name;  
定义外键 ALTER TABLE table_name ADD CONSTRIANT table_name FOREIGN KEY(column) REFERENCES orders (order_num);  
复杂的更改：copy，删除现在的表，重命名新表  
3.	删除表 DROP TABLE table_name;  
4.	重命名表 RENAME TABLE … TO …；  

## Chapter 22 	使用视图
1.	视图  
虚拟的表，只包含使用时动态检索数据的查询  
a.	为什么用：重用SQL，简化复杂操作，使用表的组成部分，保护数据，更改数据格式和表示  
b.	规则和限制：唯一命名，没有数量限制，要有访问权限，可以嵌套，不能索引/有关联的触发器或默认值，可以和表一起使用  
2.	使用视图  
CREATE VIEW 创建  
SHOW CREATE VIEW viewname; 查看  
DROP VIEW viewname; 删除  
更新：先DROP在CREATE 或 CREATE OR REPLACE VIEW   
a.	利用视图简化复杂的联结  
CREATE VIEW AS … SELECT… FROM…  
b.	用视图重新格式化检索出的数据  
c.	用视图过滤不想要的数据  
d.	使用视图与计算字段  
e.	更新视图：insert, update, delete – 实际更新基表；但视图有分组、联结、子查询、并、聚集函数、distinct、导出列 则不能更新  

## Chapter 23 	使用存储过程
1.	存储过程  
为以后的使用而保存的一条或多条与剧集和  
2.	为什么要用  
封装简化复杂操作；统一步骤完整性；安全性；提高性能；更灵活  
3.	使用存储过程  
a.	执行：CALL procedure_name(@ , @ , @);  
b.	创建：CREATE PROCEDURE 名(列举参数) BEGIN … END;  
c.	删除：DROP PROCEDURE name; 或+ IF EXISTS  
d.	使用参数：IN 传入 OUT 传出 INOUT 传入和传出  
不能通过一个参数返回多个行和列  
e.	建立智能存储过程：  
DECLARE 定义局部变量：变量名，数据类型  
使用COMMENT ‘’ 在SHOW PROCEDURE STATUS显示  
f.	检查存储过程 SHOW CREATE PROCEDURE name; SHOW PROCEDURE STATUS LIKE ‘name’;  

## Chapter 24 	使用游标
1.	游标(cursor)  
要在检索出来的行中前进或后退一行或多行，主要用于交互式应用  
是被语句检索出来的结果集，在MySQL中，只用于存储过程和函数  
2.	使用游标  
声明+打开+检索取出+关闭  
a.	创建游标：DECLARE name CURSOR  
b.	打开OPEN name; 关闭CLOSE name;  
c.	使用游标数据：FETCH  
CREATE PROCEDURE processorders()  
BEGIN  
	DECLARE done BOOLEAN DEFAULT 0;  
	DECLARE o INT;  
	DECLARE t DECIMAL(8,2);  
	DECLARE ordernumbers CURSOR;  
	FOR  
	SELECT order_num FROM orders;  
	DECLARE CONTINUE HANDLER FOR SQLSTATE ‘02000’ SET done = 1;   
CREATE TABLE IF NOT EXISTS ordertotals (order_num INT, total DECIMAL (8,2));  
OPEN ordernumbers;  
REPEAT  
	FETCH ordernumbers INTO o;  
	CALL ordertotal(0,1,t);  
	INSERT INTO ordertotals (order_num, total) VALUES (o,t);  
UNTIL done END REPEAT;  
CLOSE ordernumbers;  
END;  

## Chapter 25 	使用触发器
1.	触发器  
要某条语句在事件发生时自动执行  
2.	创建触发器  
a.	唯一命名+关联的表+响应的活动+何时执行 CREATE TRIGGER  
b.	触发器仅支持表，不支持视图；一个表最多6个；单一触发器不与多个表/事件关联  
c.	触发器失败：before失败，不执行操作；before或语句本身失败-不执行after  
3.	删除触发器 DROP TRIGGER name;  
4.	使用触发器  
a.	Insert触发器：可引用一个名为new的虚拟表，访问被插入的行；BEFORE INSERT触发器中，new值可更新  
b.	Delete触发器：可饮用old的虚拟表访问被删除的行  
c.	Update触发器：可以引用old表、new表；old表只读不更新  
