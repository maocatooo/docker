FROM ubuntu:16.04
MAINTAINER MaoCat "maocatzk@gmail.com"
#源文件有问题?
#ADD sources.list /etc/apt/sources.list
RUN  sed -i s@/archive.ubuntu.com/@/mirrors.tuna.tsinghua.edu.cn/@g /etc/apt/sources.list

RUN mkdir -p /root/.pip
ADD pip.conf /root/.pip/pip.conf
RUN apt-get clean && apt-get update && apt-get install -y \
        build-essential checkinstall libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev \
        libgdbm-dev libc6-dev libbz2-dev zlib1g-dev openssl libffi-dev libjpeg-dev \
        python3-dev python3-setuptools python3-pip wget gcc \
        libpq-dev \
        supervisor \
        openssh-server

RUN mkdir /tmp/Python37; \
    cd /tmp/Python37; \
    wget http://mirrors.sohu.com/python/3.7.4/Python-3.7.4.tar.xz; \
    tar xvf Python-3.7.4.tar.xz; \
    cd /tmp/Python37/Python-3.7.4; \
    ./configure; \
    make install; \
    cd /; \
    rm -rf /tmp/Python37; \
    ln -s /usr/bin/pip3 /usr/bin/pip