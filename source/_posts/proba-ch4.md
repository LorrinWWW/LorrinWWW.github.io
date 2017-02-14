---
title: proba-ch4 高斯向量
date: 2016-12-01 16:28:52
categories: math
tags: [probability, math, vector]
---

定义

Un vecteur aléatoire est dit gaussien si toute combinaison linéaire de ses composantes suit une loi gaussienne.

也就是：
$$
\forall \lambda_1,...,\lambda_N \in \mathbb{R} , \sum_{j=1}^{N}{\lambda_jX_j \text{ suit une loi normale.}}
$$

- 特征函数
  $$
  \varphi_X: t \rightarrow e^{i < \mu, t> -\frac{1}{2}<t,Dt>} \\
  => \varphi_X = e^{i\sum_{j=1}^{N}{\mu_j t_j}- \frac{1}{2}\sum_{1\le j,k\le N}{t_j D_{j,k}t_k}}
  $$
  $\mu$, le vecteur moyenne, 平均向量

  D, la matrice de covariances de X, 协方差矩阵

- 理论，X=(X1,…,XN) 是高斯向量，则Xj相互独立当仅当其协方差矩阵D为对角线矩阵。（也就是只有自己和自己的协方差不为零）

- Densite de la loi d'un vecteur gaussien
  $$
  D \ne 0 \\
  \mathcal{N}(\mu,D) \text{在Lebesgue测度下，在}\mathbb{R}^N\text{上绝对连续} \\
  x \longmapsto \frac{1}{(2\pi)^{N/2}\sqrt{\det D}}e^{-\frac{1}{2}<x-\mu,D^{-1}(x-\mu)>}
  $$

