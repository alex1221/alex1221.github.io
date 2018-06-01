---
title: 使用 Hexo + Github 搭建属于自己的博客
date: 2018-05-30 14:47:01
tags: [hexo]
categories: Hexo
---

前言：电脑系统为window 7专业版，64位系统

## 前期准备

1、安装了[Git](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)，Git安装好之后，单击右键出现下图：  
![Git安装好之后，单击右键出现此图](https://raw.githubusercontent.com/alex1221/resource/master/images/hexo/git.png)

**点击** `GIT GUI Here`

``` bash
$ git --version
git version 2.8.1.windows.

```

2、安装了[Node](https://nodejs.org/zh-cn/)；

``` bash
$ node -v
v8.9.0

$ npm -v
5.5.1

```

3、[Github](https://github.com/)上新建项目，项目要遵守格式：账户名.github.io

## [Hexo](https://hexo.io/zh-cn/)的安装

1、通过npm命令安装Hexo包

``` bash
$ npm install hexo -g

```

2、检查Hexo是否安装成功

``` bash
$ hexo -v

```

3、创建一个文件夹，在这个文件夹中单击右键，点击 `GIT GUI Here`，用 `hexo init` 初始化改文件夹，最后出现的 `Start blogging with Hexo!`，初始化成功

``` bash
$ hexo init

```

4、然后利用npm命令安装所需要的组件

``` bash
$ npm install

```

5、输入 `hexo g` 命令，生成静态文件

``` bash
$ hexo g

```

6、输入 `hexo s` 命令，启动服务器。默认情况下，访问网址为：[http://localhost:4000/](http://localhost:4000/)，如果端口被占用，可以输入 `hexo server -p 端口号` 来改变端口号

``` bash
$ hexo s

```

## Hexo && Github

1、设置Github的用户名和邮箱

``` bash
$ git config -global user.name "Your name"

$ git config -global user.email "Your email"

```

2、进入.ssh文件夹，文件夹所在目录C:\Users\用户名\.ssh，安装Git后生成

``` bash
$ cd ~/.ssh

```

3、`ssh-keygen` 生成秘钥，注意**C**大写，`Overwrite(y/n)?` 选择 `y`

``` bash
$ ssh-keygen -t rsa -C "你的Github的邮箱"

```

4、执行以下命令将KEY加入到ssh-agent上

``` bash
$ eval "$(ssh-agent -s)"
# Agent pid 59566

$ ssh-add ~/.ssh/id_rsa

```

5、登录Github，点击头像下的 `settings`，点击 `SSH and GPG keys`，点击 `New SSH key`按钮，`Title` 自己起，将id_rsa.pub文件里的内容复制到 `Key`中，再点击 `Add SSH key` 按钮

6、测试添加ssh是否成功，如果看到Hi后面是你的用户名，就说明成功了

``` bash
$ ssh -T git@github.com

```

7、配置 `Deployment`，在其文件夹中，找到_config.yml文件，修改deploy值

``` bash
deploy:
  type: git
  repository: git@github.com:账户名/账户名.github.io.git
  branch: master

```

8、在生成以及部署之前，需要安装以下扩展包

``` bash
$ npm install hexo-deployer-git --save

```

9、生成以及部署，用以下命令

``` bash
$ hexo d -g

```

10、以上成功后，可以去查看你的网站，地址为：https://账户名.github.io/


