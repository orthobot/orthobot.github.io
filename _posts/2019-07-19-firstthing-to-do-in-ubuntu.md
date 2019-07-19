---
layout: post
title: "Ubuntu18.04 环境搭建"
date:  2019-07-19-15-00 +0800
categeries: ubuntu  initialization
tags: ubuntu initialization
author:  orthobot
---

#  Ubuntu 18.04 环境搭建
*****
##  GitHub 相关设置
### 安装git
  ```
  sudo apt-get install git
  ```
  设置参数：
    ```
    git config --global user.name 'orthobot'
    git config --global user.email 'alaflam@163.com'
    ```

### 安装ruby、rugygem、jekyll

  ```
  sudo apt install ruby
  sudo apt-get install rubydev
  sudo gem install jekyll
  ```
  **ERROR**
    运行jekyll serve是可能出现“无jekyll-paginate插件”问题，处理
    1. 安装paginate插件
    ```
    gem install jekyll-paginate
    ```
    2. 在jekyll配置文件_config.xml中添加一行
    ```
    sudo gem: [jekyll-paginate]
    ```
### 安装SSH，生成密匙
  ```
  sudo apt-get install ssh
  ssh-keygen -t rsa -C 'alaflam@163.com'
  ```
  直接默认设置，三个回车。
  这样会在 `~/.ssh` 文件夹中，出现两个文件：`id_rsa`和`id_rsa.pub`
  打开`id_rsa.pub`文件，复制其中内容黏贴到GitHub中

### GitHub设置
  打开GitHub官网，登录进入个人页面，点击进入`setting`-->`SSH and GPG keys`，新建SSH密码，将`id_rsa.pub`文件内容黏贴进入公匙框，自己取好名字，保存即可。

### 本地 Git文件夹与远程链接、克隆
  在个人文件夹下建立git文件夹，初始化
  ```
  cd ~
  mkdir git
  cd git
  git init
  ```
  在GitHub中，选定想要连接、克隆的仓库，在`clone or download`中选择`clone with ssh`，复制其中内容，并克隆仓库到本地：
  ```
  cd ~/git
  git clone git@github.com:orthobot/orthobot.github.io.git
  ```
 最后通过jekyll生成本地页面验证查看：
 ```
  jekyll serve
 ```
 -----
## Anaconda、Jupyter notebook 和Python设置
### 下载安装anaconda
  在官网下载相应的anaconda软件，如“Anaconda3-2019.03-Linux-x86_64.sh”到本地后，在.sh文件存储位置安装即可。
  ```
  sh Anaconda3-2019.03-Linux-x86_64.sh
  ```

### python 库的安装
    1. 安装pip
    2. 通过pip安装numpy、scipy、pandas、matplotlib、scikit-learn
```
sudo apt-get install python3-pip
pip3 install numpy scipy pandas matplotlib sklearn
```

-----
##  Atom及插件
  通过ubuntu software 安装atom软件。安装后，在`packages`-->`setting view`-->`open`打开页面，搜索并安装插件：`hydrogen`、`kite`、`minimap`。

-----
## WPS
  在WPS官网下载Linux版WPS，并安装。
  下载字体：mtextra、symbol、WEBDINGS、wingding、WINGDNG2、WINGDNG3
  安装上述字体后wps即可使用。

-----
## sogou输入法
### 安装fcitx
    ```
    sudo apt-get install "fcitx"
    ```
    安装后在 “语言支持” 中选择“键盘输入法系统”中选择“fcitx”。

### 安装搜狗输入法
    在官网下载“搜狗输入法 for Linux”，安装后重启。

-----
## 百度网盘
  在官网下载“百度网盘”并安装。

-----
## VLC
  通过ubuntu software 安装VLC。

-----
## 系统美化
### 安装tweak-tool
  ```
  sudo apt install gnome-tweak-tool
  ```

### 安装gnome-shell
  ```
  sudo apt-get install chrome-gnome-shell
  ```

### 安装浏览器插件
  点击[这里](https://wiki.gnome.org/Projects/GnomeShellIntegrationForChrome/Installation)安装浏览器插件

### 安装extensions
  点击[这里](https://link.jianshu.com/?t=https://extensions.gnome.org/)安装扩展，常用扩展包括`dash to dock` 以及 `User Themes`，安装后打开这两个扩展，前者可以设定dock栏，后者可以让我们安装下载的主题，在`tweak tool`中能看到`shell`的感叹号会消失。

### 安装themes
  点击[这里](https://www.gnome-look.org/)，根据自己喜爱，下载并安装相关主题，之后在`tweak tool`中选择应用
