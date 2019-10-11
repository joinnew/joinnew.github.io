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


### 创建一个博客

#### 安装hexo-cli
```bash
    npm install -g hexo-cli
```
#### 创建hexo文件夹
```bash
    hexo init
```
#### 安装依赖包
```bash
    npm install
```

### 更换成其他博客主题
我这里的都是以某一个为主题效果的，当然每个人喜欢的可能不一样，所以索性把如何修改主题也放到这里
#### 可选择的博客主题地址 
[博客地址](https://hexo.io/themes/)

#### 更换步骤
1. 选择一个喜欢的主题，如图所示，点击下方的名字，进入github仓库地址
<img src='http://pytyayr4p.bkt.clouddn.com/QQ20191011-132123@2x.png' width=500/>

2. 复制他的下载地址，并且更换配置主题
```bash
    git clone xxx themes/主题名
    在最外围的_config.yml中修改theme的值
```