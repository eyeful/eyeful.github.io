---
title: "免费搭建oneindex"
date: 2018-10-26
tags: oneindex
---

## 免费搭建oneindex简单教程

> *其实网上有许多搭建oneindex的教程，不过免费的不多，这次也是几天前看到其他大佬分享免费的搭建教程，所以打算写一下留着以后自己看起来方便。主要是利用now.sh来免费部署。*
>
> 本文核心参考自[**如有乐享**](https://51.ruyo.net)   	
<!--more-->
**本人在x64的win7上亲测没有问题**

### 准备工作

- 注册now账号。[点击进入注册](https://zeit.co)
- 注册oendrive账号。其实大多数都是用5T云盘来搭建，请自行百度注册。也可联系我来注册。

### 安装部署

- 安装nodejs，win上直接下载安装即可。[下载地址](http://nodejs.cn/download/)

- 安装git，[下载地址](https://git-scm.com/downloads)

- 安装now.sh客户端 

  ```
  npm install -g now
  ```

- 安装完毕后登陆now.sh，提示输入邮箱，并通过邮箱点击链接通过验证（必须科学上网才能通过验证，因为需要一个谷歌的验证）

  ```
  now login
  ```

  ![now1.png](https://i.loli.net/2018/10/24/5bd091c61402d.jpg)

- 拉取最新的oneindex代码

  ```
  git clone https://github.com/malaohu/oneindex.git -b now-sh
  cd oneindex
  now
  ```

- 在oneindex目录内执行now命令，开始部署。

  ```
  now
  ```

  一直等着即可，直到下面出来success！成功后即可在now.sh面板里看到部署情况。https://zeit.co/dashboard。你也可以点击访问你的地址。

  ![now2.png](https://i.loli.net/2018/10/24/5bd094249c181.jpg)

- 部署完成后，容器默认会隔一段时间重启，为了不让容器重启，执行下面的命令

  ```
  	now n scale oneindex-vvxbukdkpi.now.sh 1
  ```

- 为了方便访问，可以把前缀设置一个别名。取一个不重复且方便记忆的即可，我用的flyme。完成后即可在面版里看到你刚才的操作。

  ```
  now alias oneindex-vvxbukdkpi.now.sh flyme
  ```

  ![now3.png](https://i.loli.net/2018/10/24/5bd096339c7ec.jpg)

### oneindex平台的部署

> *这个具体步骤网上有许多，也比较简单，我只简单介绍一下步骤*

- 直接访问你部署好的那个网址。https://oneindex-xxxxxxxx.now.sh/，进去后就看到环境检测。点击下一步。
- 点击获取ID和密钥，会自动跳转，登陆你的office账号。
- 一来说第一个显示的密钥，复制到你的oneindex里，点击【知道了，返回到快速启动】
- 接着就会显示应用ID，复制到你的oneindex里。*PS：有的人不会显示密钥而是直接显示了应用ID，解决方法如下*

  - https://apps.dev.microsoft.com/#/appList进入这个网址你会看到你刚才的应用程序。点击进入，重置密码即可，把新密码填入即可。

    ![now4.png](https://i.loli.net/2018/10/25/5bd15328d5ab0.jpg)



    ![now5.png](https://i.loli.net/2018/10/25/5bd1521792ba1.jpg)


- 一直下一步，提示登录office就登陆，提示授权就接受，完成后会提示程序安装成功，成功后可以访问后台，也可以访问网址https://XXXXXXX/?/admin进入后台修改一下后台密码其他的自己设置。这个是我做好的oneindex https://thedrive.ml。

### 给你的now.sh上的oneindex自定义域名

> 我的方法可能只是一种方法，具体可以参考一下官方文档，或者如有乐享里的方法。[帮助文档](https://zeit.co/dns#get-started) 

- 把你的域名指向他的Nameservers 

  | Host         | IP           |       IPV6        |
  | ------------ | ------------ | :---------------: |
  | a.zeit.world | 96.45.80.1   | 2600:180a:1001::1 |
  | b.zeit.world | 46.31.236.1  | 2600:180b:2001::1 |
  | c.zeit.world | 43.247.170.1 | 2600:180c:3001::1 |
  | d.zeit.world | 96.45.81.1   | 2600:180a:4001::1 |
  | e.zeit.world | 46.31.237.1  | 2600:180b:5001::1 |
  | f.zeit.world | 43.247.171.1 | 2600:180c:6001::1 |

- 然后登陆你的now，输入下面命令即可，如有错误请看英文提示。

  ```
  now alias oneindex-XXXX.now.sh XXXX（你的域名）
  ```

  ![now7.png](https://i.loli.net/2018/10/26/5bd1f2ee669fe.jpg)

- 大功告成！！！！