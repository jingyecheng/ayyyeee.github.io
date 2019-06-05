---
layout: post
title:  "非局部均值(Non-Local Means,NLM)"
date:   2019-06-02
categories: 图像去噪
tags: 图像去噪
---

# 非局部均值 (Non-Local Means,NLM) 去噪

## 动机
* 对固定场景连续拍照，得到T张图像\\(I(t)\\),\\(t\\)表示时间。图像\\(I(t)\\)被噪声\\(n(t)\\)污染，假设噪声均值=0，那么将图像求平均\\(\frac1T\sum_1^TI(t)\\)可以降噪。

<img src="{{site.baseurl}}/assets/nlm/multiple-lena.png" height=50% width=40%>
# ![Lena-Sum](../assets/nlm/sum-lena.png)







