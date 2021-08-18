# 嵌入式读书分享

## 环境配置
主要是npm和hexo，npm的环境与平台有关，请下载对应平台的版本
```Shell
sudo apt install npm
npm i hexo-cli
git clone https://github.com/NKU-EmbeddedSystem/SharingBlog.git
cd SharingBlog
```

## 新建博客
博客会出现在source/_posts/目录底下
```
hexo new post "博客名"
```

### 如果不想写markdown，想直接上传PPT的话，就按照以下步骤
1. 将PPT导出为PDF
2. 把PDF放进source/_posts/ppts文件夹中
3. 在source/_posts/往期PPT.md中增加一行
```Markdown
[标题](/share/ppts/文件名.pdf)
```
4. 跳到步骤[更改并提交到网页](#更改并提交到网站)

感觉可能有显示资源文件夹/share/ppts的方法，不过我不会-_-

## 编辑博客
内容以Markdown格式编写即可。需要改一下文件头，title和author改成自己的名字，categories写读书或者是论文分享, tags加自己想要的，以-间隔。别的会由hexo自动生成。
```Markdown
---
title: 内存管理
author: 蒋璋
top: false
cover: false
toc: false
mathjax: true
tags:
  - 内存管理
date: 2021-08-11 09:27:51
img:
coverImg:
password:
summary:
categories: 读书
---
```

## 更改并提交到网站
```Shell
# 以下步骤是为了把自己的博客放进主分支，如果不上传别人再生成一次你的博客就消失了
git add -A
git commit -m "new blogs"
git pull origin master
git push origin master

# 发行到git pages
hexo g #生成html文件
hexo d #上传到gitpages的仓库
```
效果显示在https://nku-embeddedsystem.github.io/share

## 本地调试
由于提交到git pages上会有延时，我们可以在localhost:4000中看到生成后的效果
```Shell
hexo g
hexo s
```

## 想要换骚气的签名以及照片可以更改_config.yml
