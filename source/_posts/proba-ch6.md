---
title: proba-ch6 条件期望
categories: math
tags:
  - math
  - probability
date: 2016-12-02 21:32:30
hidden: true
---

$$
P(A|B) = \frac{P(A\cap B)}{P(B)}
$$

$$
E[X|Y=y] = E_Q[X] = \sum_{x \in \tilde E}{xP(X=x|Y=y)}
$$

$$
\psi : y \mapsto E[X|Y=y] \text{ if } P(Y=y) > 0 \\
otherwise\ 0
$$

$$
E[X|Y] = \psi(Y)
$$

- 定义
  $$
  \mathcal{G} 是一个sous-tribu。\\
  E[X|\mathcal{G}] 是一个随机变量Y,满足 \\
  Y \in L^1, \forall A \in \mathcal{G}, \int_A X dP = \int_AYdP
  $$

- 定义 L2
  $$
  X \in L^2, \mathcal{G} 是一个sous-tribu \\
  E[X|\mathcal{G}] 是一个随机变量Y,满足 \\
  \forall Z \in L^2, E[XZ] = E[YZ]
  $$

  - 性质
    $$
    E[E[X|\mathcal{G}]] = E[X]
    $$

  - 性质
    $$
    若X \in L^1, E[X|\mathcal{G}] = E[X] \Leftrightarrow X是\mathcal{G}可测的。
    $$

  - 性质
    $$
    X是\mathcal{G}可测的, X,Y,XY \in L^1 \\
    \Rightarrow E[XY|\mathcal{G}] = XE[Y|\mathcal{G}]
    $$

- 定义
  $$
  E[X|Y] = E[X|\sigma(Y)]
  $$

  - 性质 若XY是实随机变量，则存在一个函数h
    $$
    E[X|Y] = h(Y)
    $$
