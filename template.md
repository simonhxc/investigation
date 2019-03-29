- `netstat -ano`查找端口占用pid
- `tasklist|findstr "<pid>"` 查找pid资源

- vcm.LiveStreamingServer已修改ids,已提交,mergeRequest
- vcm.backend已修改ids,已提交,mergeRequest
- pdm已修改ids,已提交,mergeRequest
- backend已添加vcm,pdm的ids配置,已提交,mergeRequest


- VS2019 View - OtherWindows - C# interactive 可以打开即时运行C#代码的命令窗口
- VS2019 Tools - Create GUID可以快捷的生成一个GUID
- Guid.NewGuid()用于生成新的Guid
- 123456转MD5`e10adc3949ba59abbe56e057f20f883e`
- influxDB查看是否一个时间点*查询一定会显示所有列？
- influxDB连续查询
- <measurement>[,<tag-key>=<tag-value>...] <field-key>=<field-value>[,<field2-key>=<field2-value>...] [unix-nano-timestamp] 
- influxDB支持HTTP查询？
- rm * 
- rm <file_name>
- cat>><file_name>
- vi <file_name>



#设置代理
export http_proxy=http://192.168.174.1:1080
export https_proxy=https://192.168.174.1:1080
export http_proxy=socks://192.168.174.1:1080
export http_proxy=sock4://192.168.174.1:1080
export http_proxy=sock5://192.168.174.1:1080
#如果需要账号密码
export http_proxy=username:password@127.0.0.1:1080
#删除代理
unset http_proxy
unset https_proxy

- 撤销所有未缓存的修改  git checkout .
- 撤销已经添加到缓存的修改 git reset HEAD .
- Task.FromResult<>
- 弹出框，积极的按钮放在右边

- `service.byzan.iubang.com` 和 `byzan.iubang.com`是同一个IP
- `docker ps`查看所有在运行的容器
- docker曾经使用过的去outlook中查看
- `http://byzan.iubang.com:13606`查看自动发送程序 

- select HP1_FuZaiE1Z1Perc,HP1_FuZaiE1Z2Perc from RealtimePoints where DeviceNo='433-14' AND TenantId='9999900101' AND time >= '2018-03-29 17:00:00.000' AND time < '2019-03-29 17:00:20.000'

- influxDB查询的时候，不能使用*,要根据device取出所有的码点
- 考虑查询的时候，把时间转换为时间戳，（需要考虑influxDB是以纳秒为计量单位的）
- 查询数据库或查询表做成从配置读取？