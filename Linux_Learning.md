# Linux Learning

## 初识shell

1. External → Shell → Linux
2. bash : Bourne Again Shell, 简称bash
   Linux 默认的shell
3. 初始shell

- 创建
创建以.sh为扩展名的文件
vi hello.sh

- 编辑
第一行以 `#!` 开头，声明所使用shell的全路径（`#!`：shebang符号）
`#!/usr/bin/bash/` ：表示该脚本用/usr/bin/bash/解释器执行）
不可以用shell的bash解释器去执行.py文件，同理也不可以用python解释器去执行shell文件
`#!/usr/bin/bash`：该解释器，只有当在shell中没有输入执行命令时(e.g. pingg01.sh)，才会生效

注释
使用 `#` 作为注释符号
e.g.
```
#!/bin/bash
# print “Hello World!”
echo “Hello World!”
```

- 增加脚本文件执行权限
    'chmod +x XXX.sh #所有用户均对该脚本有执行权限'
    'chmod 755 XXX.sh '

e.g. 
  1. -rwxr-xr-x 1 jingsheng jingsheng   17 Feb 29 18:44 date_755.sh*
  2. -rwxrwxrwx 1 jingsheng jingsheng   17 Feb 29 18:40 date_777.sh*
  3. -rwxrwxr-x 1 jingsheng jingsheng   17 Feb 29 18:43 date_x.sh*

- 运行脚本方法

  1. 进入脚本目录
  cd /home/jingsheng/script
  
  2. 运行脚本
     - ./XXX.sh # 运行脚本
     - 以/bin/sh XXX.sh 来运行脚本
       e.g. /bin/sh hello.sh
     - bash XXX.sh 可以运行脚本，无需权限
  3. Difference(source / sh / bash / ./)
       - `source a.sh`
       在当前shell内去读取、执行a.sh，而a.sh不需要有"执行权限"
       source命令可以简写为"."
       - `sh a.sh`
         `bash a.sh`
          都是打开一个subshell去读取、执行a.sh，而a.sh不需要有"执行权限"
          通常在subshell里运行的脚本里设置变量，不会影响到父shell的。
       ```
       ./a.sh
       #bash: ./a.sh: 权限不够
       chmod +x a.sh
       ./a.sh
       ```
       打开一个subshell去读取、执行a.sh，但a.sh需要有"执行权限"
       可以用`chmod +x`添加执行权限

## 符号表达
1. 通配符(元字符)
  - `*`：匹配任意多个字符
    e.g. ls *.pdf 
    显示该文件中所有的PDF文件
  - `？`：匹配一个字符
    e.g. ls L?ve.pdf
    显示LXve.pdf的文件 X代表不确定字符
  - `[]`：匹配括号中任意一个字符
  - `()`：在子shell中执行
  - `{}`：集合touch file{}
  - `\`：转义字符，让元字符回归本意


## 变量
1. 自定义变量(类别C,局部变量)
  - 定义变量
    变量名 = 变量值
    e.g. ip1 = 192.168.1.1
  - 引用变量
    $变量名/${变量名}
    e.g. $ip1
  - 查看变量
    echo $变量名
    e.g. echo $ip1
  - 作用范围
    仅在当前shell中生效

2. 环境变量(类比C,全局变量)
  - 定义环境变量
    1. 直接定义
       export back_dir = /home/backup
    2. 转换
       export back_dir_ZDY (将自定义变量转换为环境变量[back_dir_ZDY 为自定义变量])
  - 引用变量
    $变量名/${变量名}
    e.g. $back_dir
  - 查看变量
    echo $变量名
    e.g. echo $ip1
    查看全部
    env 
    Env |grep back_dir
  - 作用范围
    在当前shell中生效和子shell均有效

## 常用命令
  1. 显示PATH变量
    echo $PATH
  2. 查看环境变量
    env (查看所有环境变量)
    env |grep SIZE (该命令表示，查看带有SIZE的环境变量。|grep： 信息过滤)

## 小提示Tip
  1. 可以在当前shell中调用其他shell
    `. publish.sh` 例如将该命令写入其他shell，则可以调用publish.sh
		
