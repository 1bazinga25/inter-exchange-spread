# 跨市套利策略

[![Logo](https://img.shields.io/badge/KuCoin-KuMex-yellowgreen?style=flat-square)](https://github.com/Kucoin-academy/Guide)
[![GitHub stars](https://img.shields.io/github/stars/Kucoin-academy/inter-exchange-spread.svg?label=Stars&style=flat-square)](https://github.com/Kucoin-academy/inter-exchange-spread)
[![GitHub forks](https://img.shields.io/github/forks/Kucoin-academy/inter-exchange-spread.svg?label=Fork&style=flat-square)](https://github.com/Kucoin-academy/inter-exchange-spread)
[![GitHub issues](https://img.shields.io/github/issues/Kucoin-academy/inter-exchange-spread.svg?label=Issue&style=flat-square)](https://github.com/Kucoin-academy/inter-exchange-spread/issues)

[![](https://img.shields.io/badge/lang-English-informational.svg?longCache=true&style=flat-square)](README_EN.md)
[![](https://img.shields.io/badge/lang-Chinese-red.svg?longCache=true&style=flat-square)](README_CN.md)

## 策略描述

跨市套利策略，俗称“搬砖”。

**当同一交易标的在两个交易所间存在价差时，从 A 交易所买入，B 交易所卖出，赚取价差**。

**通俗的讲**，我得知在韩国 (KuCoin交易所) 神仙水 (BTC) 价格是1000元，但国内 (Huobi交易所) 价格是1800元，而我的货运成本 (手续费) 是200元。那么，我在韩国买10个神仙水到国内全部卖出，除去成本费用，总共能赚取价差（1800-1000）* 10 - 200 = 7800元。

也就是说，**当价差能覆盖交易成本时**，在不考虑其他特殊情况下，**你一定能赚钱**。

但是实际情况肯定不会如此理想，所以你得知道其中的**特殊情况**：

* 你不可能将所有机会都抓住，价格实时变化，利润毫秒之间就有可能消失；
* 虽说是无风险套利，但是单边成交的情况，会导致亏损；
* 交易所Api在大行情的时候容易出现访问延迟和错误。

那策略的重点是什么呢？

* **价差**，指定交易标的在不同交易所的价格差异；
* **交易成本**，maker/taker的交易手续费，期货还包括额外的资金费率。

因此你需要保证当你在“搬砖”的时候，你所选交易标的的价格差异能够覆盖你的交易成本，你才能够保持盈利。

<img src="./img/spread_huobi.jpg" style="zoom:60%;" />

上图是KuCoin交易所与huobi交易所周BTC-USDT交易对的价差图，可以看到价差大的地方还是比较多的，差值也基本有5USDT左右。

如果你还能得到一定的手续费折扣，那可以你说你的“睡后”收入必然很可观了。

**KuCoin**拥有**level3交易数据、强大的撮合引擎、针对api用户提供的手续费折扣**，同时提供**sandbox环境**作为数据测试支撑，帮助你规避风险。

我们仅提供一个简单且不完备的交易策略，使用时**请注意规避风险**，我们希望你能够**在sandbox环境配合其他参数或是策略进行测试调整，我们也不想你成为一个慈善家！！！**

当然，如果这个过程中，你遇到任何问题或是有赚钱的策略想要分享，请在**ISSUE**中反映，我们会努力及时响应。

:point_right: 如果你对该策略有兴趣，请点击**右上角star**，我们会根据star数来衡量策略的**受欢迎程度和后续优化优先级**，你也可以点击**右上角watching**通过接收更新通知来持续关注该项目。

