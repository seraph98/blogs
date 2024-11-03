---
title: linux 技巧
date: 2024-11-03 12:02:16
categories: linux 常用命令
tags: 奇技淫巧
---

# grep -rl '关键字'

> 递归查找当前目录下内容包含关键字的文件，并且最终输出文件名

-r: 递归查找

-l: 仅输出文件名



> Tips: 如果不想递归查找， 可执行 grep -l 'xx' *
>
> 如果要找隐藏文件，执行 grep -l 'xx' .**

