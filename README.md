# django_test
 docker发布django程序demo

docker : django+uwsgi , nginx 双镜像发布django程序（自用-无注释）

使用说明：
linux系统：centos8
docker版本：20.0
docker-compose：1.29.2

docker安装：
使用国内镜像一键安装：
curl -sSL https://get.daocloud.io/docker | sh

docker-compose安装：
1、pip3 install -U pip setuptools
2、pip3 install docker-compose

当前文件夹复制到系统内：
docker-compose build
docker-compose up

docker ps #查看容器状态