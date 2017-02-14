---
title: proba-ch5 数列和随机变量系列
categories: math
tags:
  - math
  - probability
date: 2016-12-01 23:14:28
---

# 数列和随机变量系列

1. 零一律

   > **零一律**是概率论中的一个定律，它是安德雷·柯尔莫哥洛夫发现的，因此有时也叫柯尔莫哥洛夫零一律。其内容是：有些事件发生的概率不是几乎一（几乎肯定发生），就是几乎零（几乎肯定不发生）。这样的事件被称为“尾事件”。 — wiki

   $$
   (X_n)_{n \in \mathbb{N}} v.a. \\
   \mathcal{T}_n = \sigma(X_k; k \ge n) \\
   \mathcal{T}_{\infty} = \cap_{n \in \mathbb{N}}{\mathcal{T}_n} \text{ est   appelee tribu de queue de la suite } (X_n)_{n \in \mathbb{N}}
   $$
   - 定理(loi de zero-un)

     如果存在一个事件A属于$\mathcal{T}_{\infty}$，则P(A)等于0或1。

2. 不同定义

   - convergence presque sure

     定义，当存在一个事件满足以下条件
     $$
     \exists \Omega^*, \forall \omega \in \Omega^*, \lim_{n \rightarrow \infty}{X_n(\omega)} = X(\omega)
     $$
     我们认为一个随机变量序列趋向(p.s.)一个随机变量。即
     $$
     P\{\omega \in \Omega^*: \lim_{n \rightarrow \infty}{X_n(\omega)} = X(\omega)\} = 1
     $$

   - Convergence dans Lp

     定义。首先Xn和X都在Lp空间下，并且其差值的绝对值的p次方的期望的极限等于零。- -|||

     也就是
     $$
     \lim_{n \rightarrow \infty}{E[|X_n-X|^p]} = 0
     $$

   - convergence en probabilite

     定义，满足以下条件，称依概率收敛。
     $$
     \forall \varepsilon, \lim_{n \to \infty}{P\{\omega:X_n(\omega)-X(\omega)>\varepsilon}\}=0 \\
     ou\  \lim_{n \to \infty}{P\{X_n-X>\varepsilon}\}=0
     $$
     定理，

     1. 如果Xn趋向X(p.s.)，则fXn趋向fX(p.s.)
     2. 如果Xn趋向X(P)，则fXn趋向fX(P)

     定理，

     Xn是实随机变量，以下关系等价
     $$
     X_n \xrightarrow{P} X \Leftrightarrow \lim_{n \to \infty} E(\frac{|X_n-X|}{1+|X_n-X|}) = 0
     $$
     定理，

     Xn是实随机变量，则
     $$
     若X_n \xrightarrow{L^P}X, X_n \xrightarrow{P}{X} \\
     若X_n \to X p.s., X_n \xrightarrow{P}{X} \\
     $$
     定理，

     Xn是实随机变量，若Xn依概率收敛于X，我们能找到一个序列
     $$
     (X_{n_k})_{k \in \mathbb{N}}
     $$
     使得
     $$
     X_n \to X, p.s.
     $$
     定理，

     Xn是实随机变量，若Xn依概率收敛于X，并存在一个$Y \in L^p, |X_n| \le Y$，则
     $$
     X \in L^p并且 X_n \xrightarrow{L^p}X
     $$





3. 波莱尔－坎泰利引理

   > 大致上，波莱尔－坎泰利引理说明了，如果有无穷个概率事件，它们发生的概率之和是有限的，那么其中的无限多个事件一同发生的概率是零。这个定理实际上是测度论的结论在概率论中的应用。 —wiki

   1. 如果有无穷个概率事件，它们发生的概率之和是有限的，那么其中的无限多个事件一同发生的概率是零。
   2. 如果有无穷个概率事件，无限多个事件一同发生的概率是零，那么它们发生的概率之和是有限的。

4. 大数定律

   > 在数学与统计学中，大数定律又称大数法则、大数律，是描述相当多次数重复实验的结果的定律。根据这个定律知道，样本数量越多，则其平均就越趋近期望值。 — wiki

   - 强大数定律
     $$
     X_n \in L^2 \text{若它们独立同分布且在同一个概率空间，则} \\
     lim_{n \to \infty}{\frac{\sum_{i=1}^{n}{X_i}}{n}} = \mu \ p.s.
     $$

   - 切比雪夫大数定律
     $$
     X_n  \text{若它们独立同分布且在同一个概率空间，则} \\
     lim_{n \to \infty}{\frac{\sum_{i=1}^{n}{X_i}}{n}} = \mu \ p.s. \text{ 当且仅当} E[X_i] \text{对于所有i存在}
     $$

5. Convergence en loi

   弱趋向：
   $$
   \int_{\mathbb{R}^N}{f(x)\nu_n(dx)} \xrightarrow{n \to \infty} \int_{\mathbb{R}^N}{f(x)\nu(dx)}
   $$
   定义，若PXn弱趋向于PX，则Xn是 convergence en loi vers X。记为：
   $$
   X_n \xrightarrow{\mathcal{D}} X
   $$
   定理，
   $$
   X_n \xrightarrow{\mathcal{D}} X \Leftrightarrow \lim_{n \to \infty}E[f(X_n)] = E[f(X)]
   $$
   定理，
   $$
   X_n \xrightarrow{P} X \Rightarrow X_n \xrightarrow{\mathcal{D}} X
   $$
   定理，si Xn converge en loi vers une v.a. constante presque surement, alors elle converge en probabilite.

   - 离散变量的convergence en loi
   - 分布函数的convergence en loi
   - 特征函数的convergence en loi

   均略=_=

6. 中心极限定理
   $$
   若Var(X_n) < \infty \\
   记S_n = \sum{Xi} \\
   \frac{S_n-n\mu}{\sigma\sqrt{n}} \xrightarrow{\mathcal{D}} \mathcal{N}(0,1)
   $$
   ​

