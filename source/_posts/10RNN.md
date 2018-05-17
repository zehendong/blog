---
title: The introduction of RNNs
date: 2017-07-19 14:25:08
tags: deep learning
---

RNN简单介绍
--
RNN发明于1980s，照例先看一下维基的定义：
>A recurrent neural network (RNN) is a class of artificial neural network where connections between nodes form a directed graph along a sequence. This allows it to exhibit dynamic temporal behavior for a time sequence. Unlike feedforward neural networks, RNNs can use their internal state (memory) to process sequences of inputs. This makes them applicable to tasks such as unsegmented, connected handwriting recognition[1] or speech recognition.

RNN的结构如下：

<!--more-->

![RNN 图一](/images/pic/640px-Recurrent_neural_network_unfold.svg.png)

内部的结构其实是这样子，

![RNN 图二](/images/pic/434px-Elman_srnn.png)

图一是单层的上图中的u就是internal state。$o(t)=h_t(Wx_i+Wv_{t-1})$

可以想象一下，其实我们也可以用一个很长的sequence 来 train feedfoward network，即使是长短不一的sentence，也可以通过补0来解决。而且相比较于feed forward network而言，RNN比较难train起来。但与feedfoward network相对比，RNN的优势在于：
1. 比如我们现在有一个很长的sequence需要去train。在training feedfoward netwok的时候，input layer必须也要很大，导致了layer的参数比较多，就容易在training data上比较容易出好的结果，会over-fitting；
2. RNN model只需要比较少的参数，可能在training data上比较难获得好的结果，但是一旦能够train起来，在testing data上的表现也比较好。

Deep RNN
--
RNN当然也可以是deep的，只要能够把第一层的output的维度和第二层的input相匹配，就可以了。
![deep RNN](/images/pic/deeprnn.png)

Pyramidal RNN
--
Pyramidal的模型，能够大大降低计算量。因为rnn中的sequence是无法并行计算的，而pyramidal rnn中，两个input可以并行计算，所以就能够在大大降低计算量,并且越深的RNN，sequence越短。
![pyramidal RNN](/images/pic/pyramidalrnn.png)


LSTM
--
LSTM（Long Short-Term Memory）是长短期记忆网络，是一种时间递归神经网络，适合于处理和预测时间序列中间隔和延迟相对较长的重要事件。
下面这张图，左边是RNN的结构，右边是LSTM的结构。显而易见LSTM多了一个c的输入。c变化的比较慢，因此能看到long-term的信息。具体有关LSTM的内容，后续再具体讲讲，这里就不展开了。

![RNN.vs.LSTM](/images/pic/lstmvsrnn.png)



GRU
--
GRU参数比较少，外观和RNN差不多。跟LSTM相比，少了一个Gate。有一种说法就是，GRU因为参数少，就不容易overfitting。GRU在很多应用上效果比LSTM要好。


Stack RNN
--
在Stack RNN中，input的stack参数可以很大。stack只需要取出前几个element，公共一个function F。
$$F(stack_n,x^t) = (Info,push,pop,nothing)$$
F输出的info就是需要push到下一个stack中的vector，stack中的n需要自己先设定好。
![stack RNN](/images/pic/stackrnn.png)

参考文献：
1. William Chan, Navdeep Jaitly, Quoc V. Le, Oriol Vinyals. "Listen, Attend and Spell".arXiv:1508.01211 [cs.CL]
2. Armand Joulin, Tomas Mikolov.Inferring Algorithmic Patterns with Stack-Augmented Recurrent Nets. arXiv:1503.01007 [cs.NE]
3. Junyoung Chung, Caglar Gulcehre, KyungHyun Cho, Yoshua Bengio. Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling. arXiv:1412.3555 [cs.NE]
