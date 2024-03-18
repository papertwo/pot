==英文文献如何阅读？==

读文献可以先快速过一遍，不要对每个公式穷根究底，这样做可能效率极低，说不定我们的精度就是老师的粗度，这可能也是为什么老师理解文献的速度那么快了

==另外一方面==，可能读文献的速度并不是天赋决定的，日积月累，熟能生巧，或者对一个领域足够了解了，读起来就会很快，相应，效率就会很高

文章的构成也是粗度要看的一部分，并不是按照introduction-...这个就叫看了文章的构成，每一部分写了什么东西也是粗度的一部分，也就是说粗度和细读并不是通过这两个词来区分的，粗度的程度由你自己定义，这可能也是为什么老师说我们汇报的时候普遍理解的不够深入，我们认为的精度在老师看来可能只是刚过粗读的效果，归根结底的解决方法是什么

读的慢可能还是能力问题

文章读得多了，你就知道读一篇文章时重点关注哪些方面了，读文章得时候就非常有针对性，文章读起来自然而然地就加速了

==要在一个领域广泛地读文章。多读，多理解==

翻译没问题，但没理解文章内容

专业词汇不要自己翻译，最好通过人工智能或者百度翻译，否则很容易出错，本来就看不懂，还翻译错，岂不是更难看懂

论文中i.e.的意思是换句话说，也就是说

# 通过绘制相图寻找吸引域

![image-20240223144529092](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240223144529092.png)

![image-20240223144019189](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240223144019189.png)

如上图，吸引域就是一个有限圆

缺点：状态量只能显示二维的



# 李雅普诺夫方法

zubov‘theorem（祖博夫定理）--找到吸引域边界的基础工具，该理论有**存在性定理**的特点且需要求偏微分方程的解。

注：渐近稳定的区域并不等于吸引域的估计，**因此用李雅普诺夫函数求出来的渐近稳定区域并不等于吸引域**



常用方法：线性化→李雅普诺夫函数→渐近稳定范围的→能量函数小于某一常数的状态范围→这个范围就是吸引域估计



# 平方和规划算法（数值方法maybe）

## TAC2009本文介绍了MATLAB中如何用平方和法检验多项式的非负性（可能侧重matlab与SOS方法）：Pre- and Post-Processing Sum-of-Squares Programs in Practice

【检索来源：SOS关键词谷歌学术】

## ①TAC2008本文介绍了（可能侧重）：Stability region analysis using polynomial and composite polynomial Lyapunov functions and sum-of-squares programming

【检索来源：TR汇报论文参考文献SOS相关】

本文含有吸引域估计的大致框架

大多数计算方法针对于计算吸引域的内边界（就是保守估计？）分为lyapunov方法**本文侧重点**（基于局部稳定性理论与寻找满足条件的函数）与non-lyapunov方法



## auto1985本文介绍了多种吸引域估计方法（基于极大李雅普诺夫函数【本文有介绍】），：Maximal lyapunov functions and domains of attraction for autonomous nonlinear systems

【检索来源：①】

导出了表征极大ly函数的偏微分方程并讨论了与zubov方法的关系

并提出了求解偏微分方程的迭代方法、

获得吸引域的方式：1. zubov's method        2. fit hyper-ellipse into S并使用Dvision和Kurak's method

吸引域的形式并不一定是图像呈现出来的，也可以是解析式，比如一个包含多变量的不等式



## TAC    :Robust Region-of-Attraction Estimation

【检索来源：R汇报论文参考文献SOS相关】



## auto  ：Local stability analysis using simulations and sum-of-squares programming

【检索来源：R汇报论文参考文献SOS相关】

**方法论**：文章提出了一种利用模拟信息生成Lyapunov函数候选解的方法，这些候选解满足双线性约束的必要条件。通过解决线性平方和优化问题来评估Lyapunov函数候选解的适用性。合格的候选解用于计算ROA的不变子集，并初始化各种双线性搜索策略以进行进一步优化。

**结论**：文章提出了一种计算动态系统渐近稳定平衡点吸引域不变子集的方法。该方法使用多项式Lyapunov函数作为局部稳定性证书，并通过模拟信息生成候选解，然后通过解决线性平方和优化问题来评估这些候选解。



