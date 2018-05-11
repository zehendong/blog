RNN简单介绍
RNN的结构如下：
![RNN]()

我们也可以用一个很长的sequence去train feedfoward network，及时比如说是长短不一的sentence，也可以补0。往往来说rnn相比较于feed forward network而言，比较难train起来。但与feedfoward network相对比，rnn的优势在于：

1. 比如我们现在有一个很长的sequence需要去train。在training feedfoward netwok的时候，input layer必须也要很大，导致了layer的参数比较多，就容易在training data上比较容易出好的结果，容易over-fitting；
2. 相比较而言，rnn的好处就是，我们的model只需要比较少的参数，可能在training data上比较难获得好的结果，但是一旦train起来，在testing

Deep RNN
