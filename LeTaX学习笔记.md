# LeTaX学习笔记

## 看看更新没【失败】

## 1. primary

一篇文章的构成，以中文为例

### 1.1 整体框架

#### 1.1.1 声明类

相当于说“我想写一篇文章了”

~~~
\documentclass[UTF8]{ctexart}
~~~

文章编码：UTF8

文章类型：中文

#### 1.1.2 导入包

相当于说："我要开始写文章"

~~~
\usepackage{mathtools,wallpaper}

\usepackage{t1enc}
\usepackage{pagecolor}
~~~

可以一次性导入全部宏，每个包之间用逗号分隔；也可以一行行导入，用到什么导什么。

#### 1.1.3 环境

相当于在说：“我正在写文章”

~~~
\begin{document}
	文章
\end{document}
~~~



### 1.2 开始写文章

#### 1.2.1 maketitle

~~~
	\title{标题\LaTeX}  
	\author{xxx}
	\date{62-50-0202}
	\maketitle
~~~

运行效果

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526214002443.png)

