---
title: Activation function
date: 2018-03-14 19:25:04
tags: machine-learning
banner: https://www.commercialradio.my/wp-content/uploads/2015/03/CRM_Trendstatistic.jpg
---
激活函数是我们在deep learning中至关重要的一个因子。我们先来看下Wikipedia中对activation function的定义：
>In computational networks, the activation function of a node defines the output of that node given an input or set of inputs. A standard computer chip circuit can be seen as a digital network of activation functions that can be "ON" (1) or "OFF" (0), depending on input. This is similar to the behavior of the linear perceptron in neural networks. However, only nonlinear activation functions allow such networks to compute nontrivial problems using only a small number of nodes. In artificial neural networks this function is also called the transfer function.
<!--more-->

每一个nueron都会带一个activation function，可见其重要性。一般来说，有这么几种性质：
1. 非线性。因为如果说activation function如果说是linear function的话，那么deep learning就可以只需要一层layer就可以了也就是一个多元方程，显然不能表征复杂的模型。这里有点类似于傅里叶展开。这样我们的model就能够解决线性模型无法解决的问题。
2. 要可微分。由于我们在train模型的时候，往往需要基于梯度做优化参数。
3. 单调性。其实这是一个伪命题，只是我们一般碰到的activation function都是单调的而已。

我们一般常见的activation function有一下几种：

![activation](/images/pic/activate1.png)

从发展历史来看，激活函数经历了Sigmoid -> Tanh -> ReLU -> Leaky ReLU -> Maxout的慢慢演变发展。同时也派生出其他很多遍变种，但是琳琅满目的激活函数，也给我们选择困难。现在学术界也没有特别的证明说，什么情况下适合用哪种激活函数。但一般有一下的经验供参考：

- 当处理分类问题，Sigmoid函数及其组合通常效果更好（可以看一下上面sigmoid图，是不是很像一个理想分类器呢）
- 由于梯度消失问题，有时要避免使用sigmoid和tanh函数，建议用Relu
- ReLU函数是一个通用的激活函数，目前在大多数情况下使用。所以我们要是一开始不知道要用什么好，那么建议可以先从ReLU开始
- 如果神经网络中出现死神经元，那么PReLU函数就是最好的选择

本文简单介绍了一下神经网络中的现今常用激活函数，还有很多其他没有提到的变种，不过主要思想都是一致的。随着deep learning的快速发展，相信会有更多更理想的激活函数提出来。
