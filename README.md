
Docker
=====

> Docker 是一个开源的应用容器引擎，让开发者可以打包他们的应用以及依赖包到一个可移植的容器中，然后发布到任何流行的 [Linux](http://baike.baidu.com/view/1634.htm) 机器上，也可以实现[虚拟化](http://baike.baidu.com/view/729629.htm)。容器是完全使用[沙箱](http://baike.baidu.com/subview/720343/13998082.htm)机制，相互之间不会有任何接口。

# 推荐您安装Docker Toolbox#

> 下载地址：[DOCKER TOOLBOX](https://www.docker.com/products/docker-toolbox)
>
> Docker Toolbox Github下载地址：[Docker toolbox](https://github.com/docker/toolbox/releases/tag/v1.12.3) 
>
> Docker中文：[docker中文](http://www.docker.org.cn/index.html)
>
> 阿里云，开发者平台: https://dev.aliyun.com/search.html
>
> #### Docker Toolbox 是什么?

- Docker 只能运行在Linux内核的系统上。

- Docker Toolbox 则为用户在Windows或者Mac系统上体验 Docker 提供了一个完整的工具包。

- Docker Toolbox 适用于 Mac OS X 10.8+ and Windows 7 & 8.1。

- #### Docker Toolbox 组件包括:####

  - Docker Client
  - Docker Machine
  - Docker Compose (Mac only)
  - Docker Kitematic
  - VirtualBox

- ### 镜像###

  - 推荐国内[阿里云.开发者平台](https://dev.aliyun.com/search.html)  下载镜像文件

  - 搜索镜像地址：http://hub.docker.com/explore

  - `docker searh centos`  搜索跟centos相关镜像

  - `docker images`  查看已安装的镜像文件 

  - `docker pull centos`  下载centos 镜像文件

  - `docker-machine ls`   查看

  - `docker-machine rm default`  删除default

  - ##### 快速开始

    ```
    # 创建一台安装有Docker环境的Linux虚拟机，指定机器名称为default，同时配置Docker加速器地址。
    docker-machine create --engine-registry-mirror=https://wy1740fk.mirror.aliyuncs.com -d virtualbox default

    # 查看机器的环境配置，并配置到本地。然后通过Docker客户端访问Docker服务。
    docker-machine env default
    eval "$(docker-machine env default)"
    docker info
    ```

- ### 容器###

  - `docker run centos /bin/echo 'hello'`  基于centos镜像运行创建一个容器
  - `docker ps`  查看正在运行的容器
  - `docker ps —all`   查看所有的容器
  - `docker run centos ls`   查看centos镜像目录里面的文件夹
  - `docker rm ID`   删除id容器
  - 创建一个容器：`docker run --name greeting centos /bin/echo 'hello'`
  - `docker ps --all --latest`  显示最近创建的容器
  - `docker logs id或者名字`  查看日志
  - `docker stop greeting`  停止容器
  - `docker restart greeting`  重新启动容器
  - `docker start greeting`  运行容器
  - `docker run --interactive --tty centos /bin/bash`  进入容器，添加互动
  - `pwd`   查看当前所在位置
  - `exit`  退出


