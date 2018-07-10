
# 基础镜像
FROM python:2.7.13

# 维护者信息
MAINTAINER tianfeiyu <www.tianfeiyu.com>

ADD blog.tar.gz /usr/src/ 

# app 所在目录
WORKDIR /usr/src/myblog

# 安装 app 所需依赖
#RUN apt-get -y install build-essential python-dev zlib1g-dev libssl-dev && pip install --no-cache-dir -r requirements.txt
#RUN apk add --no-cache --virtual .build-deps gcc libc-dev linux-headers mariadb-dev python3-dev && pip install --no-cache-dir -r requirements.txt

RUN apt-get update \
#  && apt-get install -y mysql-server --no-install-recommends \
  && apt-get clean \
  && pip install --no-cache-dir -r requirements.txt \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

