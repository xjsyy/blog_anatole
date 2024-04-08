---
title: "Docker_Ubuntu_install"
date: 2024-04-08T01:17:28-04:00
Description: ""
Tags: [Docker]
Categories: [Linux]
DisableComments: false
---

1. 运行下面的命令以卸载所有冲突的包
```shell
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```
```shell
# 添加Docker官方的 GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# 添加仓库到Apt源:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
```

2. 安装最新版Docker包
```shell
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

3. 验证Docker是否安装成功
```shell
sudo docker run hello-world
```
PS:

1. Docker换源：`download.docker.com` => `mirrors.ustc.edu.cn/docker-ce`.
2. Docker镜像换源：编辑或新建`/etc/docker/daemon.json`文件，向其中添加`registry-mirrors`项，使最终配置类似：
```
{
  "registry-mirrors": ["https://docker.mirrors.sjtug.sjtu.edu.cn"]
}
```
