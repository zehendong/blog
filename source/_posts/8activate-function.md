---
title: Activation function
date: 2018-03-14 19:25:04
tags: machine-learning
banner: https://www.commercialradio.my/wp-content/uploads/2015/03/CRM_Trendstatistic.jpg
---
激活函数是我们在deep learning中至关重要的一个因子。所以今天就来简单的归纳一下activate function。

每一个nueron都会带一个activation function，可见其重要性。一般来说，有这么几种性质：
1. 非线性。因为如果说activation function如果说是linear function的话，那么deep learning就可以只需要一层layer就可以了也就是一个多元方程，显然不能表征复杂的模型。这里有点类似于傅里叶展开。
2. 要可微分。由于我们在train模型的时候，往往需要基于梯度做优化参数。
3. 单调性。其实这是一个伪命题，只是我们一般碰到的activation function都是单调的而已。

我们一般常见的activation function有一下几种：

| Name | plot   |  Equation | deriavative 
| :-----:  | :-----:  |
| -d, --deploy | Deploy after generation finishes |
