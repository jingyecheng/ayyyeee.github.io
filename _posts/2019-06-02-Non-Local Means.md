---
layout: post
title:  "非局部均值(Non-Local Means,NLM)"
date:   2019-06-02
categories: 图像去噪
tags: 图像去噪
---

# 非局部均值 (Non-Local Means,NLM) 去噪

## 动机
* 对固定场景连续拍照，得到T张图像\\(I(t)\\),\\(t\\)表示时间。图像\\(I(t)\\)被噪声\\(n(t)\\)污染，假设噪声均值\\(=0\\)，那么将图像求平均\\(\frac1T\sum_1^TI(t)\\)可以降噪。
<img src="{{site.baseurl}}/assets/nlm/sum-lena.png" height="250">
* 对于单张图像，存在冗余图像块(Patch)。将冗余块“平均”，或许可以降噪。由于冗余块不完全相同，需要特别的“平均”，具体参见**方法**
<img src="{{site.baseurl}}/assets/nlm/redundent.png" height="360">

## 方法
$$I(x) = sum_yI(y)f(p(x)-p(y))$$
* \\(I(x)\\)是图像\\(I\\)x处的像素值
* \\(p(x)\\)是以x为中心的patch，这里假设patch是\\(s \times s\\)方块

### 计算步骤
* 对图像\\(I\\)的每一点\\(x\\)，计算patch\\(p(x))\\)
* 定义一个以\\(x\\)为中心\\(w \times w\\)大小的搜索窗
* 对搜索窗内每一点\\(y\\)
    计算patch\\(p(y)\\)
    计算\\(p(x)\\)和\\(p(y)\\)的相似性，使用高斯距离平方和度量patch间相似性，
    \\(f(p(x)-p(y))=GSSD(p(x)-p(y))=e^{-1\times{SSD(p(x)-p(y))\over\sigma^2}}\\)
    ，其中\\(SSD(p(x)-p(y))=sum_{i,j}(p_{i,j}(x)-p_{i,j}(y))^2\\)
    求加权和

## 改进
### 加速
* 使用PCA对\\(p(x)\\)降维








