---
title: How to use jupyter notebook
date: 2018-03-14 15:48:47
tags:
---

### 1.Jupyter NoteBook 安装
目前，最新版本的Anaconda是自带Jupyter NoteBook的，不需要再单独安装

### 2.更改Jupyter Notebook 的工作空间

#### 2.1 直接更改配置文件
```
#in cmd
jupyter notebook --generate-config

#set c.NotebookApp.notebook_dir
c.NotebookApp.notebook_dir = 'F:\kaggle'
```
设置了这个之后无论在哪个cmd窗口输入 *jupyter notebook* 都会直接将home目录设置为
上面的dir

#### 2.2 在文件目录下打开
进入想要的home目录

输入cmd，在cmd窗口输入jupyter notebook

![](http://chuantu.biz/t6/241/1519960915x-1404814622.png)

### 3.Jupyter 快捷键
- 执行当前cell，并自动跳到下一个cell：Shift Enter

- 执行当前cell，执行后不自动调转到下一个cell：Ctrl-Enter

- 是当前的cell进入编辑模式：Enter

- 退出当前cell的编辑模式：Esc

- 删除当前的cell：双D

- 为当前的cell加入line number：单L

- 将当前的cell转化为具有一级标题的maskdown：单1

- 将当前的cell转化为具有二级标题的maskdown：单2

- 将当前的cell转化为具有三级标题的maskdown：单3

- 为一行或者多行添加/取消注释：Crtl /

- 撤销对某个cell的删除：z

- 浏览器的各个Tab之间切换：Crtl PgUp和Crtl PgDn

- 快速跳转到首个cell：Crtl Home

- 快速跳转到最后一个有内容的cell：Crtl End

### 4.其他

#### 4.1导入本地python文件
在需要导入该段代码的cell中输入
```
%load test.py #test.py是当前路径下的一个python文件
```

#### 4.2 运行python文件
利用jupyter的cell是可以运行python文件的，即在cell中运行如下代码：
```
%run file.py
```

#### 4.3 使用Matplotlib绘图
在Jupyter Notebook中，如果使用Matplotlib绘图，有时是弹不出图像框的，此时，可以在开头加入
```
%matplotlib inline
```
