---
title: 'EDP基础：矩阵的复习'
date: 2017-02-07 10:22:27
categories: [math]
tags: [EDP, matrix]
---

## 注意点：

1. A est une matrice hermitienne <=> A=A* et donc A est normale
2. A est une matrice  unitaire (酉矩阵) <=> A^-1 = A* et donc A est normale
3. A est une matrice orthogonale <=> A=A^T



## Schur定理（矩陣三角化）

$$
A = [a_{ij}]_{n\times n} , 特征值\lambda_i , 对应特征向量x_i \\
S = [x_1,...,x_n], D = diag[\lambda_1,...,\lambda_n] \\
则,A是可对角化矩阵 \\
A = SDS^{-1}
$$

如果**A**是*n*阶的复方阵，则存在*n*阶酉矩阵U，*n*阶上三角矩阵T，使得：
$$
A = UTU^{-1}
$$

## 酉矩阵

$$
UU^* = I \\
i.e. \to U^*= U^{-1}
$$

U是酉矩阵。



## Cholesky分解

条件：

1. une matrice hermitienne：矩阵中的元素共轭对称（复数域的定义，类比于实数对称矩阵）。Hermitiank意味着对于任意向量x和y，(x*)Ay共轭相等
2. Positive-definite：正定矩阵A意味着，对于任何向量x，(x^T)Ax总是大于零(复数域是(x*)Ax>0)

则存在L为下三角矩阵，使得 A = LL*。



## QR分解

目标：A = QR，*Q*是正交矩阵（意味着*Q*T*Q* = *I*）而*R*是上三角矩阵。

