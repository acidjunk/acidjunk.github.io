---
title: Install python 2.7.11 on Ubuntu 14.04 LTS
subtitle: Howto to compile your own python
date: 2016-04-20
author: acidjunk
layout: post
permalink: /2016/02/install-latest-python-version-on-ubuntu1404
categories:
  - Computerz
header-img: "img/post-bg-02.jpg"
comments: true
---
On an Ubuntu 14.04 LTS you should not touch the Python version of the system. Why? Of particular importance is the fact that one of Ubuntu policies is to extensively use Python for writing end-user software. So in fact, fairly large part of the system itself is written in Python 2.7. As the stock version of python is a rather ancient 2.7.6 chances are that you run into problems. 

I experienced some weird behaviour with SSL requests (SSL23_GET_SERVER_HELLO:sslv3 alert handshake failure) which forced me to upgrade python. So the best option IMO is to compile Python from source and use those runtimes with VirtualEnv. Don't worry compiling it yourself is simple. You could of cource also use python3.5 if that's an option.

On CentOS 7 or Redhat 7 you'll have almost the same problems. CentOS uses python for their package manager yum; so if you want a newer python version you should compile it yourself.

# Install build dependencies

Install the build depencencies. 

## ubuntu
`sudo apt-get update`
`sudo apt-get install -y autotools-dev blt-dev bzip2 dpkg-dev \
g++-multilib gcc-multilib libbluetooth-dev libbz2-dev libexpat1-dev \
libffi-dev libffi6 libffi6-dbg libgdbm-dev libgpm2 libncursesw5-dev \
libreadline-dev libsqlite3-dev libssl-dev libtinfo-dev mime-support \
net-tools netbase python-crypto python-mox3 python-pil python-ply \
quilt tk-dev zlib1g-dev`

## centos
`yum update`
`yum install zlib-devel bzip2-devel openssl-devel ncurses-devel \
readline-devel pcre-devel curl-devel`

# Get sources and compile it
```
wget https://www.python.org/ftp/python/2.7.11/Python-2.7.11.tgz
tar -xzvf Python-2.7.11.tgz
cd Python-2.7.11/
./configure --prefix /usr/local/lib/python2.7.11 --enable-ipv6
make
sudo make install
```
