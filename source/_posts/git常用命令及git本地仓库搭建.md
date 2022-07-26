---
title: git常用命令及git本地仓库搭建
date: 2022-07-20 11:12:27
tags:
---

## git常用命令及git本地仓库搭建

+ 本地仓库搭建

  1. 首先需要在自己的电脑安装git

  2. 配置本地用户名

     在git bash终端中输入

     ```
     git config --global user.name "YOUR NAME"
     git config --global user.email "YOUR EMAIL ADDRESS"
     ```

     其中，`YOUR NAME` 是自己取的名字，`YOUR EMAIL ADDRESS` 是自己的邮箱。由于自己的博客网站就自己一个人提交，所以就都设置成跟 Github 用户名和邮箱相同了。但其实是可以不同的，因为对于很多项目，并不只有一个开发者，Github 允许多人向同一个 Repo 提交，这里提供用户名和邮箱，只是为了搞清楚哪些代码是谁提交的。

  3. 一般本地仓库有两种产生途径

     1. 在某个文件夹下面通过git init 命令初始化作为本地仓库

        然后在通过git remote add origin  仓库地址 建立与远程仓库的连接

     2. 在某个文件夹下通过git clone 仓库地址  将远程仓库克隆下来作为自己的本地仓库

        如果直接clone的是仓库地址，会将整个仓库都克隆下来，其中仓库名称作为文件名

+ git常用命令

  + git init ：将当前目录初始化git仓库 作为本地仓库
  + git add  .  : 将当前目录下所有的的文件或者文件夹提交到暂存区
  + git commit -m "第一次提交"： 给暂存去待提交文件添加本次提交注释
  + git push -u origin master ：  向远程仓库田松文件
    1. 需要注意的是一般都是在本地代码中第一次推送的时候 需要我们手动给他加上参数-u
    2. 后面再推送至远程仓库的时候就可以不需要用到我们的-u参数了
  + git remote add origin  仓库地址：重新添加远程仓库地址建立链接
  + git pull --rebase origin master 获取远程库与本地同步合并(如果远程库不为空必须做这一步，否则后面的提交会失败)
  + git remote remove origin：删除远程仓库配置
  + git rm --cached "文件的位置或者路径" ：删除暂存区内容