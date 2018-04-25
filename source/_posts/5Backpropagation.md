---
title: Backpropagation
date: 2017-03-20 17:29:14
banner: /css/images/pic/bp7.png
tags: deep learning
---

Backpropagation 算法在神经网络中扮演这重要作用。他的出现使得我们先计算neural network的gradients descent的时候更加有效。本文就重点来讲讲backpropagation的实现原理。

深度学习中的名词都看上去比较高大上，什么backpropagation\forwark pass\backwark pass等等，其实内部用到的数学知识就只用到了chain role。

![pic1](/images/pic/bp1.png)
<!--more-->

比方说我们现在有输入 $x^n$ 经过 neural network 得到输出 $y^n$,我们把残差记作 $C_n$

我们就可以得到残差，及其微分
$$L(\theta) = \sum_{i=1}^N C^n(\theta)$$

$$\frac{\partial L(\theta)}{\partial w} = \sum_{n=1}^N \frac{\partial C^n (\theta)} {\partial w}$$

![pic2](/images/pic/bp2.png)

上图是我们的网络的具体样子，先只关注红色框框里的这一部分：

![](/images/pic/bp3.png)

根据chain role，只关注一项C，因为求和都是一样的。
$$\frac{\partial C}{\partial w} = \frac{\partial z}{\partial w}\frac{\partial C}{\partial z}$$

那么这里的$\frac{\partial z}{\partial w}$ 就是forward pass；$\frac{\partial C}{\partial z}$就是我们backward pass。

为什么这么说，看下面的图就很好理解，

![](/images/pic/bp4.png)

口算就能得出$\frac{\partial z}{\partial w_1} = x_1$, $\frac{\partial z}{\partial w_2} = x_2$ ，而我们可以想想一下，下一层的偏微分其实就是z经过 activate function之后的value。所以就叫做forward pass。

![](/images/pic/bp5.png)

根据上面这张图，我们可以推导出来
$$\frac{\partial C}{\partial z} = \sigma	'(z) [w_3 \frac{\partial C}{\partial z'} + w_4 \frac{\partial C}{\partial z''}]$$
那$\frac{\partial C}{\partial z'}$以此类推，需要根据下一层的$\frac{\partial C}{\partial z'''}$得到。一直到output为止。然后我们就可以反过来看这个nerual netwrok他的形式其实如下图：
![](/images/pic/bp6.png)
所以我们可以根据output反向，依次进行计算出每一层的$\frac{\partial C}{\partial z_i}$。最后两项相乘就得到了我们要求的
$$\frac{\partial C}{\partial w} = \frac{\partial z}{\partial w}\frac{\partial C}{\partial z}$$
