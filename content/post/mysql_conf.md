---
title: "Mysql_conf"
date: 2024-04-30T23:02:18-04:00
Description: ""
Tags: [MySQL]
Categories: [DB]
DisableComments: false
---
### 登录

```shelll
mysql -u root -o <password>
```

### Ubuntu系统下查看密码

```shell
cat /etc/mysql/debian.cnf
```

### 修改密码（密码忘记情况下 ）

```shell
mysql -u debian-sys-maint -p; # 连接数据库
use mysql; # 选择数据库
----
alter user 'root'@'%' identified with mysql_native_password by '123456';# 更改密码
----
# 5.7.9v及以上用上述命令，5.7.9v以下则选用下面其中一个即可
----
update user set password=Password("123456") where user = 'root';# 更改密码
update user set authentication_string=Password("123456") where user = 'root';# 更改密码
----
flush privileges;# 刷新权限
\! clear # 清屏
```

### 设置支持远程访问

```shell
show  variables like '%port%';
select user, host from user where user = 'root'; 
```

如果`host`不是`%`，用`update`修改为`%`即可。<span style="color:red">这种做法极不安全，不要在生产环境里面这样做！！！</span>

#### MySQL监听地址

```shell
sudo vim /etc/mysql/mysql.conf.d/mysqld.conf
```

默认只监听本地ip，无法从外部链接MySQL,可以设置为

```
bind-address = 0.0.0.0
mysqlx-bind-address = 0.0.0.0
```
