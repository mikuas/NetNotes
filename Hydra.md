### Hydra
hydra 的基本命令格式
~~~bash
hydra [options] server://IP/URL

## 常用语法
~~~bash
# 指定服务和目标
hydra -l <userName> -p <password> <IP> <server>

# 对FTP服务进行单用户密码爆破
hydra -l admin -p 123456 192.168.1.1 ftp

# 使用用户名和密码字典
hydra -L <userNameDict> -P <passwordDict> <IP> <server>
~~~

## SSH爆破
~~~bash
hydra -L <userNameDict> -P <passwordDict> ssh@IP
# 指定端口
hydra -s PORT -L <userNameDict> -P <passwordDict> ssh://IP
~~~

## HTTP登录页面爆破
~~~bash
# HTTP GET
hydra -L <userNameDict> p <passwordDict> http-get://IP/

# HTTP POST 表单
hydra -L <userNameDict> -P <passwordDict> <IP> http-post-from "/login:username=^USER^&password=^PASS^:F=Login failed"

# 使用代理 添加
-x <socks5://proxy>

# 设置线程
-t <number>
~~~

## Telnet爆破
~~~bash
hydra -L <userNameDict> -P <passwordDict> telnet://IP
~~~