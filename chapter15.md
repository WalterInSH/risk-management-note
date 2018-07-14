# 从金融角度聊聊业务风险

我们已经聊了很多做业务风控的手段和技术，可是到现在还没有说清楚“风险控制”中的“风险”是什么。

我一直在想应该从什么角度来写这个问题，最终我决定从金融行业借鉴一些内容。这个行业已经花了几十年研究风险，我们看看这个行业会带给我们什么启示。

橡树资本联合创始人Howard Marks在几篇备忘录中阐述了他对风险的看法，下面就围绕他写过的内容聊一聊。

### 风险来自不确定性

简单来说，金融投资行业就是今天花一笔钱在一件事情上，未来获得一个结果。有难度的部分是：站在现在，很难说未来的结果是好是坏。

其实投资不是金融行业特有的行为，普通公司、每个人的生活都充满了投资，做一次广告活动、报考大学都是投资，都是花一笔钱或者几年时间在一件事上，未来获得一个结果。同样难的是：站在现在，很难说未来的结果是好是坏。

那么我们站在现在，该用什么眼光看到未来的结果呢？

>The future should be viewed not as a fixed outcome that’s destined to happen and capable of being predicted, but as a range of possibilities and, hopefully on the basis of insight into their respective likelihoods, as a probability distribution.
>
>未来不应被视为一个注定发生、可被预测的结果，而应被视为一个可能性区间，寄希望于对各个可能性的洞悉，未来可以被看做一个概率分布。

拿金融投资来说，花几百万买了一家公司的股票。未来能不能盈利是不能预测的，结果可能是亏损、回本、盈利（当然你可以拆分的更细），每一种结果都有一个可能性区间。当你认真研究基本面后，在加上一些主观直觉，你就得到了一个概率分布。例如：90%的概率会盈利，5%的概率会亏损，还有5%概率不亏不赚。

考大学和金融投资类似，花几万学费和很长时间在大学的某个专业学习，几年后毕业的时候也会有很多结果。对于刚高考完的学生而言是无法预测的。我们站在2018年回首，即便同样是计算机专业的毕业生、同样的学校、同样的努力，毕业于14年和16年的两批学生面临的互联网就业环境是完全不一样的。

这和风险有什么关系呢？

>This uncertainty as to which of the possibilities will occur is the source of risk in investing.
>
>哪种可能会真正发生的不确定性，是投资风险的来源。

也就是说金融投资的风险来自于亏本还是盈利的不确定性，读大学的风险来自于最后是进BAT还是去搬砖的不确定性。

基于"风险来自不确定性"，Howard Marks延伸出了几个很有意义的关键点。

>Risk means more things can happen than will happen.
>
>风险意味着可能发生的事总是多于确定发生的事

在评估业务风险时，除了那些大概率会发生的事情，还有更多小概率发生的事，有时那些负面的小概率事件才是风险的来源。所以事前评估风险时应该冷静、开放的思考各个方面，包括小概率事件，甚至将业务逻辑之外的东西也考虑进去。

某家公司曾经通过QQ群发现有人在卖自己网站的用户账号，但是风控系统显示最近撞库并没有异常，通过风控团队和用户团队的配合，发现用户登录量少于风控记录到的登录量。为什么有些用户登录没有进行风控判断呢？排查后发现：当系统判断到用户在请求接口https://example.com/login时会调用风控，黑产通过请求 //login(两个/)绕开了这个判断逻辑，且依然可以访问登录接口(HTTP路径中/和//指向的地址是一样的)。

类似的案例表明风险有时来自于我们很难想到的地方，我们总显得比黑产“笨”一些。所以在风险评估时，应该尽可能从多方面想想，必要时应假设我们的策略失败了，并设计兜底方案。

>Knowing the probabilities doesn’t mean you know what’s going to happen.
>
>知道发生的概率不意味着你知道接下来会发生什么

就像扔骰子，我们都知道扔一次每个面的概率是1/6，但是我们却无法准确预测某一次扔出的结果。即便我们通过分析，得出风险很低(或者很高)，也不意味着未来真的是这样。

>Even though many things can happen, only one will.
>
>即便一件事有很多可能性，但最终只有一种会发生

在很多时候我们当然可以用均值作为判断，但是我们要谨记的是即便均值是一个很好的结果，某一次结果仍然有可能很差，甚至超过我们的承受能力。

>I have no interest in being a skydiver who’s successful 95% of the time.
>
>我没有兴趣成为一个成功率有95%的跳伞运动员

也是因为最后只有一个结果会发生，我们有时会进入一个误区：事后去评估事前发生的风险时，大大低估那些最后没发生的可能结果的概率。下面这些想法你也许听说过：

1. 我就知道这个活动会失败！
2. 之前分析报告已经写了，成功率80%，我们果然成功了

### 风险的定义

我们说清了风险的来源，接着看看Howard Marks给风险的定义是什么：

>The possibility of permanent loss. A downward fluctuation – which by definition is temporary – doesn’t present a big problem if the investor is able to hold on and come out the other side.
>
>风险就是发生永久性损失的概率。一个暂时的向下波动并不是一个大问题，只要投资者可以承受，且之后可以翻盘。

业务方投入资源(包括时间和经费)去做拉新、促销，是为了获取回报，也就是更多用户、更多订单，当然说到底都是为了利润。对应Howard Marks给出的定义，业务方面临的永久性损失是什么？

一家成熟公司投入了10万元进行了一次为期1个月的促销活动，最后只多带来了1万元收入
1. 那么差值（9万元）是永久性损失吗？
2. 后一个季度公司盈利了9万元，是不是意味着公司只是经历了一次“向下波动”，并没有风险？

（未完待续）


参考文献：

[《Risk Management: History, Definition and Critique》(Georges Dionne)](https://www.cirrelt.ca/DocumentsTravail/CIRRELT-2013-17.pdf)

[《Risk Revisited》(Howard Marks)](https://www.oaktreecapital.com/docs/default-source/memos/2014-09-03-risk-revisited.pdf)

致谢：

感谢上海工程技术大学翻译专业的Cecilia对本章内容的帮助。
