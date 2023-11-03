# LeTaX学习笔记

## 看看更新没【失败】

**这是一个简短的总结：**

~~~
#文章编码及类型
\documentclass[UTF8]{ctexart}
\usepackage{mathtools,wallpaper}
#导包
\usepackage{t1enc}
\usepackage{pagecolor}
\begin{document}
#标题
	\title{标题\LaTeX}  
	\author{xxx}
	\date{62-50-0202}
	\maketitle
#章节
\section{\LaTeX 的使用}
\subsection{\LaTeX 的基本知识}
\subsubsection{\LaTeX 的结构}
#列表
	\begin{enumerate}
	\item 第一条
	\item 第二条
	\item 第三条
	\end{enumerate}
#换行
	第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行第一行
	
	第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行第二行
#转义
\{显示大括号\}
#换行公式
\begin{align}
girlfriends=money*face \notag \\ %%如果想要这一行没标号的话，notag要加在\\之前
boyfriends=face^n 
\end{align}
#对齐
\begin{align}
&girlfriends=money*face \notag \\ 
&boyfriends=face^n 
\end{align}
#行内公式
$girlfriends=money*face$

\end{document}

~~~





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

注意：`\maketitle`一定要加上，不然显示不了

#### 1.2.2章节

~~~
\section{\LaTeX 的使用}
\subsection{\LaTeX 的基本知识}
\subsubsection{\LaTeX 的结构}
~~~

分章节，一般都是无脑sub,但是注意，最多到`\subsubsection`，没有`\subsubsubsection`,如果你还想在\subsubsection以下分段的话，只能选择`\paragraph`：

~~~
\section{Introduction}
There is a theory which states that if ever anyone discovers exactly what the Universe is for and why it is here, it will instantly disappear and be replaced by something even more bizarre and inexplicable.
There is another theory which states that this has already happened.
\subsection{subsection}
I am subsection.

\subsubsection{subsubsection}
I am subsubsection.

\paragraph{P1} I am paragraph one.

\paragraph{P2} I am paragraph two.
~~~

效果如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210304185231443.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzMwMTMzMw==,size_16,color_FFFFFF,t_70)

#### 1.2.3 列表

~~~
接下来是列表：
	\begin{enumerate}
	\item 第一条
	\item 第二条
	\item 第三条
	\end{enumerate}
~~~

#### 1.2.2 换行

想要达到两段文字之间换行的效果，两段文字之间必须要有一个空行

~~~
	第一行第一行第一行第一行第一行
	
	第二行第二行第二行第二行第二行
~~~

#### 1.2.2转义

\ +"…"表示将某个字符转义为原来的样子显示，如`{}、&`等具有特殊含义的字符

~~~
\{显示大括号\}
~~~

## 2 公式

### 2.1 普通公式

~~~
	\begin{equation}
	girlfriends=money*face
	\end{equation}
~~~

运行效果：![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526225332336.png)

不要标号的

~~~
\begin{equation}
girlfriends=money*face \notag
\end{equation}
~~~

~~~
\begin{equation*}
girlfriends=money*face
\end{equation*}

\[
girlfriends=money*face
\]
~~~

运行效果：![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526225513219.png)

普通公式在一个环境里不支持`\\`换行，例如：

~~~
\begin{equation}
girlfriends=money*face1 \\
boyfriends=face^n 
\end{equation}
~~~

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526225756816.png)

需要用到`align`换行公式

~~~
%换行公式
\begin{align}
girlfriends=money*face \notag \\ %%如果想要这一行没标号的话，notag要加在\\之前
boyfriends=face^n 
\end{align}

~~~

效果：![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526225913495.png)

还可以使用`&`实现行间对齐

~~~
\begin{align}
&girlfriends=money*face \notag \\ 
&boyfriends=face^n 
\end{align}
~~~

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526230040775.png)

### 2.3 行内公式

用`$ $`实现文字内部插入公式：

~~~
这是一个众所周知的定理：$girlfriends=money*face$，所以你只能在这里写博客
~~~

> 注意的是，现在latex最好不要用`$ $`这种行内公式写法，最好使用`\( \)`的写法。同样行间公式也应该用`\[ \]`而不是`$$ $$`

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526231036807.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzMwMTMzMw==,size_16,color_FFFFFF,t_70)



# **至此已经入门了，剩下用到了有问题自行百度**





