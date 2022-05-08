---
title: 面向考试常用编程思想 Method of programming facing to exams
date: 2016-11-27 13:49:31
categories: programming
tags: [algo, programming]
hidden: true
---

1. 穷举法

   略

2. 贪心法

   略

3. 分治法

   ```Python
   def merge(A, B):
       # merge two small solved problems into one.
       return merged

   def divideConquer(S, divide, combine):
       if len(S) == 1: return S
       # divide a grand problems
       L, R = divide(S)
       A = divideConquer(L, divide, combine)
       B = divideConquer(R, divide, combine)
       return merge(A, B)
   ```

   上面的情形只供参考，参数等视具体情况而定。

4. 动态规划

   比较经典的就是背包问题。[代码来源](http://blog.csdn.net/littlethunder/article/details/26575417)

   ```Python
   def bag(n,c,w,v):  
       res=[[-1 for j in range(c+1)] for i in range(n+1)]  
       for j in range(c+1):  
           res[0][j]=0  
       for i in range(1,n+1):  
           for j in range(1,c+1):  
               res[i][j]=res[i-1][j]  
               if j>=w[i-1] and res[i][j]<res[i-1][j-w[i-1]]+v[i-1]:  
                   res[i][j]=res[i-1][j-w[i-1]]+v[i-1]  
       return res  
     
   def show(n,c,w,res):  
       print('最大价值为:',res[n][c])  
       x=[False for i in range(n)]  
       j=c  
       for i in range(1,n+1):  
           if res[i][j]>res[i-1][j]:  
               x[i-1]=True  
               j-=w[i-1]  
       print('选择的物品为:')  
       for i in range(n):  
           if x[i]:  
               print('第',i,'个,',end='')  
       print('')  
     
   if __name__=='__main__':  
       n=5  
       c=10  
       w=[2,2,6,5,4]  
       v=[6,3,5,4,6]  
       res=bag(n,c,w,v)  
       show(n,c,w,res)
   ```

   ​