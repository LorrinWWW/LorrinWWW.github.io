---
title: 编码解码 compression
date: 2016-11-27 14:22:11
categories: programming
tags: [algo, compression, programming]
hidden: true
---

1. Run length encoding

   ex:

   0101 — 0,101 — "3 pixels are color '0'"

   1101 — 1,101 — "6 pixels are color '1'"

   You can also define other signification like:

   1 |1111|1111|1111|1111|0111|0111|0111|0111| with the first 1 meaning encoding in rank, while 0 meaning encoding in row.

2. Huffman

   Defined in wiki

   Normally we supppose higher number with "1".

   ex:

   ​                        (1)

   ​                   0/       \1

   ​            a(0.45)     (0.55)

   ​                             0/     \1

   ​                     b(0.25)    c(0.30)

3. Lempel-Ziv

   Encode:

   - Origin: ababcbab...
   - Init: a:0, b:1, c:2
   - Extensions du dico: ab: 3, ba: 4, abc: 5, cb: 6...
   - Result: 01324...

   Decode: pass

   ​