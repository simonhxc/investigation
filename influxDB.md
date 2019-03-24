#influxDB使用
- influxDB安装后，默认开启8086端口
- 连接influx `influx -host <ip> -port <port>`
- 数据库操作
   - 创建数据库
      - `create database <database_name>`
   - 查询所有数据库
      - `show databases`
   - 删除数据库
      - `drop database <database_name>`
   - 使用指定数据库
      - `use <database_name>`
- 表操作
   - 创建表
      - 在插入数据时若表不存在，则自动创建
   - 查询所有表
      - `show measurements`
   - 删除表
      - `drop measurement <measurement_name>`
- 数据操作
   - 插入数据
      - `insert <measurement_name>,<tag>=<tag_context> value=<value> [time]`
      - 例如：insert testDB,order=MP001 value=1 150000(不指定time则默认使用当前时间戳)
   - 数据查询
      - `select * from <measurement_name>`
      - `select * from <measurement_name> where ["tag"='tag_context']`(注意单、双引号)
- series操作
   - `show series from <measurement_name>`(目前不知道有什么意义)
##疑问列表
```
create database testDB
use testDB
insert point,order=test1 value=1.1 1
insert point,order=test1 value=1.2 1//插入tag相同的数据，会覆盖原数据
insert point,order=test1,project=p1 value=1.3 1//会创建一条新数据
select * from point where "order"='test1'//会取出两条数据，如果生产情况有这种情况，需要去除重复数据

```

