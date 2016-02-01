---
layout: post
comments: true
categories: lucene
---

* content
{:toc}

# mac 中编译opencv,包含SIFT

## 下载opencv源码,建议下载 3.0版本，3.1最新版在python调用时存有一个bug

## 下载opencv_contrib源码,新版的opencv已经将一些工具独立成单独的工程，不再默认包含进去 

    git clone https://github.com/Itseez/opencv_contrib.git

## 用cmake编译安装

    cd ~/Downloads/opencv-3.0.0/
	cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=~/Downloads/opencv_contrib/modules -D BUILD_TEST=OFF -D BUILD_PERF=OFF -D BUILD_EXAMPLES=OFF . 
    make -j5
    sudo make install




