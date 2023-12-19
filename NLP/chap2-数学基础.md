# 数学基础

- [概率论基础](#概率论基础)
- [信息论基础](#信息论基础)
- [应用案例](应用案例)

## 概率论基础

1. 最大似然估计：

   > 如果一个实验的样本空间是$\{S_1,S_2,\cdots,S_n\}$，在相同的情况下重复试验$N$次，观察到样本$s_k(1\le k\le n)$的次数为$n_k(s_k)$，则$s_k$的相对概率为：
   > $$
   > q_N(s_k) = \dfrac{n_N(s_k)}{N}
   > $$
   > 由于$\sum_{k=1}^nn_N(s_k)=N$，因此$\sum_{k=1}^nq_N(s_k)=1$。
   >
   > 当$N$越来越大时，相对频率$q_N(s_k)$就越来越接近$s_k$的概率$P(s_k)$。事实上：
   > $$
   > \lim\limits_{N\rightarrow\infty}q_N(s_k)=P(s_k)
   > $$
   > 因此，相对频率常用作概率的估计值。这种概率值的估计方法称为<u>**最大似然估计**</u>。

2. 贝叶斯决策理论：

   > 假设研究的分类问题有$c$个类别，各类别的状态用$w_i(i=1,2,\cdots,c)$表示，$w_i$出现的先验概率为$P(w_i)$；在特征空间已观察到某一向量$\overline{x}=[x_1,x_2,\dots,x_d]^T$是$d$维特征空间上的某一点，且条件概率密度函数$P(x|w_i)$是已知的。那么，利用贝叶斯公式可以得到后验概率：
   > $$
   > P(w_i|\overline{x})=\dfrac{P(\overline{x}|w_i)P(w_i)}{\sum_{j=1}^nP(\overline{x}|w_j)P(w_j)}
   > $$
   > <u>**基于最小错误律的贝叶斯决策规则**</u>为：
   >
   > （1）如果$P(w_i|\overline{x})=\max\limits_{j=1,2,\cdots,c}P(w_j|\overline{x})$，则$\overline{x}\in w_i$；
   >
   > （2）或：如果$P(\overline{x}|w_i)P(w_i)=\max\limits_{j=1,2,\cdots,c}P(w_j|\overline{x})P(w_j)$，则$\overline{x}\in w_i$；
   >
   > （3）或（$c=2$）：如果$l(\overline{x})=\dfrac{P(\overline{x}|w_1)}{P(\overline{x}|w_2)}>\dfrac{P(w_2)}{P(w_1)}$，则$\overline{x}\in w_1$，否则$\overline{x}\in w_2$。
   >
   > <u>**贝叶斯决策理论在文本分类、词汇语义消歧等问题的研究中具有重要用途**</u>。

3. 二项式分布：

   > <u>**在自然语言处理中，一般以句子为处理单位。假设一个句子独立于它前面的其他语句，句子的概率分布近似地认为符合二项式分布**</u>。

## 信息论基础

1. 熵：

   > 如果$X$是一个离散型随机变量，其概率分布为：$\{p(x)=P(X=x)|x\in X\}$。$X$的熵$H(X)$为：
   > $$
   > H(X)=-\sum\limits_{x\in X}p(x)\log_2p(x)
   > $$
   > 其中，约定$0\log0=0$。$H(X)$也可以写为$H(p)$。通常熵的单位为二进制比特位（bit）。
   >
   > 熵又称为自信息（self-information），表示信源$X$每发一个符号（不论发什么符号）所提供的平均信息量。<u>**熵也可以被视为描述一个随机变量不确定性的数量**</u>。一个随机变量的熵越大，它的不确定性越大。那么，正确估计其值的可能性就越小。越不确定的随机变量需要越大的信息量用以确定其值。

2. 联合熵：

   > 如果$X,Y$是一对离散型随机变量$(X,Y)\sim p(x,y)$，则$X,Y$的联合熵$H(X,Y)$为：
   > $$
   > H(X,Y)=-\sum\limits_{x\in X}\sum\limits_{y\in Y}p(x,y)\log_2p(x,y)
   > $$
   > <u>**联合熵实际上就是描述一对随机变量平均所需信息量的数量**</u>。

3. 条件熵：

   > 给定随机变量$X$的情况下，随机变量$Y$的条件熵定义为：
   > $$
   > \begin{aligned}
   > H(Y|X)&=\sum_{x\in X}p(x)H(Y|X=x)\\
   > &=\sum_{x\in X}p(x)[-\sum_{y\in Y}p(y|x)\log_2p(y|x)]\\
   > &=-\sum_{x\in X}\sum_{y\in Y}p(x,y)\log_2p(y|x)
   > \end{aligned}
   > $$
   >
   > - <u>**条件熵与联合熵的关系**</u>：$H(X,Y)=H(X)+H(Y|X)$（<u>**连锁规则**</u>）。	
   >   - tips:
   >
   > $$
   > \begin{aligned}
   > H(X,Y)&=-\sum_{x\in X}\sum{y\in Y}p(x,y)\cdot\log[p(x)p(y|x)]\\
   > &=-\sum_{x\in X}\sum{y\in Y}p(x,y)\cdot[\log p(x)+\log p(y|x)]
   > \end{aligned}
   > $$
   >
   > - $H(X|Y)\neq H(Y|X)$。

4. 熵率：

   > 一般地，对于一条长度为$n$的信息，每一个字符或字的<u>**熵率**</u>为：
   > $$
   > H_{\text{rate}}=\dfrac{1}{n}\cdot H(X_{1n})=-\dfrac{1}{n}\sum_{x_{1n}}p(x_{1n})\log p(x_{1n})
   > $$
   > 其中，变量$X_{1n}$表示随机变量序列$(X_1,\cdots,X_n)$。 $x_{1n}=x_1,\cdots,x_n$，亦作：$x_1^n=(x_1,\cdots,x_n)$。

5. 相对熵（或Kullback-Leibler divergence，KL距离）：

   > 两个概率分布$p(x),q(x)$的<u>**相对熵**</u>为：
   > $$
   > D(p||q)=\sum_{x\in X}p(x)\log\dfrac{p(x)}{q(x)}
   > $$
   > 约定$0\log(0/q)=0$及$p\log(p/0)=\infty$。
   >
   > 相对熵常被用以衡量两个随机分布的差距。当两个随机变量相同时，其相对熵为0。当两个随机分布的差别增加时，其相对熵也增加。

6. 交叉熵：

   > 如果一个随机变量$X\sim p(x)$，$q(x)$为用于近似$p(x)$的概率分布，则随机变量$X$和<u>**模型**</u>$q$之间的交叉熵为：
   > $$
   > H(X,q)=H(X)+D(p||q)=-\sum_xp(x)\log q(x)
   > $$
   > <u>**交叉熵的概念用以衡量估计模型与真实概率分布之间的差异**</u>。
   >
   > 语言$L=(X_i)\sim p(x)$与其模型$q$的交叉熵为：
   > $$
   > H(L,q)=-\lim_{n\rightarrow\infty}\dfrac{1}{n}\sum_{x^n_1}p(x^n_1)\log q(x^n_1)
   > $$
   > 其中，$x^n_1=(x_1,\cdots,x_n)$为语言$L$的语句。$p(x^n_1)$为$L$中语句$x^n_1$的概率；$q(x^n_1)$为模型$q$对$x^n_1$的概率估计。
   >
   > 假设这一语言是“理想”的，即$n\rightarrow\infty$时，其全部“单词”的概率之和为1。则进一步有以下定理：
   >
   > > 假定语言$L$是<u>**稳态**</u>随机过程，$x^n_1$为$L$的样本，$L$与其模型$q$的交叉熵为：
   > > $$
   > > H(L,q)=-\lim_{n\rightarrow\infty}\dfrac{1}{n}\sum_{x^n_1}p(x^n_1)\log q(x^n_1)\\
   > > \Downarrow\\
   > > H(L,q)=-\lim_{n\rightarrow\infty}\dfrac{1}{n}\log q(x^n_1)
   > > $$
   >
   > 由此，可以根据模型$q$和一个含有大量数据的$L$的样本来计算交叉熵。在设计模型$q$时，我们的目的是<u>**使交叉熵最小**</u>，从而使模型最接近真实的概率分布$p(x)$。

7. 困惑度：

   > 给定语言$L$的样本$l^n_1=(l_1,\cdots,l_n)$，$L$的<u>**困惑度**</u>$PP_q$为：
   > $$
   > PP_q=2^{H(L,q)}\approx2^{-\frac{1}{n}\log q(l^n_1)}=[q(l^n_1)]^{-\frac{1}{n}}
   > $$
   > 在设计语言模型时，通常用困惑度来代替交叉熵衡量语言模型的好坏。语言模型设计的任务就是寻找<u>**困惑度**</u>最小的模型，使其最接近真实的语言。

8. 互信息：

## 应用案例