# compact紧集

开集是闭集的补集（集合的开闭是相对而言的，是不可以继承的，也就是说，在某个空间的子空间上一个集合是开集，但它的开集性质无法继承到大的空间中，在大空间中可能就是一个半开半闭的集合了），但紧集可能就不一样了，可以继承（也就是说，一个集合在子空间上是紧集，那么在大空间上也是紧集）

# 范德波尔方程：

![image-20240316111957924](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240316111957924.png)

# 李普希思连续

![image-20240306165842094](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240306165842094.png)



# hopfield神经网络-吸引域（离散）

[反馈神经网络——Hopfield网络 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/457810569)

## 讲解

最初的网络输出仅有0/1，分别表示神经元的抑制和兴奋状态，4个神经网络的网格结构图如下：![img](https://pic1.zhimg.com/80/v2-2d134522dbcfa4a6d483a963a0e3ecec_720w.webp)

t时刻的神经元输入为：![image-20240226153451050](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240226153451050.png)

权重/偏置量

t+1时刻的输出为：![image-20240226153604181](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240226153604181.png)

网络的输出可作为神经元的状态，写成向量形式:![image-20240226153738475](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240226153738475.png)

用n维常微分方程来描述系统有关状态变量：![image-20240226153845506](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240226153845506.png)

吸引子与吸引域示意图：![img](https://pic2.zhimg.com/80/v2-58cc7c2d3f661d3bf5eac58a64adcfa9_1440w.webp)

**网络计算的过程就是初始输入向量经过逐次迭代向吸引子演化的过程。演化的规则是向能量函数减小的方向演化，直到达到稳定状态。**

这里引入Lyapunov函数作为能量函数，其定义为：![image-20240226154142834](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240226154142834.png)

## 设计

Hopfield网络可以用于联想记忆，因此又称**联想记忆网络**。

1. 记忆阶段

在记忆阶段，外界输入的数据，使得系统自动调整网络的权值，最终用合适的权值使系统具有若干个稳定状态，即吸引子。**联想记忆网络的记忆容量定义为吸引子的数量。**

完成联想记忆的关键在于恰当的学习算法得到网络的权值。

![image-20240226155115266](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240226155115266.png)

## 如何快速了解一个概念

提出几个问题，进行检索或者提问

1. 如何判断一个问题是否为凸问题（是否为非凸问题）



# 吸引域

求解吸引域，对一个状态方程已知的系统，算一个点是否在吸引域的范围内就是求微分方程的解

计算精准的吸引域是困难或者不可能的，因此现在的研究集中在确定吸引域的不变子集→利用李雅普诺夫的水平子集→因此引出一些重要问题

要是吸引域，得满足两个证明，①：t趋于无穷时，能量函数V趋于零；②：t趋于无穷时，系统状态x趋于平衡点

1.李雅普诺夫函数不确定，有很多确定李雅普诺夫函数的方法；这里就可以引入SOS方法，**可以通过选择不同的lyapunov function来扩大吸引域的估计**

2.为了让所求吸引域尽可能大，所求解的问题就是受约束最优化问题，因此有很多方法

其他一些可以做的方向：鲁棒吸引域估计（系统参数具有不确定有界参数）；









# 粘度解viscosity

"Viscosity solution" 在中文中可以翻译为“粘度解”。在数学中，特别是在偏微分方程和控制理论的背景下，粘度解（Viscosity Solution）是一种用于解决某些类型的非线性偏微分方程（如Hamilton-Jacobi方程）的方法。这种方法通过考虑方程的一阶导数的粘度（即斜率）来构造解，从而在某些情况下能够绕过方程可能存在的不光滑性或复杂性。粘度解在计算流体动力学、最优控制和数值分析等领域有着广泛的应用。

# 凸约束（convex constraint）

![image-20240313170822627](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240313170822627.png)

对于一个式子可以这么定义，但是对于多个式子组成的约束总体，就不能简单的这么定义了，例如：

![image-20240313171959719](C:\Users\冲浪的胡辣汤\AppData\Roaming\Typora\typora-user-images\image-20240313171959719.png)

















# 文献管理：
