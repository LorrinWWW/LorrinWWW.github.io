---
title: 数据挖掘笔记 Note of datamining
date: 2016-11-30 15:35:24
categories: [programming, unfinished]
tags: [datamining]
---

# 构成

一般说的数据挖掘指的是知识挖掘，构成如下：

1. 数据清洗 - data clearing
2. 数据集成 - data integration
3. 数据转换 - data transformation
4. 数据挖掘 - data mining
5. 模式评估 - pattern evaluation
6. 知识表示 - knowledge presentation

分析：

1. 关联分析

   age(X, "20-29") ^ income(X, "20K-30K") => buys(X, "MP3")

   [support = 2%, confidence = 60%]

2. 分类预测

   分类挖掘的主要表示手段有：

   - 分类规则
   - 决策树
   - 数学公式
   - 神经网络

3. 聚类分析

   与分类预测的主要区别是，后者是分类已知，属于监督学习方法；前者无事先确定类别归属，属于无监督学习方法。