---
title: 使用Hexo搭建博客
date: 2017-05-01 18:16:12
tags: Hexo
category: Coding
---
## 使用Hexo搭建博客  
### 一、Github配置
#### 创建仓库   
![创建Github仓库_1](hexo_github_blog/create_repository1.png)  
登录账号后，点击Github右上方的new repository建立仓库。
![创建Github仓库_2](hexo_github_blog/create_repository2.png)  
在`Repository name`输入你的仓库名称，如：`ljyxian.github.io`，然后点击`Create repository`即可。  
#### 添加密钥  
在终端输入`ssh-keygen -t rsa -C "Github的注册邮箱地址"`，然后一直`Enter`，最后会生成两个文件，id_rsa和id_rsa.pub, 复制id_rsa.pub里面的内容，然后进入[ssh设置页面](https://github.com/settings/ssh)粘贴到key内容框里面，title内容框可以随便填写一个即可。

### 二、安装与配置Hexo  
#### 安装node.js  

### 三、使用Hexo写作
### 四、定制主题
