- `netstat -ano`查找端口占用pid
- `tasklist|findstr "<pid>"` 查找pid资源
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
