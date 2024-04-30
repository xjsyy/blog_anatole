---
title: "Zsh_install"
date: 2024-04-30T01:29:27-04:00
Description: ""
Tags: [zsh]
Categories: [shell]
DisableComments: false
---
> 极简教程。。。

## 安装

```shell
sudo apt install zsh -y
```

## 将`zsh`设置为默认的Shell

```shell
chsh -s $(which zsh)
```

## 安装`Oh My Zsh`插件

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## 安装`powerlevel10k`/`autosuggestions`/`autosyntaxhighlighting`插件

```shell
# powerlevel10k 主题：
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

# zsh-autosuggestions自动补全插件：
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# zsh-syntax-highlighting语法高亮插件：
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting      
```

  然后编辑`.zshrc`文件，找到下列属性，修改成下列内容即可：

```shell
ZSH_THEME="powerlevel10k/powerlevel10k"
plugins=(git
        zsh-autosuggestions
        zsh-syntax-highlighting
        )
```

然后输入命令：

```shell
zsh
```

然后根据提示完成即可。。。
