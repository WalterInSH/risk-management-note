# 从金融角度聊聊业务风险

我们已经聊了很多做业务风控的手段和技术，可是到现在还没有说清楚“风险控制”中的“风险”是什么。

我一直在想应该从什么角度来写这个问题，最终我决定从金融行业借鉴一些内容。这个行业已经花了几十年研究风险，我们看看这个行业会带给我们什么启示。

## 什么是风险

橡树资本联合创始人Howard Marks在几篇备忘录中阐述了他对风险的看法，下面就围绕他写过的内容聊一聊风险。

Howard Marks给风险的定义是：
>The possibility of permanent loss. A downward fluctuation – which by definition is temporary – doesn’t present a big problem if the investor is able to hold on and come out the other side.
>
>风险就是发生永久性损失的概率。一个暂时的向下波动并不是一个大问题，只要投资者可以承受，且之后可以翻盘。

业务方投入资源(包括时间和经费)去做拉新、促销，是为了获取回报，也就是更多用户、更多订单，当然说到底都是为了利润。对应Howard Marks给出的定义，业务方面临的永久性损失是什么？

一家成熟公司投入了10万元进行了一次为期1个月的促销活动，最后只多带来了1万元收入
1. 那么差值（9万元）是永久性损失吗？
2. 后一个季度公司盈利了9万元，是不是意味着公司只是经历了一次“向下波动”，并没有风险？

首先我们要避免一个误区：站在事后去评估事前发生的风险。下面这些想法对于分析风险是没有帮助的：

1. 我就知道这个活动会失败！
2. 之前分析报告已经写了，成功率80%，我们果然成功了

对于这个误区，Howard备忘录中有三句话总结的很好：

>Risk means more things can happen than will happen.
>
>风险意味着可能发生的事总是多于确定发生的事

在评估业务风险时应该冷静的多想一想有哪些风险，将业务之外的东西也考虑进去。

某家公司曾经通过QQ群发现有人在卖自己网站的用户账号，但是风控系统显示最近撞库并没有异常，通过风控团队和用户团队的配合，发现用户登录量少于风控记录到的登录量。为什么有些用户登录没有进行风控判断呢？排查后发现：当系统判断到用户在请求接口https://example.com/login时会调用风控，黑产通过请求 //login(两个/)绕开了这个判断逻辑，且依然可以访问登录接口(HTTP路径中/和//指向的地址是一样的)。

类似的案例表明风险有时来自于我们很难想到的地方，我们总显得比黑产“笨”一些。所以在风险评估时，应该尽可能从多方面想想，必要时应假设我们的策略失败了，并设计兜底方案。

>Even though many things can happen, only one will.
>
>即便一件事有很多可能性，但最终只有一种会发生

>Knowing the probabilities doesn’t mean you know what’s going to happen.
>
>知道发生的概率不意味着你知道接下来会发生什么

（未完待续）


参考文献：

[《Risk Management: History, Definition and Critique》(Georges Dionne)](https://www.cirrelt.ca/DocumentsTravail/CIRRELT-2013-17.pdf)

[《Risk Revisited》(Howard Marks)](https://www.oaktreecapital.com/docs/default-source/memos/2014-09-03-risk-revisited.pdf)
