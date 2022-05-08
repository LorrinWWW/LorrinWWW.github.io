---
title: proba-ch1 概率空间
date: 2016-12-01 12:17:29
categories: math
tags: [probability, math]
hidden: true
---

- 一个基本的不等式，当


$$
P(\cup(A_n)) \leq \sum_{n \in N}^{}{P(A_n)}
$$

- 如果An递增

$$
P(\cup(A_n)) = \lim_{n -> + \inf}{P(A_n)}
$$

- 如果An递减

$$
P(\cap(A_n)) = \lim_{n -> + \inf}{P(A_n)}
$$

- 条件概率定义，略
- 性质

$$
P({A_1}\cap{...}\cap{A_{n-1}}) = P(A_1)P(A_2|A_1)...P(A_n|A_1\cap{...}\cap{A_{n-1}})
$$

- 定理(Equation de partition)

$$
P(A) = \sum_{n}{P(A|E_n)P(E_n)}
$$

- 定理(de Bay)

$$
P(E_n|A) = \frac{P(A|E_n)P(E_n)}{\sum_{m}{P(A|E_m)PE_m}}
$$

- 两个独立事件概率，略

- 定理

  对一可数或有限事件集，P({wn}) = pn，若对pn求和，则P存在且唯一。

- 均值定义，
  $$
  E[X] = \sum_{\omega \in{\Omega}}{X(\omega) P(\omega)}
  $$

- 方差定义

$$
Var(X) = E[(X - E(X))^2] = E[X^2] - (E(X)^2)
$$

- 几种分布

  - Loi discrete uniforme，

  - $$
    \forall k \in \{1,...,n\}, P(X=k) = \frac{1}{n}
    $$

    $$
    E[X] = \frac{n+1}{2}
    $$

  - Loi de Bernoulli，

    $$
    P(X=1) = p, t P(X=0) = 1-p
    $$
    $$
    E[N] = p, Var(N) = p(1-p)
    $$

  - Loi binomiale 二项分布，略
    $$
    E[N] = np, Var(N) = np(1-p)
    $$

  - Loi geometrique 
    $$
    P(N=n) = P^n(1-p),$$$$
    E[N] = np, Var(N) = np(1-p)
    $$

  - Distribution de Poisson
    $$
    P(X=n)=\frac{\lambda^n}{n!}e^{-\lambda},
    $$
    $$
    E[X] = \lambda, Var(X) = \lambda
    $$
