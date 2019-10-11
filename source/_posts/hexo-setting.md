---
title: hexo-setting 其他补充配置
date: 2019-10-11 12:23:38
tags:
- hexo配置
- 前端
categories: 工具使用配置
---
之前写的博客配置忘记上传，导致使用新的电脑需要从头开始，所以就另写一篇博客用于记录，这里的配置记录包括如何上传本地博客的配置文件、使用七牛保存需要使用的图片、还有如何创建一个博客、以及更换成其他博客主题等等

<!-- more --->
### 利用七牛云保存需要的图片

1. 注册一个七牛云账号

2. 选择管理控制台
<br/>
<img src='http://pytyayr4p.bkt.clouddn.com/QQ20191011-123410@2x.png' width=400>

3. 内容管理 - 上传文件 - 选择复制外链 - 在md文件中引入
```html
<img src='http://pytyayr4p.bkt.clouddn.com/QQ20191011-123410@2x.png' width=400>
```

<font color=red>因为hexo中的markdown还不支持对图片裁剪大小，所以通过标签来引入，标准版的markdown支持
```bash
![图片](url = 400x) 宽x高 也可以只设置其中一个属性
```
</font>

### 如何把源代码上传到仓库中
当我们通过hexo g -d部署到仓库上时，并没有把配置文件、md文件之类的上传，而只是生成一些博客需要的静态的页面

1. 可以通过创建新的仓库专门用于保存源码，也可以在当前仓库创建新的分支用于保存
2. 我使用的创建新分支保存
#### 本地创建新分支
```bash
    git checkout -b feature/hexo-source
```
#### 提交代码
```bash
    git add .
    git commit -m '源码提交'
    git push origin feature/hexo-source
```