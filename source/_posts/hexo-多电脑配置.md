---
title: hexo 多电脑配置
date: 2018-05-28 23:42:48
tags: hexo
categories: hexo
---

更换了mac电脑后，hexo配置也得重新来捣鼓一遍，参考知乎大神的文章，也算是完美迁移，目前windows和mac本都能进行hexo一系列操作
原贴作者：TonyStank
链接：https://www.zhihu.com/question/21193762/answer/299183554

主要的就是在git建立个分支，把你本地的hexo环境用git管理起来

操作如下：
假如你的本地hexo目录是 blog_hexo，那么
```
cd blog_hexo
git init
git add .
git commit -s
git branch hexo_new
git checkout hexo_new
git remote add origin https://github.com/yourname/yourname.github.io.git
git push -u origin hexo_new

```

就可以了
在另外的机器上：
```
git clone -b hexo_new https://github.com/yourname/yourname.github.io.git
cd yourname.github.io.git
hexo clean
hexo g
hexo s

```
如果执行后无法启动本地服务，在当前目录中，执行以下语句
例如: 访问 http://localhost:4000/,返回 Cannot GET /
```
npm install
npm install hexo --save
npm install hexo-server --save
```
在操作过程中，出现了这种错误
```
WARN No layout: index.html
```
如果你也出现这种情况
* 注意站点配置文件主题是否配置正确
* 注意所选主题文件夹是否为空，如果为空，将旧电脑内的主题文件将空文件夹替换即可