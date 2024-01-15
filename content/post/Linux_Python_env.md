---
title: "Linux_Python_env"
date: 2024-01-14T22:37:04-05:00
Description: ""
Tags: ["Python"]
Categories: ["Linux"]
DisableComments: false
---
本文介绍简单配置Ubuntu Python环境。

首先，下载[Python](https://www.python.org/downloads/)压缩包：

```bash
wget https://www.python.org/ftp/python/<版本号>/Python-<版本号>.tgz
```

解压：

```bash
tar xzf Python-<版本号>.tgz
```

进入该文件夹后，有一个`configure`文件，执行命令：

```bash
sudo ./configure --enable-optimizations
```

然后执行：

```bash
sudo make altinstall
```

        该命令用于在系统的默认Python版本旁边安装另一个版本。这对于在同一系统上管理不同的Python版本而不影响依赖于默认Python版本的系统工具和应用程序非常有用。

结束！
