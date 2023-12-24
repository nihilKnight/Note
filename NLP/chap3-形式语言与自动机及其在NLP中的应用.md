# 形式语言与自动机及其在NLP中的应用

- [基本概念](#基本概念)
- [形式语言](#形式语言)
- [自动机](#自动机)
- [有限自动机的应用](#有限自动机的应用)

## 基本概念

1. 树：一个连通的无回路的无向图称为树。

2. 字符串：
    - 定义：假定$\Sigma$是字符的有限集合，由$\Sigma$中字符相连而成的有限序列被称之为$\Sigma$上的字符串。特殊地，不包含任何字符的字符串称为空串。
    - 操作：（1）连接；（2）方幂；（3）符号串集合的乘积；（4）闭包。

3. 正则表达式：
    > 正则表达式简称正则式，对应于$\Sigma$上的一些子集（正则集），并通过递归定义：
    > - 空集$\emptyset$和空字符串的集合$\{\epsilon\}$是正则集；
    > - 任何$x\in\Sigma$，若$x$是正则式，则它的正则集是$\{x\}$；
    > - 如果$X,Y$是$\Sigma$上的正则式，且其对应的正则集是$U,V$。则$X|Y,\;X\cdot Y,\;X^*$也是正则式，且它们的正则集为$U\cup V,\;U\cdot V,\;U^*$。

## 形式语言

1. 语言描述的三种途径：
    - **穷举法**：只适合句子数目有限的语言；
    - **语法描述**：生成语言中合格的句子；
    - **自动机**：对输入的句子进行检验，区别哪些是语言中的句子，哪些不是。

2. 形式语言：用来精确地描述语言（包括人工语言和自然语言）及其结构的手段。**形式语言学**也称**代数语言学**。

3. 形式语言：
    > 形式语法是一个4元组$G=(N,\Sigma,P,S)$，其中$N$是非终结符的有限集合（变量集/句法种类集）；$\Sigma$是终结符的有限集合，$N\cap\Sigma=\emptyset$；$v=N\cup\Sigma$为总词汇表；$P$是一组重写规则的有限集合：$P={\alpha\rightarrow\beta}$，其中$\alpha,\beta$是$V$中元素构成的串，但$\alpha$至少应含有一个非终结符；$S\in N$为句子符或初始符。

4. 推导：
    > 设$G=(N,\Sigma,P,S)$是一个文法，在$(N\cup\Sigma^*)$上：
    > - **直接派生或推导**$\;\overset{\Rightarrow}{_{_G}}$：若$\alpha\beta\gamma\in(N\cup\Sigma)^*,(\beta\rightarrow\delta)\in P$，则有$\alpha\beta\gamma\;\overset{\Rightarrow}{_{_G}}\;\alpha\delta\gamma$。
    > - **按非平凡方式派生**$\;\overset{+}{\overset{\Rightarrow}{_{_G}}}$：表示$\overset{\Rightarrow}{_{_G}}$的传递闭包，即由$(N\cup\Sigma)^*$上的符号串$\xi_i$到$\xi_{i+1}$的$n(n\ge1)$步推导或派生。
    > - **派生**$\;\overset{*}{\overset{\Rightarrow}{_{_G}}}$：表示$\overset{\Rightarrow}{_{_G}}$的自反和传递闭包，即由$(N\cup\Sigma)^*$上的符号串$\xi_i$到$\xi_{i+1}$的$n(n\ge0)$步推导或派生。
    - 最左推导、最右推导和规范推导：
        - 约定每步推导只改写最左边的非终结符，称为“**最左推导**”。
        - 约定每步推导只改写最右边的非终结符，称为“**最右推导**”。
        - 最右推导也称**规范推导**。

5. 文法划分：（1）3型文法（正则文法）；（2）2型文法（上下文无关文法）；（3）1型文法（上下文有关文法）；（4）0型文法（无约束文法）。
    - 派生规则约束：
        - （左线性）正则文法：$A\rightarrow Bx, A\rightarrow x, A,B\in N,x\in\Sigma$；
        - 上下文无关文法：$A\rightarrow\alpha,A\in N,\alpha\in(N\cup\Sigma)^*$；
        - 上下文有关文法：$\alpha A\beta\rightarrow\alpha\gamma\beta,A\in N,\alpha,\beta,\gamma\in(N\cup\Sigma)^*,|\gamma|\ge1$；
        - 无约束文法（/无限制重写系统）：$\alpha\rightarrow\beta,\alpha,\beta\in(N\cup\Sigma)^*$。
    - 关系：$L(G3)\subset L(G2)\subset L(G1)\subset L(G0)$。

## 自动机



## 有限自动机的应用
