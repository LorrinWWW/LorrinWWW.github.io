---
title: 解决hexo使用公式冲突问题 hexo with latex
date: 2016-11-30 22:19:02
categories: other
tags: [hexo, latex, mathjax, marked]
---

在hexo中使用大量公式的同学一定会发现，在hexo很多公式的渲染不正常。这是由于markdown渲染器和latex渲染器冲突的问题（具体说，就是公式中的特殊字符首先被markdown渲染器转义了）。我们可以通过更换Markdown渲染插件来解决这个问题。

Google了一些博文，在[如何处理Hexo和MathJax的兼容问题](http://2wildkids.com/2016/10/06/%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86Hexo%E5%92%8CMathJax%E7%9A%84%E5%85%BC%E5%AE%B9%E9%97%AE%E9%A2%98/)这篇文章中发现了一个符合要求的插件：[hexo-renderer-kramed](https://github.com/sun11/hexo-renderer-kramed)。作者fork了 hexo-renderer-marked 项目，并且只对MathJax支持进行了改进，其他特性完全一致。

简单粗暴的讲，卸载原渲染器，安装我们需要的渲染器。

依次运行下列语句即可。

```
$ npm uninstall hexo-renderer-marked --save
$ npm install hexo-renderer-kramed --save
```

现在公式的显示已经正常。

注：传说行内代码渲染仍然有问题，在代码块中工作正常。