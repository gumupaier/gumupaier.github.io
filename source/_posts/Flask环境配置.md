---
title: Flask环境配置
date: 2018-05-28 22:49:03
tags: [Flask,Virtualenv]
categories: "Flask"
---

## Flask安装环境
使用虚拟环境安装flask,可以避免包的混乱和版本的冲突。

虚拟环境使用virtualenv创建，可以查看系统中是否安装了virtualenv：

```
virtualenv --version
```

### 安装虚拟环境
```
$ sudo pip install virtualenv

$ sudo pip install virtualenvwrapper
```
### 创建虚拟环境（需在联网状态下）
```
$ mkvirtualenv flask_py2
```
安装完虚拟环境后，如果提示找不到mkvirtualenv命令，需配置环境变量：
```
# 1.创建目录用来存放虚拟环境
mkdir
$HOME/.virtualenvs
# 2.打开～/.bashrc文件，并添加如下:
export WORKON_HOME=$HOME/.virtualenvs
source /usr/local//bin/virtualenvwrapper.sh
# 3.运行
source ~/.bashrc
```

### 删除虚拟环境

```bash
rmvirtualenv xxx
```

### 进入虚拟环境
$ workon flask_py2
```
### 退出虚拟环境
如果环境为真实环境，会提示deactive：未找到命令
```
$ deactivate flask_py2
```

## 安装Flask
```
指定Flask版本安装
$ pip install flask==0.10.1
输出requirements.txt文件
pip freeze > requirements.txt

```
mac 系统
```
easy_install flask==0.10.1
```
使用requirements文件安装
```
pip install -r requirements.txt
```



## 补充：mac python3 virtualenv环境配置
1、安装python3，推荐官网下载安装文件安装 链接：https://www.python.org/downloads/mac-osx/

2、pip3 install virtualenv virtualenvwrapper

3、create a fold to store all of the virtual environments:
```
cd ~
mkdir ~/.virtualenvs
```
3、修改~/.bash_proflie文件,添加如下:
 ```bash
export WORKON_HOME=~/.envs # point to the .envs fold created above
export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3.6   # make sure this is the python version you want to point to
export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
export VIRTUALENVWRAPPER_VIRTUALENV_ARGS='--no-site-packages'
source /usr/local/bin/virtualenvwrapper.sh
```
>注：确保VIRTUALENVWRAPPER_PYTHON为你的python3可执行文件

4、执行
```bash
source ~/.bash_profile
```
