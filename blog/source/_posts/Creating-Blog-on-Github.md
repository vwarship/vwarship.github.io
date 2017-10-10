---
title: Creating Blog on Github
date: 2017-10-10 10:10:42
tags: [Hexo,Github]
categories: 开发
---
使用Hexo在Github上创建自己的Blog。

```swift
let s = "Hello World!"
print(s)
```

## 搭建步骤

### 安装Hexo

``` bash
$ brew install ruby
$ brew install node
$ npm install hexo-cli -g
```

### 在Github上创建Blog仓库

创建仓库：<username>.github.io，username换成你的Github用户名，克隆到本地。

``` bash
$ git clone https://github.com/<username>/<site>.git
$ cd site
```

### 创建Blog

``` bash
$ hexo init blog
$ cd blog
$ npm install
```

### 本地预览
``` bash
$ hexo server
```

### 配置Github

打开blog目录下的_config.yml，定位到文件尾部，按下面的进行修改，repository对应的是我自己的仓库地址。

``` yml
deploy:
  type: git
  repository: https://github.com/<username>/<site>.git
  branch: master
```

生成静态页面并部署到Github上。

``` bash
$ hexo generate
$ hexo deploy
```

## 其它

### 绑定域名

对域名进行解析设置，这里以阿里云为例。到你要绑定的域名进行解析设置。分别增加了2条解析记录并启用：

记录类型|主机记录|记录值
-|-|-
A | @ | 151.101.73.147
CNAME | www | vwarship.github.io

* 151.101.73.147 这个IP是我 ping vwarship.github.io 得到的，你可以ping自己的。
* vwarship.github.io 这个你要填写自己的Blog仓库名。

到Github上对Blog仓库设置域名。Settings -> Custom domain -> www.gouchicao.com
* www.gouchicao.com 使用自己注册的域名

### 在Blog中插入图片

打开blog目录下的_config.yml，修改post_asset_folder为true。

``` yml
post_asset_folder: true
```

安装图片的插件

``` bash
$ npm install hexo-asset-image --save
```

创建文章xxx。在source/_posts/目录下会多一个xxx的目录，xxx文章的图片放在这个目录下就可以了。

``` bash
$ hexo new "xxx"
```

使用图片。

``` md
![图片](xxx\image.png)
```

### 更改主题(theme)

克隆主题到themes目录下

``` bash
$ git clone https://github.com/hexojs/hexo-theme-light themes/light
```

打开blog目录下的_config.yml，修改theme为light

``` yml
theme: light
```

### 切换主题为中文

打开blog目录下的_config.yml，修改language为zh-CN
``` yml
language: zh-CN
```

### 创建关于页面

``` bash
$ hexo new page about
```

### 修改landscape主题的样式

打开landscape/souce/css/_variables.styl

```css
banner-height = 120px
```

打开landscape/souce/css/_partial/header.styl

```css
#banner
  background: center #000
$nav-link
  opacity: 0.9
  font-size: 20px
```

[hexo-prism-plugin](https://github.com/ele828/hexo-prism-plugin)
