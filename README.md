
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
> [阿里云，开发者平台](https://dev.aliyun.com/search.html) 
>
> 保存镜像的库： [Docker Hub](https://hub.docker.com/login) 
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

  >  注释：`CONTAINER ID` 容器的ID， `IMAGE` 容器使用的镜像，`COMMAND` 容器里执行的命名， `CREATED`创建的时间， `STATUS`状态，  `PORTS`端口，  ` NAMES`容器的名字
  >
  > 基于一个镜像可以创建多个容器，

  - `docker run centos /bin/echo 'hello'`  基于centos镜像运行创建一个容器

  - `docker ps`  查看正在运行的容器

  - `docker ps —all`   查看所有的容器

  - `docker run centos ls`   查看centos镜像目录,列表

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

  - `docker run --detach centos ping ninghao.net`  在后台运行的容器

  - `docker logs —follow`  查看容器的日志

  - `dockwe stop 'ID号‘ `  停止容器

    ​

  ## 创建镜像##

- #### 手工创建镜像####

  `docker run -i -t centos bash`  创建带交互的容器

  安装nodejs 

  1. 添加一个nodejs 安装源

  ```node
  curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
  ```

  2. 安装nodejs

  ```node
  yum install nodejs -y
  ```

  3. 完成nodejs，可以使用node

  ```测试,输出hello
  node -e "console.log('hello')"
  ```

  - ##### 提交修改   

    `docker commit -m '安装nodejs' -a 'guoqing' 容器名字或者ID号 guoqing/nodejs-demo:latest`

  - ##### 删除镜像#####

    1. 查看相关容器`docker ps -a -l`
    2. 先删除容器 `docker rm 容器id或者容器名字`
    3. 再删除镜像 `docker rmi guoqing/nodejs-demo`

- #### 创建镜像####

  1. `cd ~/desktop`    进入桌面
  2. `mkdir nodejs-demo`   新建nodejs-demo
  3. `cd nodejs-demo `  进入nodejs-demo文件
  4. `subl ./`   用sublime 打开
  5. 在nodejs-demo文件，新建一个Dockerfile

  ```Dockerfile
  FROM centos  //指定镜像
  MAINTAINER guoqing<gqzydh@qq.com>  //镜像作者
  RUN curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -  //指定源
  RUN yum install nodejs -y   //安装nodejs
  ```

  6. docker build —tag guoqing/nodejs-demo:latest .   //使用Dockerfile制作镜像

     > 创建成功：Successfully built 的提示

  7. 上传镜像到 [Docker Hub](https://hub.docker.com/login)

     1. `docker login`  登录Docker Hub

     > 输入账号，密码，提示：login Succeeded,表示登录成功

     2. `docker push guoqing/nodejs-demo` 上传到Docker Hub

        ​

