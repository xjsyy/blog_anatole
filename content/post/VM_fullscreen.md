---
title: "VM_fullscreen"
date: 2023-09-07T05:32:33-05:00
categories: ["Linux"]
tags: ["VM"]
---

Debian虚拟机全屏,首先找到配置文件
```bash
su      #管理员目录
cd /etc/apt
cp sources.list sources.list.bak  #备份sources.list文件
```
将文件内容**替换**为下列内容，即更改[软件源](https://mirrors.ustc.edu.cn/help/debian.html)
```tex
deb http://mirrors.ustc.edu.cn/debian stable main contrib non-free non-free-firmware
# deb-src http://mirrors.ustc.edu.cn/debian stable main contrib non-free non-free-firmware
deb http://mirrors.ustc.edu.cn/debian stable-updates main contrib non-free non-free-firmware
# deb-src http://mirrors.ustc.edu.cn/debian stable-updates main contrib non-free non-free-firmware

# deb http://mirrors.ustc.edu.cn/debian stable-proposed-updates main contrib non-free non-free-firmware
# deb-src http://mirrors.ustc.edu.cn/debian stable-proposed-updates main contrib non-free non-free-firmware
```

```bash
apt update 
apt install build-essential dkms linux-headers-$(uname -r) #更新
```

然后点击虚拟机的“安装增强功能”


```bash
cd /media
cd cdrom
cp VBoxLinuxAdditions.run /tmp
cd /tmp
./VBoxLinuxAdditions.run
```

然后重启，可以从虚拟机选择全屏模式了
