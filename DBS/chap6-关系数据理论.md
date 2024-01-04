# 关系数据理论

- [规范化](#规范化)
- [函数依赖的公理系统](#函数依赖的公理系统)

## 规范化

1. （非）平凡函数依赖：
    - 非平凡函数依赖：$X\rightarrow Y,Y\not\subseteq X$；
    - 平凡函数依赖：$X\rightarrow Y,Y\subset X$。

2. 完全/部分函数依赖：
    - 完全函数依赖：在$R(U)$中，若$X\rightarrow Y$，且对$X$的任意真子集$X^{\prime}$，都有$X^{\prime}\not\rightarrow T$，则称$Y$对$X$**完全函数依赖**，记作$X\xrightarrow{F}Y$。
    - 部分函数依赖：若$X\rightarrow Y$，且$Y$不完全函数依赖于$X$，则称$Y$对$X$**部分函数依赖**，记作$X\xrightarrow{P}Y$。

3. 传递函数依赖：在$R(U)$中，若由非平凡函数依赖$X\rightarrow Y,Y\rightarrow Z$，同时$Y\not\rightarrow X$，则称$Z$对$X$**传递函数依赖**，记作$X\xrightarrow{\text{传递}}Z$。

4. 范式：符合**某一级别的关系模式的集合**。
    - $1NF\supset2NF\supset3NF\supset BCNF\supset4NF\supset5NF$。

5. $2NF$：若关系模式$R\in1NF$，且每一个**非主属性**都**完全函数依赖**于**任何一个候选码**，则$R\in2NF$。
    - 解决的问题：**非主属性对候选键的部分函数依赖**。

6. $3NF$：若关系模式$R\in1NF$，且$R$中**不存在**码$X$、属性组$Y$及非主属性$Z$使得：$X\rightarrow Y,Y\rightarrow Z(Z\not\subseteq Y,Y\not\rightarrow X)$成立，则称$R\in3NF$。
    - 属性组$Y$：可能包括**部分主属性**、**非主属性**或**二者的组合**。
    - 解决的问题：**非主属性之间的依赖关系**，或称**非主属性对候选键的传递函数依赖**。

7. $BCNF$：若关系模式$R\in1NF$，且任意非平凡函数依赖$X\rightarrow Y$**必含有码**，则$R\in BCNF$。
    - 解决的问题：**主属性（组）对候选键的部分或传递函数依赖**。

8. 多值依赖：
    > 设关系模式$R(U)$，$X,Y,Z\subseteq U,Z=U-X-Y$。$R(U)$中多值依赖：
    > $$
    > X\rightarrow\rightarrow Y
    > $$
    > 成立，当且仅当对$R(U)$的任一关系$r$，给定的一对$(x,z)$有**一组**$Y$的值与之对应，且这组值**仅仅决定于**$x$而非$z$。
    - $Y$与$Z$**相互独立**。
    - **函数依赖是一种特殊的多值依赖**。

9. （非）平凡多值依赖：
    - 非平凡多值依赖：$X\rightarrow\rightarrow Y, Z\neq\emptyset$；
    - 平凡多值依赖：$X\rightarrow\rightarrow Y, Z=\emptyset$；

10. $4NF$：若关系模式$R\in1NF$，且对于$R$的每个**非平凡多值依赖**$X\rightarrow\rightarrow Y(Y\not\subseteq X)$，$X$**都含有码**，则称$R\in4NF$。
    - 不允许**非平凡且非函数依赖**的多值依赖，即允许的非平凡多值依赖实际上是**函数依赖**。
    - 解决的问题：**非平凡且非函数依赖的多值依赖**。

## 函数依赖的公理系统

11. Armstrong 公理系统：
    - A1 **自反律**：若$Y\subseteq X\subseteq U$，则$X\rightarrow Y$为$F$所蕴涵。
    - A2 **增广律**：若$X\rightarrow Y$为$F$所蕴涵，且$Z\subseteq U$，则$XZ\rightarrow YZ$为$F$所蕴涵。
    - A3 **传递律**：若$X\rightarrow Y,Y\rightarrow Z$为$F$所蕴涵，则$X\rightarrow Z$为$F$所蕴涵。

12. 推理规则：
    - **合并规则**：$X\rightarrow Y,X\rightarrow Z\Rightarrow X\rightarrow YZ$。
    - **伪传递规则**：$X\rightarrow Y,WY\rightarrow Z\Rightarrow XW\rightarrow Z$。
    - **分解规则**：$X\rightarrow Y,Z\subseteq Y\Rightarrow X\rightarrow Z$。
