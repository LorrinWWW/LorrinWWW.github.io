---
title: Note of knowledge graph
date: 2017-06-25 11:21:18
categories: [programming]
tags: [knowledge-graph, machine-learning, datamining]
hidden: true
---

# 知识图谱 Knowledge graph

知识图谱的概念由Google提出，目前成为一大热点。总体而言，英文知识图谱的文献相对齐全。中英文知识图谱的差别主要体现于对自然语言的处理，对于中文而言，首先准确的分词，其次要应对中文想对自由的语法和语言形式。

下面是一些笔记。

知识图谱的构建：

## 1. 信息抽取 information extraction

我们需要能够自动化地从结构化、半结构化和无结构数据中抽取实体(entity)、关系(relationship)以及实体属性等。

1. 实体抽取 entity extraction
   - 实体提取：
     - liu等人，Knn算法和条件随机场模型
     - lin等人，字典和最大熵算法
   - 实体分类：
     - 2012，ling等人，借鉴freebase归纳实体分类方法，条件随机场模型进行实体边界识别，自适应感知机算法实现对实体的自动分类，结果优于Stanford NER等主流命名实体识别系统
     - 预定义实体分类并不好，新思路：对于给定实体，采用统计机器学习等方法，从目标数据集中抽取与之俱有相似的上下文特征等实体，从而实现实体的分类和聚类。参考whitelaw的解决方案
     - ​
2. 关系抽取 relationship extraction