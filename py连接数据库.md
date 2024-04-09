```
import pymysql
import pandas as pd

conn=pymysql.connect(
    host="localhost",
    port=3306,
    user="root",
    password="123456",
    database="01"  # 连接的数据库
)
#游标
cur=conn.cursor()//告诉开始使用数据库了
cur2=conn.cursor()
sql = "insert into men(name, age, address) values ('燕归来', '18', '八宝山')"
cur.execute(sql )

result=cur.fetchall()#将回传的资料弄出来show 的时候用
for r in records：
	print(r)


print("执行完毕!")




#提交事务
conn.commit()
cur.close()  # 断开cursor
conn.close()  # 断开连接
```