---
layout: post
comments: true
categories: webrtc
---

* content
{:toc}

##### 1.  安装libevent
```
$ wget https://github.com/downloads/libevent/libevent/libevent-2.0.21-stable.tar.gz
$ tar xvfz libevent-2.0.21-stable.tar.gz
$ cd libevent-2.0.21-stable
$ ./configure
$ make
$ make install
```
##### 2. 安装turnserver
```
$ wget http://turnserver.open-sys.org/downloads/v4.5.0.6/turnserver-4.5.0.6.tar.gz
$ tar turnserver-4.5.0.6.tar.gz
$ cd turnserver-4.5.0.6
$ ./configure
$ make
$ make install
```