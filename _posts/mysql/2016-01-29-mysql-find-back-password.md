---
layout: post
comments: true
categories: mysql
---

* content
{:toc}

## mysql找回帐号密码

### 1 停止运行的mysql:

    /etc/init.d/mysql stop


### 2 使用 skip-grant-tables 这个选项启动mysql

    /usr/bin/mysqld_safe --skip-grant-tables &
	
### 3 现在可以不用密码进入mysql了

    mysql
	> use mysql;
	> UPDATE user SET password=password('123456') WHERE user='root'; //密码修改为123456
    > FLUSH PRIVILEGES;
	> quit; //退出mysql
	
	
### 4 重启mysql:
    
	/etc/init.d/mysql restart




