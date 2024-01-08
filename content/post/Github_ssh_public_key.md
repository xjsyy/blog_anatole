---
title: "Github_ssh_public_key"
date: 2024-01-08T06:34:08-05:00
Description: "配置Github sh连接"
Tags: ["GIT"]
Categories: ["GIT"]
DisableComments: false
---

```bash
ssh-keygen -t ed25519
```

按照提示完成三次回车，即可生成 ssh key。

查看公钥

```bash
cat ~/.ssh/id_ed25519.pub
```

然后将内容复制到`setting->SSH and GPG keys->New SSH key`.

如果更改了ssh密钥对的文件名(未采用"id_ed25519"默认文件名),须在配置文件(config)里面添加配置信息:

```
Host github.com
    IdentityFile ~/.ssh/<公钥文件文件名>
```
