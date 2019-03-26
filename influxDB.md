#influxDB使用  
##写在前面
- windows开启虚拟机安装的ubuntu
1. ubuntu系统中使用`ifconfig`查看ip
2. 使用gitBash的ssh连接虚拟机中的ubuntu系统`ssh <user>@<IP>`

##安装
1. `wget https://dl.influxdata.com/influxdb/releases/influxdb_1.7.4_amd64.deb`
2. `sudo dpkg -i influxdb_1.7.4_amd64.deb`
- 在Influxd.exe所在目录执行`.\influxd.exe`，即可启动influxDB


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
- 数据保留策略
   - `show retention policies on telegraf`
   - 需要研究一下，数据默认永久保存
##疑问列表
```
create database testDB
use testDB
insert point,order=test1 value=1.1 1
insert point,order=test1 value=1.2 1//插入tag相同的数据，会覆盖原数据
insert point,order=test1,project=p1 value=1.3 1//会创建一条新数据
- tag被当作了类似主键的东西
select * from point where "order"='test1'//会取出两条数据，如果生产情况有这种情况，需要去除重复数据？

insert point,order=test1 value=1,code="codeTest1" 1
select * from point where code = 'codeTest1'
插入时字符串用""， 查询时字符串用''
```
group by 参数只能是time和tag?
对时间字符串格式要求只能是yyyy-MM-dd HH:mm:ss??
- yyyy/MM/dd失败
存入influxDB的时间戳为UTC
调查一下UTC,Unix时间戳，是否有UTC时间戳的说法？

&lt;&gt;转义字符,因为markDown中认为尖括号是html的符号

select mean(code1) from point where time > '2019-03-26 14:00:00' and time < '2019-03-26 15:00:00'and device='no1' group by time(1m)