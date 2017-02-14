---
title: Note of statistic
date: 2017-01-28 18:13:13
categories: [math, unfinished]
tags: [statistic, math]
---

# 各种定理

### 大数定理，中心极限定理

略

### Slutsky

if
$$
\Upsilon_n \to(loi) \Upsilon \text{ et } Z_n \to (P)c
$$
then
$$
\Upsilon_n + Z_n \to(L) \Upsilon+c \text{ et } \Upsilon_n Z_n \to(L) \Upsilon c
$$

# 假设检验

## un test de $\chi^2$

列表：

| Liste | a    | b    | c    |
| ----- | ---- | ---- | ---- |
| pi    | xx   | xx   | xx   |
| npi   | xx   | xx   | xx   |
| ni    | xx   | xx   | xx   |

计算：
$$
T= \sum_{j=1}^n{\frac{(n_i-np_i)^2}{np_i}}
$$
其服从卡方分布，自由度为n-1，从而进行检验。