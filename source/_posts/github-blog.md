title: 利用hexo在github上搭建blog
date: 2014-06-04 00:15:39
tags: hexo-theme
---

hexo是一个基于nodejs的生成静态文件的博客，用markdown写作，并且可以在本地很方便的预览和同步到git等。所以必须要先安装node，npm，git，安装这些的教程就不在这说了。具体可参考文档：http://hexo.io/docs/

基本命令：

    $ hexo new          #新建文章
    $ hexo generate     #生成
    $ hexo server       #测试
    $ hexo deploy       #提交

也可以简写成：

    $ hexo n    #新建文章
    $ hexo g    #生成
    $ hexo s    #测试
    $ hexo d    #提交

<!-- more -->

## 安装hexo
因为众所周知的GFW，建议修改npm镜像，再安装

    npm install hexo -g

## 创建hexo文件夹
    
    $ hexo init “hexo_demo”
    $ cd hexo_demo
    $ npm install  #安装必要模块
    $ hexo g
    $ hexo s

完成上面的就可以在浏览器预览，默认是：http://localhost:4000/

## 同步到github

先在github新建一个项目，以我为例，我新建的项目名就是：shamcle.github.io，只需要把用户名改成自己的就行

修改hexo_demo文件夹里面的_config.yml
    
    deploy:
      type: github
      repository: https://github.com/shamcle/shamcle.github.io.git  #修改成你自己的仓库地址
      branch: master

执行

    $ hexo d

里面会涉及到github的代码提交概念，请自行查阅资料。

也可以用

    $ hexo g -d

生成+提交代码到github

以下是针对模版的一些自定义修改，模版是放在theme文件夹下的，github上也有很多别人做的模版

万恶的墙，把jquery改为sae

    <script src="http://lib.sinaapp.com/js/jquery/2.0.3/jquery-2.0.3.min.js"></script>



在默认模版的基础上新增了多说评论，只想让详情页有评论,新增如下代码解决：

    <% if (!index && post.layout=='post'){ %>

参考：
http://hexo.io/docs/themes.html
https://github.com/A-limon/pacman