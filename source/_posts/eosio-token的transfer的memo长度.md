---
title: eosio.token的transfer的memo长度
date: 2019-02-18 15:07:12
tags: [eosio]
---

## 概述：
平时我们进行 EOS 币转账的时候，`memo`最多可以填多少个汉字、多少个英文字符呢？

<!--more-->

官方`eosio.token`合约的`transfer`方法，`memo`被断言为长度小于等于`256`（`eosio_assert( memo.size() <= 256, "memo has more than 256 bytes" )`），那么作为一名“专业”码农应该觉得可以输入纯英文字符最多`256`个，纯汉字减半，然鹅在链上跑的时候，并不是酱紫的。

## 敲黑板：
在链上跑的时候，纯汉字最多可以输入`85`个，纯英文字符可以输入`258`个。每个汉字占用`length`为`3`。
