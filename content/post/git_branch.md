---
title: "Git branch"
date: 2024-01-08T06:20:08-05:00
Description: "git branch simple command"
Tags: ["GIT"]
Categories: ["GIT"]
DisableComments: false
---

Several commands related to the git branch.

### 创建分支:

```shell
git branch test　＃以"test"分支为例子 
```

### 切换分支

```bash
git checkout test
```

### 合并分支

如果你想要把`test`分支合并到`master`分支：

```bash
git checkout master #先切换回master分支
git merge test #合并操作
```

### 如果你想在合并后把原来的分支删除：

```bash
git branch -d test	#删除本地分支
git push origin --delete test	#删除远程分支
```
