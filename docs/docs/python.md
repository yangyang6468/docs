## python



####  clickhouse

```python
from clickhouse_driver import Client
client = Client(host='127.0.0.1',port='9000',user=clickhouse_user ,password=clickhouse_pwd)
sql = 'select * from db_name.tb_name limit 0, 1000'
ans = client.execute(sql)
```



####  *arg与**kwargs参数的用法

在函数调用时，*会以单个元素的形式解包一个元祖，使其成为独立的参数。

在函数调用时，**会以键/值对的形式解包一个字典，使其成为独立的关键字参数。



#### request包使用

<img src=".\assets\image-20220531150539026.png" alt="image-20220531150539026" style="zoom: 150%;" />



#### python & mysql

```python
python读取mysql字段为datetime格式时候类型为datetime.datetime 格式转换方法:str.timeftime("%Y-%m-%d %H:%M:%S")
```