---
layout: post
comments: true
categories: lucene
---

* content
{:toc}

# mac 中编译opencv,包含SIFT

#### 1. 下载opencv源码

#### 2. 下载opencv_contrib源码,新版的opencv已经将一些工具独立成单独的工程，不再默认包含进去 

    git clone https://github.com/Itseez/opencv_contrib.git

#### 3.  用cmake编译安装

    cd ~/Downloads/opencv-3.1.0/
	cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=~/Downloads/opencv_contrib/modules -D BUILD_TESTS=OFF -D BUILD_PERF_TESTS=OFF -D BUILD_EXAMPLES=OFF . 
    make -j5
    sudo make install

#### 4. 复制cv2.so 到python库目录

    sudo cp /usr/local/lib/python2.7/site-packages/cv2.so /Library/Python/2.7/site-packages


