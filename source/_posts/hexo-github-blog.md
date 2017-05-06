---
title: 使用Hexo搭建博客
date: 2017-05-01 18:16:12
tags: Hexo
category: Coding
---
# 使用Hexo搭建博客  
## 一、Github配置
### 创建仓库   
![创建Github仓库_1](hexo_github_blog/create_repository1.png)  
登录账号后，点击Github右上方的new repository建立仓库。
![创建Github仓库_2](hexo_github_blog/create_repository2.png)  
在`Repository name`输入你的仓库名称，如：`ljyxian.github.io`，然后点击`Create repository`.  
### 添加密钥  
在终端输入`ssh-keygen -t rsa -C "Github的注册邮箱地址"`，然后一直`Enter`，最后会生成两个文件，id_rsa和id_rsa.pub, 复制id_rsa.pub里面的内容，然后进入[ssh设置页面](https://github.com/settings/ssh)粘贴到key内容框里面，title内容框可以随便填写一个即可。

## 二、安装与配置Hexo  
### 安装node.js  
进入官网[node.js官网](https://nodejs.org/en/)下载最新版本即可。
### 安装Hexo
在终端执行命令`npm install hexo-cli -g`,下载可能相当久，此时可以使用淘宝源来下载：先下载cnpm `npm install -g cnpm --registry=http://registry.npm.taobao.org`接着用cnpm 命令代替cpm。 有时间的同学可以查看[Hexo的官方文档](https://hexo.io/docs/)
安装成功后,在终端输入`$hexo`,若出现下图则说明安装成功。
![安装Hexo](hexo_github_blog/install_hexo.png)  
### 使用Hexo搭建博客
**初始化Hexo**
`$cd 指定目录`  
`$hexo init`  

**配置_config.xml文件**  
需要配置的主要内容包括:
```java
title: 李嘉裕的博客
subtitle:
description: 一个耕耘一分收获
author: 作者  
language: zh-CN  
timezone: Asia/Shanghai  ```  

```java  
deploy:
  type: git
  repo: https://github.com/ljyxian/ljyxian.github.io.git(上面申请的github仓库地址)
  branch: master
```
注意，每一项的填写，在`:`后面都需要留一个空格。

**新建markdown文档**
在终端输入 `$hexo new "文章标题"`
在`./source/_post/`即生成对应的markdown文档。

**本地发布**
在终端输入 `$hexo server`
出现下图:  
![本地运行](hexo_github_blog/hexo_server_local.png)  
在浏览器中输入  
```
http://localhost:4000/
```
即可看到我们搭好的博客和新发布的文章。

**发布到github**  
在终端输入 `$hexo generate` `$hexo deploy`  
然后在浏览器中输入仓库名字如：`ljyxian.github.io` 即可查看我们布置好的博客内容。

**多机更新Hexo博客**
基于上面操作，每次我们使用`$hexo generate` `$hexo deploy`命令更新博客时，github仓库所更新的内容是经过Hexo处理后所生成的文件，并不是我们在本地的源文件。一旦换机器，则无法原来的基础上更新博客。因此我们在github仓库中新建多一个分支来保存我们的源文件，具体操作如下：
1.新建源文件分支  
![github新建分支](hexo_github_blog/github_create_branch.png)  
2.把源文件分支设置为默认分支  
![github设置默认分支](hexo_github_blog/github_set_default_branch.png)  
由于把源文件分支设置为默认分支，因此每次换机器时，都可以通过`git clone github库地址`来拉去源文件。

## 四、定制主题  
主题的资源文件都在`./themes`目录下，我们把需要配置的主题文件放到此目录下。然后更改_config.xml文件中的`theme:`所指向的主题。
