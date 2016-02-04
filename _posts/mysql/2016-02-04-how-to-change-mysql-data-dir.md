---
layout: post
comments: true
categories: mysql
title: ubuntu下更改mysql数据目录
---

* content
{:toc}

#### 1. 创建新的数据目录

    mkdir -p /data/mysql

#### 2. 复制原有数据

    cp -R /var/lib/mysql/* /data/mysql

#### 3. 修改权限

    chown -R mysql:mysql /data/mysql

#### 4. 修改配置文件

    vi /etc/mysql/my/cnf
    datadir = /data/mysql

#### 5. 修改启动文件

    vi /etc/apparmor.d/usr/sbin/mysqld
    #把
    /var/lib/mysql r,
    /var/lib/mysql/** rwk,
	改成
    /data/mysql r,
	/data/mysql/** rwk,
	
#### 5. 重启服务
	
    /etc/init.d/apparmor restart
    /etc/init.d/mysql restart 



