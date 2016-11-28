
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

## Requirements

* cordova `^5.0.0`
* framework7 `^1.4.0`

## Dependencies

HiApp use `npm` to manage third-party packages now.

Then install all dependencies, in repo's root:

```
$ npm install 
```

## PhoneGap App Guides

Install the cordova module using npm utility of Node.js.

```
$ npm install -g cordova
```

### Create App

Go to the directory where you maintain your source code, and run a command such as the following:

```
$ cordova create hiapp com.hiapp.hiapp HiApp
```

### Check out source code

Because the PhoneGap app directory should not already exist, so check out the HiApp source code in this step.

```
$ cd hiapp  
$ git init   
$ git remote add origin git@github.com:BelinChung/HiApp.git  
$ git pull origin master  
$ git reset --hard origin/master  
```

### Add Platforms

Before you can build the project, you need to specify a set of target platforms.

```
$ cordova platform add ios
```

### Add Plugins

You need to add plugins that provide access to core Cordova APIs.

```
$ cordova plugin add cordova-plugin-whitelist cordova-plugin-camera cordova-plugin-geolocation cordova-plugin-file-transfer cordova-plugin-inappbrowser cordova-plugin-network-information
```

### Build the App

Run the following command to iteratively build the project:

```
$ cordova build ios
```

### Test the App on an iOS Device with Xcode

Double-click to open the `platforms/ios/HiApp.xcodeproj` file

Press the `Run` button to deploy the application in the emulator

## Web App Preview

HiApp use webpack browser sync server to develop, Just run it in repo's root:

```
$ npm run dev
```

WebApp will be available on `http://localhost:3000/`

## Web App Release / PhoneGap App Release

```
$ npm run build
```

The result is available in `www/` folder.

## Demo

[http://hi.dearb.me/]

[![App Store](http://dearb.u.qiniudn.com/appstore-button.png)](https://itunes.apple.com/us/app/hi-liao-gao-xiao-shu-dong/id917320045?mt=8)

## License

Copyright (c) 2014-2016 Belin Chung. MIT Licensed, see [LICENSE] for details.

[http://hi.dearb.me/]: http://hi.dearb.me/
[LICENSE]:https://github.com/BelinChung/HiApp/blob/master/LICENSE.md