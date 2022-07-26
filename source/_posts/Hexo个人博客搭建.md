---
title: Hexo个人博客搭建
date: 2022-07-20 11:37:40
tags:
---

#	记录Hexo个人博客搭建

## 搭建具体参考杰哥博客

```
https://yangdijie.github.io/2022/02/02/2022%E5%B9%B42%E6%9C%882%E6%97%A5-hexo%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2/#2-Hexo-%E6%9C%AC%E5%9C%B0%E5%BB%BA%E7%AB%99
```



##	Hexo

Hexo 是一款静态博客生成器。静态的意思是指生成的博客网站访客只能浏览，没法像淘宝那样在我们的网站上提交信息。Hexo 负责把我们写的 Markdown 文件根据选定的主题（规定网站的外观样式的文件）生成一堆 HTML 以及负责外观样式的 CSS 和 Javascript 文件。此外，Hexo 还提供了帮我们把这一堆 HTML、CSS、Javascript 文件上传到 Github 服务器的功能，也就是部署。

## gihub Page

我们平时在新浪上看新闻的时候，所有的东西都要从新浪服务器发送到我们的手机、电脑上。我们的网站也一样，需要一个服务器，把用 Hexo 生成的那些 HTML、CSS、Javascript 文件发送给访客。但我们自己没有服务器呀？Github Pages 是 Github 提供的一项免费的静态页面托管服务，提供 your_name.github.io 的域名（your_name 为你的 Github 用户名）发布自己的静态网站。我们把 Hexo 生成的内容上传到 Github 服务器，访客的浏览器就是从 Github 服务器获取相关文件的。

## 使用Hexo建立站点

### 安装Hexo
切换node源为淘宝镜像

```
npm config set registry "https://registry.npm.taobao.org"
```

使用nodejs来为我们安装

```
npm install -g hexo-cli
```

### 建立站点

1. 先在电脑中的某一位置建立好 `your_name.github.io` 文件夹，比如 `D:\Blog\your_name.github.io`；

2. 在终端中切换到 `your_name.github.io` 文件夹所在的路径。需要注意的是，在 Windows 中，如果要进入某个磁盘，不需要敲 `cd`，直接敲盘符即可。比如我要进入 `D:\Blog\your_name.github.io`，那就输入 `D:` 回车，然后再 `cd Blog\your_name.github.io`；

3. 根据 Hexo 的官方文档 [开始使用 — 建站](https://hexo.io/zh-cn/docs/setup.html)，依次执行下面两条命令，建立我们的新网站：

   ```
   hexo init
   npm install
   ```

   换了淘宝的镜像后，应该能在几分钟内完成。完成后，`your_name.github.io` 文件夹下面的目录如下：

   **其他没有的文件夹由于版本更新，尚未完全去了解，有需求的可自行去hexo官网了解。**

   ```
   .
   ├── _config.yml
   ├── package.json
   ├── scaffolds
   ├── source
   |   └── _posts
   └── themes
   ```

   - `_config.yml` 文件存放着网站的配置信息，可以在这里配置大部分的参数。
   - `package.json` 文件存放着插件信息，从中可以查看那些插件已经安装。
   - `scaffolds` 是模板文件夹，新建文章时，Hexo 会根据 scaffold 来建立文件，不过这个模板和后面的主题里指的模板不一样。
   - `source` 是存放用户资源的地方的文件夹，除 `_posts` 文件夹之外，开头命名为 `_` (下划线) 的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 `public` 文件夹（别急，等下会生成的），而其他文件会被拷贝过去。
   - `themes` 主题文件夹，Hexo 会根据主题来生成静态页面，我们以后自己安装的主题也都会放在这个文件夹下面，默认的 landscape 主题已经在里面了。不同的主题可以根据自己的需要去网上下载，下载完成后放到主题文件夹，下载的主题一般来讲的话都是具有参考文档的会告诉你如何进行主题的切换

4. 根据 Hexo 的官方文档 [开始使用 — 命令](https://hexo.io/zh-cn/docs/commands.html)，在终端中敲入 `hexo server` 命令（确保路径仍在 `your_name.github.io` 下），可以在 http://localhost:4000/ 中看到我们网站默认的样子了。

5. 这个时候我们的本地网站其实已经建好了，但是并没有部署在我们的github page上，要在 Github 上创建项目，当然首先需要[注册 Github帐号](https://github.com/join?source=header-home)。在注册完成后，Github 的官方文档 [Create a new repository on GitHub](https://help.github.com/articles/create-a-repo/#create-a-new-repository-on-github) 已经图文并茂将如何建立一个 repository 交待得非常清楚明白了，唯一要注意的是，第二步里的 Repository name 一定要是 `your_name.github.io` ，`your_name` 是你的 Github 用户名。

6. 因为`your_name.github.io`托管的是静态页面，所以我们首先必须将我们利用hexo建立好的网站生成静态文件，在我们建立的站点目录下直接cmd使用hexo generate 命令生成静态文件，执行完后我们的目录会多出一个public 文件夹里面就是生成的静态文件，也就是我们需要部署（上传）到github上的内容，

   1. hexo generate 到底做了啥我也很好奇，目前给我的感觉就是将我们站点下source文件夹里面的内容进行了解析在public 下生成了静态文件
   2. Hexo 引入了差分机制，如果 `public` 目录存在，那么 `hexo g` 只会重新生成改动的文件。

## 部署站点

​	部署站点有两种方式 一种是使用hexo 部署，另一种就是不使用hexo 进行部署

### 使用Hexo进行部署

Hexo 提供了 `hexo deploy` 命令，可以方便地将整个 `public` 文件夹部署到 Github 服务器上去。根据 Hexo 的官方文档 [基本操作 — 部署](https://hexo.io/zh-cn/docs/deployment.html) 我们只需要做以下两步：

- 在终端中运行如下命令，安装 `hexo-deployer-git` 插件：

  ```
  npm install hexo-deployer-git --save
  ```

- 在 `_config.yml` 中修改参数，如下所示：

  ```
  deploy:
    type: git
    repo: https://github.com/your_name/your_name.github.io.git
    branch: master
  ```

  注意yml 文件冒号后的空格很重要

- 配置完成后直接使用`hexo deploy`命令将文件上传至Github仓库，在此之前确保静态文件已经生成，如果不想每次有了新内容后都进行一下`hexo g`,可以直接使用此命令参数`hexo deploy -g`部署之前预先生成静态文件

### 不使用Hexo部署

如果不使用一键部署的话那就需要手动建public下生成的静态文件上传至github仓库

- 进入public文件夹，直接右键git bash here打开git，输入git init，将此文件夹作为仓库。
- 首先可以查看一下远程仓库的信息，如果没有的话 `git remote add origin 你的仓库地址`重新添加远程仓库
- 然后使用`git add .`将当前文件夹所有内容添加至暂存区，然后通过`git commit -m 'xxx'`写个注释,最后通过`git push -u origin master`上传至远程仓库。 
- 在我们使用hexo new xxxx 生成了新博客内容后，我们需要`hexo g`重新生成静态文件，然后再重复上面操作，将新增内容上传至github仓库

## 有新内容再补充

