---
title: Note of NLP
date: 2017-06-26 20:52:45
categories: [programming]
tags: [nlp, machine-learning, deep-learning]
---

# NLP

1. "One-hot" representation

   每一个词都作为一个特征，用一个很大的向量来描述文章。
   $$
   [0,0,0,0,0,0,0,0,0,1,0,0,0]
   $$

2. Main idea of word2vec

   Two algorithms

   1. Skip-grams
   2. Continuous bag of words (CBOW)

   Two training methods

   1. Hierarchical softmax
   2. Negative sampling

## 基于深度学习的关系提取

>[Zeng et al. 2014] 提出采用卷积神经网络进行关系抽取。他们采用词汇向量和词的位置向量作为卷积神经网络的输入，通过卷积层、池化层和非线性层得到句子表示。通过考虑实体的位置向量和其他相关的词汇特征，句子中的实体信息能够被较好地考虑到关系抽取中。后来，[Santos et al. 2015]还提出了一种新的卷积神经网络进行关系抽取，其中采用了新的损失函数，能够有效地提高不同关系类别之间的区分性。
>
>[Miwa et al. 2016] 提出了一种基于端到端神经网络的关系抽取模型。该模型使用双向 LSTM（Long-Short Term Memory，长短时记忆模型）和树形 LSTM 同时对实体和句子进行建模。目前，基于卷积神经网络的方法在关系抽取的标准数据集 SemEval-2010 Task 8 上取得了最好的效果。
>
>--基于深度学习的关系抽取技术进展_刘知远_熊德意

RNN在NLP中应用较多，有关它的文章：[The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) 译文[递归神经网络不可思议的有效性](http://www.csdn.net/article/2015-08-28/2825569)

其中目前比较流行的是LSTM，有关它的文章：[Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) 译文 [理解LSTM网络](http://blog.csdn.net/jerr__y/article/details/58598296)

[LSTM的tensorflow简单实现](http://blog.csdn.net/jerr__y/article/details/61195257)

### GAN ?

ACGAN可用于分类问题，Discriminator输出正伪的同时还会输出类别。适合类别数量已给定的情况。

InfoGAN。

半监督GAN。