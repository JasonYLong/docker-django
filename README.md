# Docker + nginx + Redis + Django + Mysql 部署 web 应用


### 所需镜像 

* Docker version 1.7.1
* daocloud.io/nginx:1.11
* daocloud.io/python:2.7
* daocloud.io/mysql:5.6
* daocloud.io/django:1.9

此代码详细说明参考：[使用 Docker 部署 Django 应用程序](http://www.jianshu.com/p/4e4c85e1e2b8)

**启动脚本**:

    ./docker-start.sh

**停止脚本**:

    ./stop.sh

此项目照搬： https://www.jianshu.com/p/4e4c85e1e2b8
只是对web中的Dockerfile 进行了修改。

通过访问link http://IP:8888/  测试是否发布成功。

**mysql导入数据**:

   #docker inspect --format "{{.State.Pid}}" mysql
   23962
   #nsenter --target 23962 --mount --uts --ipc --net --pid
   root@efdca36076cb:/etc/mysql/conf.d# cd /etc/mysql/conf.d/
   root@efdca36076cb:/etc/mysql/conf.d# mysql -uroot -p123456 -D blog < blog.sql 
