SQL语言

关联式sql mysql oracle sqlserver

非关联 mogoDB Redis 



#什么是SQL？

结构性查询语言，与数据库（关联式数据库）进行沟通

#概念

主键 primary key 唯一的表示每一个数据（类似身份证号）

外键 ：对应另一张表的主键（必须），也可以对应回自己的表 foreign key

复合主键：主键可以包含多个属性

可以同时把一个属性设置为主键与外键

# sql语法

##数据库

1.创建数据库

```sql
create database `名字`；反引号 esc下面的
show database  关键字用大写
```

2.删除数据库

```sql
DROP DATABASE `XXX`;
```

## 表格

1.选择数据库使用

```SQL
USE `XXX`;
```

2.创建表

数据类型：

​		INT                       --整数

 		DECIMAL(m,n)  - -#m总位数，n表示小数点占的位数

​		VARCHAR(N)      --N表示字段长度

​		BLOB                   ---存放二进制 图片影片档案

​		DATE		     --存放日期 'YYYY-MM-DD'

​		TIMESTAMP  	--存放时间

```SQL
CREATE TABLE `student`(
	`student_id` INT PRIMARY KEY,
	'name'	VARCHAR(20),	
    `major` VARCHAR(20) #最后不用写，
);
DESCRIBE `student`;
DROP TABLE 'student';
```

3.新增属性

```SQL
ALTER TABLE `student` ADD `gpa` DECIMAL(3,2);
ALTER TABLE `student` DROP COLUMN `gpa`;#删除	
```

## 存储数据

顺序要与表属性的顺序一样

```sql
INSERT INTO `student` VALUES(1,'白'，'历史');
或者自己决定顺序
INSERT INTO `student`(`name`,`major`,`student_id`) VALUES('白'，'历史',1);
INSERT INTO `student`(`name`,`major``) VALUES('白'，'历史');
```

### 查询

```sql
SELECT * FROM `XXX表名`;
```

###约束

```sql
CREATE TABLE `student`(
	`student_id` INT PRIMARY KEY,
	'name'	VARCHAR(20) NOT NULL,	#不能为空
    `major` VARCHAR(20) #最后不用写，
);
DESCRIBE `student`;
DROP TABLE 'student';
```

### 更新

将科目为中文的改成英语的

```SQL
UPDATE `STUDENT`
SET `MAJOR` =`ENGLISH`
WHERE `MAJOR`=`CHINESE`;
```

