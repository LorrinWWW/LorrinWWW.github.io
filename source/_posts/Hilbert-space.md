---
title: Hilbert space
date: 2017-02-11 13:10:06
categories: [math]
tags: [Hilbert, math, analyse]
---

# 希尔伯特空间 Hilbert space

## 感性认识

摘自wiki:

>在数学里，**希尔伯特空间**即**完备的内积空间**，也就是说一个带有内积的完备向量空间。

要弄清楚希尔伯特空间，我们需要从几个基本的地方出发。

### 几个形容词

- 线性

  有线性结构的。

- 赋范

  空间中用于度量“长度”，引入范数。

- 完备(complet)

  其上所有的柯西序列会收敛到此空间里的一点，序列的极限依然在此空间内。通俗的说，我们认为这个空间是不缺点、有皮的。

- 内积

  补充“角度”概念，引入内积。

### 几类空间

- 线性空间

- 度量空间

  最基本的空间。前者有线性结构，后者有度量空间，二者没有交集。

- 赋范线性空间

  引入范数

- 内积空间

  内积空间是赋范线性空间。

- 希尔伯特空间

  希尔伯特空间是完备的内积空间

((线性空间 + 范数  = 赋范空间 + 线性结构) + 内积 = 内积空间) + 完备性 = 希尔伯特空间

## 可以由以下空间获得

- 欧几里得空间

  定义内积。

- 序列空间

- 勒贝格空间

  特指L^2空间，定义其内积:

  ​
  $$
  (f|g) = \int{\overline{f}g}
  $$
  还需证明其完备性.

- 索伯列夫空间

  一般表示为H^s或W^(s,2)。在偏微分方程中常用。

## 希尔伯特空间的基

- 所有基的范数为1
- 彼此正交
- 其线性扩张稠密：即其中的所有元素的有限的线性组合是H的一个稠密子集。

## 相关

- 内积(produit scalaire)

  满足以下四个条件：

$$
\forall (x,y) \in H^2 \qquad \varphi(y,x) = \overline{\varphi(x,y)} \\
\forall (x,y,z) \in H^3, \forall(\lambda,\mu) \in \mathbb{C}^2 \qquad \varphi(z,\lambda x+\mu y) = \lambda\varphi(z,x) + \mu \varphi(z,y) \\
\forall x \in H^2 \qquad \varphi(x,x) \ge 0 \\
\varphi (x,x) = 0 \Longrightarrow x = 0
$$
