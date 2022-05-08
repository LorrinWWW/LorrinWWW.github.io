---
title: 复杂度 complexity
date: 2016-11-27 10:52:05
categories: programming
tags: [algo, programming, complexity]
hidden: true
---

# 计算复杂度 - Calcul the complexity

这里我们只考虑时间复杂度。

There, we only discuss the time complexity.

## 通常 - Normal

1. Single operation - O(1)

2. Loop

   ```Python
   def fun(n):
   	for i in range(n):
      		pass
   ```

   ```python
   def fun(n):
   	while i < n :
       	i += 1
   ```

   — O(n)

   ```python
   def fun(n):
       while i < n :
           i *= 2
   ```

   — O(logn)

   Etc.

   ## 递归 - Recursion
   1.  代入法

       预估其复杂度，代入原方程，若相符，则可能为解。

       ex:

       T(n) = 2*T(n/2) + O(n)

       假设 T(n) = kn^2

       代入原式，成立。

       接下来用数学归纳法验证。

   2.  迭代法

          迭代地展开递归方程的右端，使其成为一个非递归的和式，随后进行复杂度计算

          ex:

          T(n) = T(n-1) + O(1)

          T(1) = O(1)

          所以，T(n) = T(n-1) + O(1) = T(n-1) + 2 * O(1) = … = n*O(1) = O(n)

   3.  套用公式

          对于形如

          T(n) = aT(n/b) +f(n)

          的方程已有固定判断法，套用公式即可。

   4.  差分方程法

          利用查分方程解，这个比较复杂，这里先占个位，以后在补。