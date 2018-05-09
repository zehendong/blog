---
title: 时间序列预测算法：Arima
date: 2018-03-14 14:25:08
tags: machine-learning
banner: https://www.commercialradio.my/wp-content/uploads/2015/03/CRM_Trendstatistic.jpg
---
时间序列（time series）是一门特殊的研究方向，在我们生活中处处可见。因此时间序列的研究也广泛应用于型号处理、模式识别、计量经济、天气预报等。本文将要介绍的是一种传统的时间序列预测算法——Arima。本文结构：
- 什么是Arima
- Arima的数学模型
- Arima的参数调整
- python的实现
- 常见问题
- Arima的变种

ARIMA模型（英语：Autoregressive Integrated Moving Average model），差分整合移动平均自回归模型，又称整合移动平均自回归模型（移动也可称作滑动），时间序列预测分析方法之一。ARIMA（p，d，q）中，AR是"自回归"，p为自回归项数；MA为"滑动平均"，q为滑动平均项数，d为使之成为平稳序列所做的差分次数（阶数）。
