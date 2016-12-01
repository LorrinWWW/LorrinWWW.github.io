---
title: proba-ch2 随机变量
date: 2016-12-01 12:17:33
categories: math
tags: [probability, math, aleatoire]
---

- ​

$$
\pi-system
$$

- R上的概率测度

  - 分布函数 la fonction de repartition
    $$
    F:x\xrightarrow{}F(x) = P(] - \infty,x] ) \\ F:x\xrightarrow{}F(x) = \int_{ ]-\infty,x] }{f(t).\lambda(dt)}
    $$

  - 定理

    如果F是分布函数，则当且仅当满足以下三个条件。
    $$
    (i) F 递增\\(ii)F 右连续\\(iii) \lim_{n \rightarrow - \infty}{F(x)=0}, \lim_{n \rightarrow+\infty}{F(x)=1}
    $$

  - 性质
    $$
    P(\{x\}) = F(x) - F(x-)
    $$

- R^N上的概率测度

  -  定义
  $$
    F:(x_1,...,x_N)\xrightarrow{}F(x_1,...,x_N) = P(\prod_{i=1}^{N}] - \infty,x_i] )
  $$

  - 定义
    $$
    P(dx_1,...,dx_N) = f(x_1,...,x_N)dx_1...dx_N \\ where||f||_{L^2}
    $$

- 随机变量

  - 定义
    $$
    Soit(\Omega,{\cal F})\rightarrow (E, {\cal E}); X:\Omega \rightarrow E \\ \forall A\in {\cal E}; X^{-1}(A) \in {\cal F}
    $$
    X就是一个随机变量

  - 定义 tribu engendree par X
    $$
    X^{-1}({\cal E}) = \{X^{-1}(A); A \in {\cal E}\} \\ \sigma(X)
    $$

- 随机变量的loi

  - 定义
    $$
    \forall A \in {\cal E}; P_X(A) = P(\{\omega: X(\omega) \in A\}) = P(X^{-1}(A))
    $$

- 积分

  - 数学期望定义
    $$
    E[X] = \int_{\Omega}{X(\omega).P(d\omega)}= \int_{\Omega}{X.dP}
    $$

  - 定理
    $$
    (X_n)_{n\in N} 是随机变量
    $$

    - 单调趋向性：若Xn非负且趋于X，则
      $$
      \lim_{n \rightarrow \infty}{E[X_n]} = E[X]
      $$

    - Fatou引理：若Xn非负
      $$
      E[\lim_{n \rightarrow \infty}{\inf{X_n}}] \leq \lim_{n \rightarrow \infty}{\inf{E[X_n]}}
      $$

    - convergence dominee: 若limXn = X p.s 若存在Z in L1，且|Xn|<=Z，则
      $$
      \lim_{n \rightarrow \infty}{E[X_n]} = E[X]
      $$

  - 性质(Inegalite de Markov)

    若X是随机变量并admettant un moment d'ordre 1, 对于实数a>0
    $$
    P(|X| \geq a) \leq \frac{E[|X|]}{a}
    $$

  - 转化定理
    $$
    E[h(X)] = \int_E{h(x)P_X(dx)}
    $$

  - 定义
  $$
  un\ moment\ d'ordre\ n: \int_\Omega{|X|^ndP} < \infty
  $$

  - 性质，若0<p<q，可以得到Lq被Lp包含。

  - 定义方差，前面说过了

    - $$
      Var(aX+b) = a^2 Var(X) \\ P(|X-E[X]| \geq a) \leq \frac{Var(X)}{a^2}
      $$

    - 若X几乎处处等于同一个常数，当仅当Var(X) = 0

  - 定理，与离散相似的
    $$
    E[h(X)] = \int_E{h(x)f_X(dx)}
    $$
    特别的
    $$
    P(X \in A) = E[1_{\{X\in A\}}] = \int_A{f_X(dx)}
    $$

- Vecteurs aleatoires

  X = (X1,…,XN) 与多元离散随机变量类似。

  - 协方差
    $$
    Cov(X,Y) = E[(X-E[X])(Y-E[Y])] = E[XY] - E[X]E[Y]
    $$

    - 性质
      $$
      Cov(X,X) =Var(X) \\ Cov(X,Y) = Cov(Y,X) \\ Var(X+Y) = Var(X) +Var(Y) +2Cov(X,Y)
      $$

  - 相关系数
    $$
    \rho(X,Y) = \frac{Cov(X,Y)}{\sigma(X)\sigma(Y)}, \sigma(X) = \sqrt{Var(X)}, -1 \leq \rho \leq 1
    $$

  - 改变变量
    $$
    \forall y \in R^N; f_Y(y) = \frac{f_X(h^{-1}(y))}{|det(Jh(h^{-1}))|} 1_D(y)
    $$

  - 边际概率，顾名思义，略

- 独立变量

  定义略

  - 定理，满足下列条件之一，则XY独立

    1. 对于所有A，B
    $$
      P(X \in A, Y\in B) = P(X\in A)
    $$

    2. 对于所有f，g
    $$
      E[f(X)g(Y)] = E[f(X)] E[g(Y)]
    $$

    3. 对于所有f，g，f(X)和g(Y)是独立的

  - 性质
    $$
    \text{Soient (X, Y) un couple de variables aleatoires a valeurs dans } E\otimes F \text{ muni de la tribu produit } \mathcal{E} \otimes \tilde{\mathcal{E}}. \\ \text{ X et Y sont independantes si et seulement si la lor jointe du couple (X, Y) est egale a la mesure produit } P_X \otimes P_Y.
    $$
    $$
    \text{注：对于XY相互独立，} P((X,Y)\in A \times B) = P_X(A)P_Y(B) \\
    P_X \otimes P_Y(A \times B) = P_X(A)P_Y(B)
    $$

  - 定理，对于随机变量XY，他们相互独立，当且仅当
    $$
    \forall (x,y) \in R^2; F_{(X,Y)}(x,y) = F_X(x)F_Y(y)
    $$

  - 定理，对于(X,Y)在lebesgue测度上绝对连续，XY相互独立当且仅当
    $$
    \forall (x,y) \in R^2; f_{(X,Y)}(x,y) = f_X(x)f_Y(y)
    $$

  - 性质，XY admettant un moment d'ordre 1, 相互独立，则

  - $$
    E[XY]=E[X]E[Y]
    $$

  - 性质，XY admettant un moment d'ordre 2, Cov(X,Y)=0, 则

  - $$
    Var(X+Y) =Var(X) + Var(Y)
    $$

    ​
