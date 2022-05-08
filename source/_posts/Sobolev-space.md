---
title: Sobolev space
date: 2017-02-11 14:37:53
categories: [math, unfinished]
tags: [Sobolev, analyse, math, EDP]
hidden: true
---

# 索伯列夫空间 Sobolev space

## 感性认识

摘自wiki：

>数学上，一个索博列夫空间是一个由函数组成的赋范向量空间，对于某个给定的p ≥ 1，它对一个函数f和它的直到某个k阶导数加上有限Lp范数的这个条件。

我们通常在C1(函数1阶可导并且1阶导数连续)上研究微分方程的解，但是在偏微分方程上并不是特别方便，人们便开始研究索伯列夫空间。

## 范数

$$
||f||_{k,p} = (\sum_{i=0}^k{||f^{(i)}||_p^p})^{1/p} \\
=||f^{(i)}||_p +||f||_p
$$

赋予了范数的$W^{k,p}$是一个完备空间。

## $H^k$

一些记号：
$$
H^k = W^{k,2} \\
H^1(\Omega) := \{ v\in L^2(\Omega) : \nabla v \in (L^2(\Omega))^d \} \\ \\
(.,.)_{H^1} : (u,v) \in H^1 \times H^1 \mapsto (u,v)_{L^2} +(\nabla u,\nabla v)_{L^2} \\
\qquad \qquad \qquad = \int_\Omega {uv} + \sum_{i=1}^d{\int_ \Omega {\partial_{x_i}{u} \partial_{x_i}{v}}}
$$

范数和半范数：
$$
||.||_{H^1}: v \mapsto \sqrt{||v||_{L^2}^2+||\nabla v||_{L^2}^2} \\
|.|_{H^1(\Omega)} := ||\nabla .||_{L^2(\Omega)} \\
||.||_{H_0^1} := |.|_{H^1}
$$
