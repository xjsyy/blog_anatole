---
title: "Linux Learn"
date: 2023-04-30T02:25:42-05:00
categories: ["Linux"]
---

  在 [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) 中学到的一些知识.

```bash
    `sudo`:"super user do"something.
```

```bash
missing:~$ ls -l /home
drwxr-xr-x 1 missing  users  4096 Jun 15  2019 missing
```

`r`:read	`w`:write	`x`:execute这条命令指出了　用户(`missing`)/用户组(`user`)/其他人　对该文件的使用权限．`－`表示无权限

### Vim 移动

- 基本移动: `hjkl` （左， 下， 上， 右）
- 词： `w` （下一个词）， `b` （词初）， `e` （词尾）
- 行： `0` （行初）， `^` （第一个非空格字符）， `$` （行尾）
- 屏幕： `H` （屏幕首行）， `M` （屏幕中间）， `L` （屏幕底部）
- 翻页： `Ctrl-u` （上翻）， `Ctrl-d` （下翻）
- 文件： `gg` （文件头）， `G` （文件尾）
- 行数： `:{行数}<CR>` 或者 `{行数}G` ({行数}为行数)
- 杂项： `%` （找到配对，比如括号或者 /* */ 之类的注释对）
- 查找： `f{字符}`,`t{字符}` ,`F{字符}`,`T{字符}`
  - 查找/到 向前/向后 在本行的{字符}
  - `,` / `;` 用于导航匹配
- 搜索: `/{正则表达式}`, `n` / `N` 用于导航匹配
