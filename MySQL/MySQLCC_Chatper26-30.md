## Chapter 26 	管理事务处理  
1.	事务处理(transaction processing)  
InnoDB支持，MyISAM不支持  
事务指一组MySQL语句：rollback, commit, savepoint  
2.	控制事务处理  
开始 START TRANSACTION  
a.	ROLLBACK：可以回退insert、update、delete；不能回退select、create、drop  
b.	使用commit：使仅在不出错时发生更改  
c.	使用保留点：创建占位符SAVEPOINT delete 1;  
ROLLBACK TO delete 1;回退到本点  
d.	更改默认的提交行为 SET autocommit = 0; 不自动提交更改  

## Chapter 27 	全球化和本地化
1.	字符集和校对顺序  
2.	使用字符集和校对顺序  
SHOW CHARACTER SET;  
SHOW COLLATION  
SHOW VARIABLES LIKE ‘character%’;  
SHOW VARIABLES LIKE ‘collation%’;  
DEFAULT CHARACTER SET hebrew;  
COLLATE hebrew_general_ci;  

## Chapter 28 	安全管理  
1.	访问控制：MySQL administrator  
2.	管理用户  
USE mysql;  
SELECT user FROM user;  
a.	创建账号  
CREATE USER ben IDENTIFIED BY ‘password’;  
RENAME USER ben TO beforta;  
b.	删除用户账号  
DROP USER bforta;  
c.	设置访问权限  
SHOW GRANTS FOR bforta; 查看权限  
GRANT SELECT ON db_name.* TO bforta;  
REVOKE SELECT ON db_name.* FROM bforta; 撤销  
层次：整个服务器 – 整个库- 特定表 – 特定列 – 特定的存储过程  
若某表、库被drop，权限依然存在  
简化多次授权：GRANT SELECT, INSERT ON db_name.* TO bforta;  
d.	更改口令  
SET PASSWORD FOR bforta = Password (‘new password’);  

## Chapter 29 	数据库维护  
1.	备份数据  
使用：mysqldump; mysqlhotcopy; BACKUP TABLE 或 SELECT INTO OUTFILE  
2.	进行数据库维护  
ANALYZE TABLE orders; 检查表键是否正确  
CHECK TABLE orders, orderitems; 对索引进行检查  
REPAIRE TABLE 修复相应表  
OPTIMIZE TABLE 从表中删除大量数据时，收回所用空间  
3.	诊断启动问题  
4.	查看日志文件  
  
## Chapter 30 	改善性能
