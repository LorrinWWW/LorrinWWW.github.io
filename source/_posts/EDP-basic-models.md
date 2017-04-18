---
title: EDP basic models
categories: [math]
tags:
  - math
  - EDP
date: 2017-03-06 10:04:58
---

# Examples of moedels

1.    Problem of Cauchy

      **Nomenclature** : problem of Cauchy

      **Equation** : system of 2 differential equations of order 2

      **Conditions** : initials (all the data from the same point) i.e. fix time

      $$
      \begin{equation}
        \begin{cases}
          \frac{dS}{dt}(t) = F(S,R)  ,  \\
          \frac{dR}{dt}(t) = G(S,R) ,  \\
          S(0) = S^0 \\
          R(0) = R^0
        \end{cases}
      \end{equation}
      $$

2.    Problem of Dirichlet

      **Nomenclature** : problem of Dirichlet

      **Equation** : scalar differential equation of order 2.

      **Conditions** : prescribed value at the edge

      $$
      \begin{equation}
        \begin{cases}
      - \frac{d}{dx} ( k \frac{d\theta}{dx})(x) + \theta(x) = f(x) 0<x<L, \\
        \theta(0) = \theta_0, \theta(L) = \theta_L \\
     \end{cases}
   \end{equation}
$$

   **Remark:**

   - 如果k是常数，解为指数函数；若否，我们可以用两种数值计算：les differences finies et les elements finis.
   - 可以使用*射击法*，认为$\theta(L)$由$\theta'(0)$得到，接下来就是验证是否能找到一个好的$\theta'(0)$使$\theta(L)=\theta(L) = \theta_L$

### Physic examples

- Fluide environnant au repos
$$
  \rho c_v \partial_t{\theta} - div(k\cdot\overrightarrow{grad}(\theta)) = f
$$
  - init condition:
$$
    \theta(0,.) = \theta_0
    $$

-   condition at the edges could be:

    - condition of Dirichlet:
      $$
      \theta(t,.) = g(t)
      $$

    - Condition of Neumann:
      $$
      \overrightarrow{grad}(\theta)(t,.) \cdot \vec{n}= h(t)
      $$

    - Condition of Dirichlet and Neumann: Mix

-   Fluide environnant en mouvement a une vitesse $\vec u(t,x)$
    $$
    \rho c_v \partial_t{\theta} - div(\rho c_v \theta \vec u) - div(k\cdot\overrightarrow{grad}(\theta)) = f
    $$
    si le fluide est incompressible i.e $\partial_t \rho = 0$ soit encore $div(\vec u) = 0$ (直观上理解，若不可压缩，则速度场一定是连续的，不然一定会在局部压缩), alors:
    $$
    \rho c_v \partial_t{\theta} - \vec u \cdot div(\rho c_v \theta ) - div(k\cdot\overrightarrow{grad}(\theta)) = f
    $$
    ​

    ​