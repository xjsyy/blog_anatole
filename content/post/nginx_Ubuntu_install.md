---
title: "Nginx_Ubuntu_install"
date: 2024-04-08T01:13:17-04:00
Description: ""
Tags: [Nginx]
Categories: [Linux]
DisableComments: false
---
## Step 1—先更新系统在安装Nginx：

```shell
sudo apt update
sudo apt install nginx
```

## Step 2—调整防火墙：

使用以下命令列出UFW已知的应用程序配置列表

```shell
sudo ufw app list
```
应该输出

```shell
Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
```
如果没有
```shell
sudo ufw allow 'Nginx HTTP'
sudo ufw status
```
输出如下
```shell
Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere                  
Nginx HTTP                 ALLOW       Anywhere                  
OpenSSH (v6)               ALLOW       Anywhere (v6)             
Nginx HTTP (v6)            ALLOW       Anywhere (v6)
```
## Step 3—检查你的Web Server：

```shell
systemctl status nginx
```
输出如下
```shell
nginx.service - A high performance web server and a reverse proxy server
   Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
   Active: active (running) since Fri 2020-04-20 16:08:19 UTC; 3 days ago
     Docs: man:nginx(8)
 Main PID: 2369 (nginx)
    Tasks: 2 (limit: 1153)
   Memory: 3.5M
   CGroup: /system.slice/nginx.service
           ├─2369 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
           └─2380 nginx: worker process
```
## Step 4—管理Nginx进程：
```shell
sudo systemctl stop nginx
sudo systemctl start nginx
sudo systemctl restart nginx
sudo systemctl reload nginx # execute when you make configuration changes
sudo systemctl disable nginx # enable start automatically
sudo systemctl enable nginx
```
