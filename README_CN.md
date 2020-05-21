# 跨市套利策略

[![Logo](https://img.shields.io/badge/KuCoin-KuMex-yellowgreen?style=flat-square)](https://github.com/Kucoin-academy/Guide)
[![GitHub stars](https://img.shields.io/github/stars/Kucoin-academy/inter-exchange-spread.svg?label=Stars&style=flat-square)](https://github.com/Kucoin-academy/inter-exchange-spread)
[![GitHub forks](https://img.shields.io/github/forks/Kucoin-academy/inter-exchange-spread.svg?label=Fork&style=flat-square)](https://github.com/Kucoin-academy/inter-exchange-spread)
[![GitHub issues](https://img.shields.io/github/issues/Kucoin-academy/inter-exchange-spread.svg?label=Issue&style=flat-square)](https://github.com/Kucoin-academy/inter-exchange-spread/issues)

[![](https://img.shields.io/badge/lang-English-informational.svg?longCache=true&style=flat-square)](README.md)
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

因为你需要保证当你在“搬砖”的时候，你所选交易标的的价格差异能够覆盖你的交易成本，你才能够保持盈利。

**KuCoin**交易所提供**level3的交易行情数据**，保证你能在第一时间获取行情的变化，同时也保证了买卖盘透明性；

也提供了**极优的撮合引擎**，使你的订单能够更加快速的成交；

还提供了对api用户“低门槛”的**手续费优惠活动**，你只需要申请，满足条件即可享受手续费的优惠，让你能拥有很低的交易成本。



**请注意，任何策略在使用时需要做好风险管理，如果你想在实际环境中利用策略获得稳定的盈利，我们希望你能够在sandbox环境配合其他参数或是策略进行测试调整，以使你能够达到目的，我们也非常期待你能分享你的测试数据以及独到的见解。**

**当然，如果这个过程中，你遇到任何问题需要帮助亦或是有赚钱的策略想要分享，请在ISSUE中反映，我们会努力及时响应。**

