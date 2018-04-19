---
title: Neural Networks
date: 2017-03-18 17:29:14
banner: https://typeset-beta.imgix.net/rehost/2016/9/13/8f21f4ef-d61e-4fdf-99d5-ce299afc4e1a.jpg?w=970&h=582&fit=crop&crop=faces&auto=format&q=70
tags: deep learning
---

Neural Networks
---
这篇文章将简单介绍一下神经网络。我们先考虑有一个supervised learning的问题（），然后我们手头上有一堆带标签的训练样本，用 $(x_i,y_i)$ 来表示。
神经网络（Neural Networks）会根据这些样本进行训练，然后给出一个复杂、非线性的hypotheses $h_W,b(x)$的模型，来拟合我们的数据，其中
的W，b为我们模型的参数。
<!--more-->

为了清晰的说明神经网络是啥玩意，先看一个简单的例子，只有一个神经元（neuron）。如下图，就是一个neuron:

![neuron](/css/images/pic/300px-SingleNeuron.png)

他有四个输入 $x_1$,$x_2$,$x_3$和为+1的截距，他的输出为

$$h_{W,b}(x) = f(W^Tx)$$

$$= f(\sum_{i=1}^3 W_i x_i +b)$$


其中的$f : \Re \mapsto \Re$ 我们把他叫做 activation function（激活函数）。这里我们就用sigmoid function 作为我们的激活函数：

$$f(z) = \frac{1}{1 + e^{-z}}$$



所以缩啊，我们的单个神经元其实就是用logistic regression（逻辑回归）来定义的输入输出映射函数f。

我们这里用的是 sigmoid 函数，但还是要大力推荐一下另外一个常用的aactivation function, tanh 函数，公式如下：

$$f(z) = tanh(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}$$

要是把sigmoid 和 tanh函数画出来的话，这两哥们长的还是有点像的：

![Sigmoid function](/css/images/pic/400px-Sigmoid_Function.png) ![tanh function](/css/images/pic/400px-Tanh_Function.png)

但是要注意的是tanh（z）的输出范围是[-1, 1]，而sigmoid 的输出范围是[0, 1]。

不同于其他地方（比如公开课CS229），我们这里没有用$x_0 = 1$,而是直接用截距参数b。

Neural Network model
---
在神经网络中，我们还可以吧很多上面介绍的 neurons 连接起来，一个neuron的输出可以是另一个neuron的输入。比如，下面这个简单的神经网络：

![neural network](/css/images/pic/400px-Network331.png)

这张图里面，我们用圆来表示网络的输入。那个写着+1的圆，就把他叫做偏置单位，对应于截距项。最左边的
叫做输入层，最右边的L3叫做输出。中间的就叫做隐藏层，因为它的值在训练集里我们不去观察。所以例子的神经网络有3个输入单元
(不包括偏置单元)，3个隐藏单元，1个输出单元。
