# SQL常用命令及其书写顺序

```
select *
from
```

##查询

```sql 
select	*    	#查询列
from	table1
limit	3;		#显示第三行数据
```

去重

##distinct 会吧它后面的所有的字段全部去重

```sql
select distinct investdays，
				age
from  table1
where investment >10000 and investment <40000;#条件筛选  where这里可以写很多的条件判断
```

##as生成新的列（重命名）

```sql
select	*  #查询列
		age+score as other#新的列为other列
from	table1
limit	3;		#显示第三行数据
```

##拼接字段concat

```sql
select concat(字段1，字段2) as '新字段名'
from 表名;
```

## 数据分组

语法结构：

```sql
select   字段,计算字段
from 	 表名
where	 查询条件
group by 字段
having 条件；#对组别进行筛选
```

## having与where的区别

having对分组后进行筛选  where对分组前进行筛选

## order by排序

```sql
select   字段,计算字段
from 	 表名
where	 查询条件
group by 字段
having 条件#对组别进行筛选
order by investday desc；#进行排序
```

