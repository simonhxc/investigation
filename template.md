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
