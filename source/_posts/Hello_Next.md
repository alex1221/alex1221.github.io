---
title: 使用 Hexo 的 Next 主题美化自己的博客
date: 2018-05-30 16:20:15
tags: [hexo]
categories: Hexo
---

1、安装 [Next](http://theme-next.iissnan.com/)

在你的博客的文件夹下，右键点击 `Git Base Here`，输入以下命令

``` bash
$ git clone https://github.com/iissnan/hexo-theme-next themes/next

```

2、启动主题

在你的博客的文件夹下，打开配置文件 `_config.yml`，修改 `theme：next`

3、启动服务

``` bash
$ hexo s

```

4、主题设定

在<span class="label label-info">主题配置文件</span>中将 `scheme: Muse` 注释，将 `scheme: Pisces` 注释放开

5、语言设定

在<span class="label label-primary">站点配置文件</span>中设置 `language: zh-Hans`（简体中文）

6、菜单修改

在<span class="label label-info">主题配置文件</span>中间 `menu: tags: /tags/ || tags` 的注释放开

新建tags的页面，命令如下：

``` bash
$ hexo new page tags

```
在 `source\tags\index.md` 文件中添加 `type: "tags"`,结果如下:

``` bash
 ---
 title: tags
 date: 2018-05-30 17:18:36
 type: "tags"
 ---

```

在<span class="label label-info">主题配置文件</span>中间 `menu: categories: /categories/ || th` 的注释放开

新建categories的页面，命令如下：

``` bash
$ hexo new page categories

```
在 `source\tags\index.md` 文件中添加 `type: "categories"`,结果如下:

``` bash
 ---
 title: categories
 date: 2018-05-30 17:20:36
 type: "categories"
 ---

```

7、修改样式

我们修改样式最好不要修改源文件，在Next中为我们提供了修改样式的地方。
定制样式文件： `next\source\css\_custom\custom.syl`，
定制变量文件： `next\source\css\_variables\custom.syl`，
定制mixin的文件：  `next\source\css\_mixins\custom.syl`


其他的配置可查看 [Next官网](http://theme-next.iissnan.com/)，或者自己测试研究。





