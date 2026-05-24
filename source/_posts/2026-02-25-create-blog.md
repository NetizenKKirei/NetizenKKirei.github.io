---
title: Hexo➕github pages 的个人博客建站教程
date: 2026-02-25 11:52:02
categories: 技术分享
tags:
  - Hexo
  - GitHub Pages
description: 使用 Hexo、GitHub Pages 和 Butterfly 搭建个人博客的入门记录。
cover: https://img.heliar.top/file/1771991858690_36b90cc6f7ca133e0995d531e7046ad4.jpg
top_img: https://img.heliar.top/file/1771991871311_c38f393f68bd30c7982a10afbd7d2134.jpg
---

## 软件与本地环境

### [Scoop - 命令行式的 Windows 软件安装工具](https://gitee.com/scoop-installer-mirrors)
Scoop 是 Windows 平台的命令行包管理器，能通过简单的命令快速实现软件的安装、更新、卸载和环境变量的配置，这里我使用的是gitee上的国内纯净镜像源。
给出的链接有详细的步骤指引，对于本教程而言，只需执行到下方命令即可。
```bash
scoop config use_sqlite_cache
```

### Node.js
在已经安装并配置好scoop的前提下，在命令行执行
```bash
scoop search nodejs
```

一般会返回多个版本的软件，复制其中带有 lts（即长线支持版）的版本名称，并执行
```bash
scoop install nodejs
```
此时软件将被下载到scoop安装目录的子目录下。

### 其他
除上述软件外，还需要使用到 [VsCode](https://code.visualstudio.com/) 和 [git](https://git-scm.com/) ，可参考网络其他教程进行基础配置。

## 搭建本地网站

### 安装[hexo](https://hexo.io/zh-cn/)
1. 桌面右键，点击 Open Git Bash here
![alt text](/post-img/-post1.png)
2. 在打开的命令行界面输入
```bash
npm install -g hexo-cli
```

### 建站
1. 选择一个自己记得住的路径，新建文件夹，这就是个人博客的本地目录
2. 选择文件夹，右键打开，点击 Open Git Bash here
3. 在命令行界面输入以下命令，安装hexo框架
```bash
hexo init
```
至此，网站框架已经搭建完成，可以直接用vscode打开文件夹进行后续操作。
下面是几个hexo的常用命令
| 命令 | 作用 |
| :----- | :--- |
| `hexo clean`  | 清空缓存和旧静态文件  |
| `hexo g` | 生成新的静态文件 |
| `hexo s` | 生成本地预览 |
| `hexo d` | 推送文件到 GitHub Pages |

### 主题
- 在hexo官网的[主题](https://hexo.io/themes/)页面，有丰富的网站主题可供选择，我自己使用且推荐的是[butterfly](https://butterfly.js.org/)，对于主题的配置有详尽的双语文档和个性化内容。
- 值得一提的是，站点的[文档（二）](https://butterfly.js.org/posts/dc584b87/)讲的都是网站页面内的配置，我更建议只跟着创建完标签页、分类页和友链后直接到[文档（三）](https://butterfly.js.org/posts/4aa8abbe/)进行网站的整体布局配置，可以搭配[这篇教程](https://www.fomal.cc/posts/3451f874.html)食用。
- 本站[友情链接](/link/index.html)的**实用工具**一栏提供了一些在配置时可能用到的小玩意。

## 通过Github Pages上线个人博客
1. 在浏览器登录自己的github账号，点击右上角+号，选择新建仓库
![alt text](/post-img/-post2.png)
2. 将仓库命名为`你的GitHub用户名.github.io`，可见性为`public`，创建仓库
3. 由于github新仓库的默认分支命名为main ，而Hexo默认创建的是master分支，需在本地执行以下命令重命名
```bash
git branch -M main
```
1. 打开本地Hexo博客的根目录，找到 _config.yml 配置文件，找到`deploy`部分，修改为以下内容：
```bash
deploy:
  type: git
  repo: https://github.com/你的GitHub用户名/你的GitHub用户名.github.io.git
  # 若此前已经和github建立ssh链接，则替换为git@github.com:你的GitHub用户名/你的GitHub用户名.github.io.git
  branch: main
```
2. 依此执行以下命令
```bash
hexo clean
hexo g # 可选，在本地生成静态网页预览
hexo d
```
3. 待推送完毕后等待1-2分钟，即可通过`你的GitHub用户名.github.io`访问你搭建好的个人博客。
