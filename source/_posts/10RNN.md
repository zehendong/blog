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

![RNN 图二](/images/pic/434px-Elman_srnn.png)

图一是单层的上图中的u就是internal state。$o(t) = f_t(x_t,V_t)= h_t(W_1x_i+W_2u_{t-1})$

可以想象一下，其实我们也可以用一个很长的sequence 来 train feedfoward network，即使是长短不一的sentence，也可以通过补0来解决。而且相比较于feed forward network而言，RNN比较难train起来。但与feedfoward network相对比，RNN的优势在于：

1. 比如我们现在有一个很长的sequence需要去train。在training feedfoward netwok的时候，input layer必须也要很大，导致了layer的参数比较多，就容易在training data上比较容易出好的结果，会over-fitting；
2. RNN model只需要比较少的参数，可能在training data上比较难获得好的结果，但是一旦能够train起来，在testing data上的表现也比较好。

Deep RNN
--

Pyramidal RNN
--

Naive RNN vs LSTM
--

GRU
--
GRU参数比较少，少了一个gata。不容易overfitting


Stack RNN
--
stack的参数size可以很大。
