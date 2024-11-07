---
title: linux 技巧
date: 2024-11-03 12:02:16
categories:
- linux
- 常用命令
tags:
- 奇技淫巧
---

# grep -rl '关键字'

> 递归查找当前目录下内容包含关键字的文件，并且最终输出文件名

-r: 递归查找

-l: 仅输出文件名



> Tips: 如果不想递归查找， 可执行 grep -l 'xx' *
>
> 如果要找隐藏文件，执行 grep -l 'xx' .**



# find . -type d -exec rm -rf {} +

删除目录下所有的文件夹

- find . -type d 找到所有目录类型文件

- -exec rm -rf 执行删除指令

- {} 是占位符，表示所有 find 找到的项目

- +和/ 可以互换， + 表示一次性删除， / 表示顺次删除

  - +:`rm -rf dir1 dir2 dir3 ... dir10`

  - /:

    ```
    rm -rf dir1
    rm -rf dir2
    rm -rf dir3
    ...
    rm -rf dir10
    
    ```

  
