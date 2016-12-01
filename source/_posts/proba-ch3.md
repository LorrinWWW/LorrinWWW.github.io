---
title: proba-ch3 实域概率和特征方程
date: 2016-12-01 14:54:10
categories: math
tags: [probability, math]
---

1. 几种常见分布

    若不在区间内，f=0

   1. loi uniforme
      $$
      f(x)=\frac{1}{b-a} si\ x \in [a,b]
      $$

   2. loi exponentielle
      $$
      f(x) = \lambda e^{-\lambda x} si\ x \ge 0 \\
      E[X] = \frac{1}{\lambda}, Var(X) = \lambda^2
      $$

   3. Loi de weibull
      $$
      f(x) = \alpha \lambda^\alpha x^{\alpha-1}e^{-(\lambda x)^\alpha} si\ x \ge 0\\
      E[X] = \frac{\Gamma(1+1/\alpha)}{\lambda}, Var(X) = \frac{\Gamma(1+2/\alpha)}{\lambda^2}
      $$

   4. loi gamma
      $$
      f(x) = \frac{\lambda}{\Gamma(p)}(\lambda x)^{p-1}e^{-\lambda x}\\
      E[X] = \frac{p}{\lambda}, Var(X) = \frac{p}{\lambda^2}
      $$

   5. loi normale
      $$
      f(x) = \frac{1}{\sqrt{2\pi}\sigma}exp[-\frac{(x-m)^2}{2\sigma^2}], x \in R\\
      E[X] = m, Var(X) = \sigma^2
      $$

   6. Loi lognormale
      $$
      f(x) = \frac{1}{\sqrt{2\pi}\sigma x}exp[-\frac{(\ln x-m)^2}{2\sigma^2}], x \ge 0 \\
      E[X] = e^{m+\sigma^2/2}, Var(X) = e^{2m+\sigma^2}(e^{\sigma^@}-1)
      $$

   7. Loi du $ \chi^2 $
      $$
      X = U_1^2+...+U_n^2 \\
      U_i\ est\ de\ loi\ \mathcal{N}(0,1) \\
      E[X] = n, Var(X) = 2n
      $$

   8. Loi de Student
      $$
      X = \frac{U}{\sqrt{\frac{Z}{n}}} \\
      U\ suit\ la\ loi\ normale\ \mathcal{N}(0,1) \\
      Z\text{ est independante de U et suit la loi du }\chi^2\text{ a n degres de liberte}
      $$

2. 特征函数
   $$
   \varphi_X: \mathbb{R^N} \rightarrow \mathbb{C} \\
   t \rightarrow \varphi_X(t) = E[e^{i<t,X>}] = \int_{\mathbb{R}^N}{e^{i<t,X>}P_X(dx)}
   $$
   我们说特征函数是对X进行基于PX的傅立叶变换 = =好绕

   若PX存在概率密度 $f \in L^1$
   $$
   \varphi_X(t) = \int_{\mathbb{R}^N}{e^{i<t,X>}f(x)dx}
   $$

   - 性质

     - $$
       \forall t \in \mathbb{R}^N, |\varphi_X(t)| \le 1=> \varphi_X(0) = 1
       $$

       $$
       \varphi_{\lambda X+a}(t) = e^{iat}\varphi_X(\lambda t)
       $$

       $$
       \varphi_X 是一个半正函数，即 \\
       \forall z_1,...,z_n\in \mathbb{C}, \sum_{1 \le j, k\le n}{z_j \varphi_X(t_j-t_k)\bar{z_k}} \ge 0
       $$

   - 其他性质

     - 特征函数连续

     - PX以lebesgue测度绝对连续，则

     - $$
       \lim_{|t|\rightarrow \infty}{\varphi_X(t)} = 0
       $$

     - XY，它们拥有相同的P，当且仅当

     - $$
       \varphi_X=\varphi_Y
       $$

     - 逆变换

     - $$
       \forall x \in \mathbb{R}^N, f(x)=\frac{1}{(2\pi)^N}\int_{\mathbb{R}^N}{e^{-i<t,X>}\varphi_X(t)}dt
       $$

   - 特征方程和独立性

     - 定理
       $$
       X_1,...,X_N \text{ 是独立的，当且仅当它们的特征方程满足：} \\
       \forall t = (t_1,...,t_N) \in \mathbb{R}^N; \varphi_X(t) = \prod_{k=1}^{N}{\varphi_{X_k}(t_k) } \\
       where\ X = (X_1,...,X_N)
       $$

     - 性质
       $$
       X_1,...,X_n independants, P_{X_1},...,P_{X_N}. \\
       \text{La loi de } \sum{X_i} \text{est le produit de concolution } \prod{P_{X_i}} \\
       \text{Pour fonction caracteristique } \sum{\varphi_{X_i}} \text{definie par} \\
       \forall t \in \mathbb{R}^N; \varphi_{X+...+X_n}(t) = \prod_{i=1}^{n}{\varphi_{X_i}(t) }
       $$


