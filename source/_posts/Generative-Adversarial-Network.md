---
title: Generative Adversarial Network
date: 2017-06-25 14:41:15
categories: [programming]
tags: [GAN, deep-learning]
typora-copy-images-to: ipic
hidden: true
---

# Generative Adversarial Network

## Generater

1. Auto encoder

   input => nn encoder => code => nn decoder => output

   Output compared with input as close as possible

   [code => nn decoder => output] := a generater

2. VAE

   Auto-encoder Variational Bayes:

   input => nn encoder 

   => {

   ​    code : [$m_i$],

   ​    variation : [$\sigma_i$],

   ​    error : [$e_i$],

   } 

   => {$c_i = exp(\sigma_i) \times e_i + m_i$}

   => nn decoder => output

   The goal is to monimize the expression as followed:
   $$
   \sum(exp(\sigma_i) - (1+\sigma_i) + (m_i)^2)
   $$





## GAN

<img src="https://lorrin-1251763245.cos.ap-shanghai.myqcloud.com/photo/2018-03-12-202530.png" width="70%">

相当于是由一个生成器和分类器(true or false)

极大似然$P_{data}(x; \theta) , P_G(x;\theta)$

- Generator G

  - G is a function, input z, output x
  - Given a prior distribution $P_{prior}(z)$, a probability distribution $P_G(x)$ is defined by function G

- Discriminator D

  - D is a function, input x, output scalar
  - Evaluate the "difference" between $P_G(x)$ and $P_{data}(x)$

- Function V(G, D)
  $$
  G^* = {arg} {min}_G {max}_D V(G,D)
  $$




从G*中可以看出，D是在给定G的情况下，尽其所能地提高V，即发现$P_{data}$和$P_G$的最多的差异。而G则是使该值尽量减小。在G和D的博弈中模型逐渐完善。

给定V
$$
V = E_{x~P_{data}}[logD(x)]+ E_{x~P_G}[log(1-D(x))] \\
= \int_x P_{data}(x)logD(x)dx +\int_xP_G(x)log(1-D(X))dx \\
= \int_x[P_{data}(x)logD(x) + P_G(x)log(1-D(x))]dx
$$
要让V的大小可以由积分内的式子决定，即
$$
P_{data}(x)logD(x) + P_G(x)log(1-D(x))
$$
i.e. find D* maximizing: $f(D) = alog(D)+blog(1-D)$
$$
=> D^* = \frac{a}{a+b} = \frac{P_{data}(x)}{P_{data}(x)+P_{G}(x)}
$$
所以
$$
max_D V(G,D) = V(G, D^*) \\
= -2log2 + \int_x P_{data}(x) log\frac{P_{data}(x)}{(P_{data}(x)+P_{G}(x))/2}dx \\ + \int_x P_{data}(x) log\frac{P_{G}(x)}{(P_{data}(x)+P_{G}(x))/2}dx \\
= -2log2 + KL(P_{data}(x) ||\frac{P_{data}(x)+P_{G}(x)}{2}) \\ 
+ KL(P_{G}(x) ||\frac{P_{data}(x)+P_{G}(x)}{2}) \\
= -2log2 + 2JSD(P_{data}(X||P_G(x))
$$
其中
$$
KL := KL divergence \\
JSD(P||Q) = \frac{1}{2}(KL(P||M) + KL(Q||M)), M= \frac{P+Q}{2}
$$
所以$max_D(G,D)$，当且仅当$P_G = P_{data}$

### **总结一下算法**

- Given $G_0$
- Find $D_0^*$ maximizing $V(G_0,D)$
- $\theta_G \leftarrow \theta_G - \eta \partial V(G, D_0^*)/ \partial \theta_G $ => Obtain G1
- Find $D_1^*$ maximizing $V(G_1,D)$
- ...

#### 实际操作

我们知道实际上是不能求期望，即作不能作积分的。因此需要一定的近似。

我们需要将其离散化，取m个样本，V可以写为
$$
V = \frac{1}{m}\sum logD(x_i) + \frac{1}{m} \sum log(1-D(x_i^G)) \\
where \{x_1, ..., x_m\}  from P_{data}(x), \{x_1^G,...,x_m^G\} from P_G(x)
$$
