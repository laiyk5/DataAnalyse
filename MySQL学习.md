# 目录

[toc]



# MySQL新手学习环境搭建

1. 搭建学习环境：
   1. 在Oracle官网注册账号并下载安装MySQL8.0 Community。
   2. 将MySQL server下的bin目录添加到系统环境变量的PATH中。
   3. 在Microsoft官网下载安装高颜值Terminal：windows terminal（可选）
   4. 前往MySQL官网tutorial：https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/tutorial.html
2. 要求：基本的命令行使用即可。

# Truble shooting

## 没有mysql命令

将bin文件夹添加到加path。

## 启动服务器

`win+X` ，打开power shell（管理员），输入`net start mysql80`启动服务器。

## 数据导入数据库

### 打开local_infile选项

登录服务器时使用：`mysql --local-infile=1 -u root -p`

登录后：`set global local_infile=1`

### 在命令行当前目录里打开记事本

`notepad pet.txt`	notepad：记事本，pet.txt要打开/创建的文件名。

### 输入后table的格式混乱

#### 检查数据集本身格式

#### 检查是否是以`\t`分隔

水平制表符，即是否使用tab键分隔而不是用空格分隔

解决方法：从Excel复制到记事本里，默认`\t`分隔。

#### 检查是否有NULL值未填充为`\N`

解决方法：在Excel中使用`Ctrl+G`搜索列中空值，填充为`\N`, `Ctrl + Enter`应用到该列所有空值。

#### 检查命令是否缺失

windows 默认的换行符是\r\n，所以在`load data local infile 'pet.txt' into table pet`后还需要加上`lines terminated by '\r\n'`

