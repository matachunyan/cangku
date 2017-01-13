---
title: hexo博客
date: 2016-10-05 02:55:53
tags:
---
# 如何拥有一个属于自己hexo博客

------
千里之行始于足下 动手去做才是开始
## **1.准备工作**
> * 安装Node.js
> * 安装Git
> * 注册Github

## **2.SSH keys**


SSH keys可以git项目与远程的github建立联系
右键打开Git Bash Here,查看现有ssh keys，输入：
```1
$ cd ~/. ssh
```
生成新的SSH Keys
（此处的邮箱地址请输入你注册的git邮箱）
```1
$ ssh-keygen -t rsa -C "邮件地址@xxxxx.com
```
然后回车

然后系统会要你输入密码。这个密码会在你提交项目时使用，如果为空的话提交项目时则不用输入。
（输入密码的时候没有*字样的，你直接输入就可以了）
```1
Enter passphrase (empty for no passphrase):<输入加密串>
Enter same passphrase again:<再次输入加密串>
```
获取秘钥
```1
$ cat ~/.ssh/id_rsa.pub
```
然后拷贝key

在Github上添加SSH密钥
![此处输入图片的描述][1]


然后title随便取个名字，key 就是上面我们拷贝的内容
输入以下命令：
```1
$ ssh git@github.com
```
会看到
```1
Hi matachunyan! You've successfully authenticated, but GitHub does not provide shell access.Connection to github.com closed.
```
设置用户信息
```1
$ git config --global user.name "你git的名字"
$ git config --global user.email  "注册邮箱地址@xxxx.com"
```
## **3.HEXO的搭建**
Github上建立库
登陆Github，建立一个名为seminelee.github.io的仓库。
注意！Github Pages的Repository名字是特定的，比如我Github账号是matachunyan，那么我Github Pages Repository名字就是matachunyan.github.io

安装HEXO
打开Git Bash Here
```1
$ npm install -g hexo
 
```
接下来，我们选择一个硬盘目录作为存放文件的路径，例如我手动在e 盘目录下建了一个BLOG的文件夹

然后进入该目录：
```1
$ cd e:\BLOG
 
```
在BLOG目录下：
```1
$ hexo init e:\BLOG
 
```
Hexo随后会自动在目标文件夹建立网站所需要的所有文件。

在BLOG目录下，然后生成部署文件，启动本地服务：
```1
$ hexo s # 或者hexo server，可以在http://localhost:4000/ 查看
$ hexo g # 或者hexo generate
 
```
在浏览器中输入localhost:4000看看，可以看到默认主题下的博客，这就实现了本地预览了。
Hexo 几个常用的命令：
```1
hexo generate (hexo g) 生成静态文件，会在当前目录下生成一个新的叫做public的文件夹
hexo server (hexo s) 启动本地web服务，用于博客的预览
hexo deploy (hexo d) 部署博客到远端服务器
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
 
```
上传至Git库中
打开BLOG目录下的_config.yml,更改增加配置：
注意冒号后要添加一个空格
```1
# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: https://github.com/matachunyan/matachunyan.github.io.git
  branch: master
 
```
然后输入
```1
$ hexo g #generate生成
$ hexo d #deploy开发环境
 
```
如执行 hexo deploy 后,出现 error deployer not found:github 的错误 输入
```1
$ npm install hexo-deployer-git --save
 
```
再次执行hexo deploy，打开https://matachunyan.github.io/就能看到你自己的博客了！

 

 

