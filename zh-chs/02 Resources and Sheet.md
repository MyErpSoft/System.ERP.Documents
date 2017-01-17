# 资源与账
## 简介
现在我们已经知道，管理软件首要管理的资源，那么企业通常有哪些资源呢？  
最常见的就是钱，比如你可以说这个企业现在有1,000,000人民币，其中200,000万的现金以及800,000万的银行存款。还有一种常见的是物料，例如A仓库里面有10,000瓶X牌可乐成品，还有20吨的X牌可乐原浆，这些资源我们可以使用数量来衡量他的量。  
有些种类的资源具有时间的敏感性，例如加工机床，我们在评估这个资源时，不仅关心它有几台机床，还关心这些机床在今天能够提供多少小时的加工服务。  
在软件设计中，我们使用账来记录这些资源的变动情况，并通过此查询到某个时间点这些资源的量。下面我们将逐一介绍帐处理的各个要素。 
## 账的要素 
### 数量
数量是评估资源的基础，在发生变动时，我们使用数量描述变动的量，例如卖了3瓶X牌可乐，这里的3就是数量。在查询某个时间点的资源的量时，也使用数量，例如当前我的库存有100瓶X牌可乐。数量是一个数字，因此他是可以计算的，例如我可以将这个月的所有销售的X牌可乐的数量进行累加，得到这个月的销售数量。  
但是，不是数量之间都可以计算的，这个计算是有前提的，例如你不能将3瓶的瓶装X牌可乐与散装的1吨原料进行累加，也不能将100元人民币与200美元进行累加。
### 单位
数量一定与单位关联，你必须说3`瓶`可乐，或者100`元`人民币，或者3.25千克的猪肉。但在实践中，我们将单位与具体的资源项强关联，意思是我们在X牌可乐这个物料资源中，明确指明唯一单位是`瓶`，在X牌可乐原浆中明确指明单位是`吨`，人民币这个资源的唯一单位就是`元`。这样我们就不必在任何单据或账中指明单位了。  
那么如果存在12瓶组合的箱包装呢？同样基于设计的便利，我们会建议建立另外一个物料`12瓶组合装X牌可乐`，其唯一的单位是箱。当然他们存在一定的转换关系，这个在后续的文章中会讨论。  
> 问题：现实中人民币有元、角和分，我们需要建立3笔不同的记录吗？毛里塔尼亚的货币单位不是十进制，而是规定1乌吉亚等于5考姆斯，那么需要建立两笔记录吗？  
### 精度
在记录资源变动的数量时，我们还会限制精度，例如X牌可乐，我们无论如何都只允许整数，不会卖2.5瓶可乐。但是猪肉我们却可以卖3.25千克，他的精度是2位。在实践中，精度同样与特定的资源项关联，这样当销售X牌可乐时，自然就限定了只能例如整数。  
有些软件，会设计精度与不同的活动也有关，例如在财务统计中，人民币可能会精确到小数4位，但在销售活动中，销售金额就只能到分，甚至大宗交易到元，但这不影响最终帐的帐的精度，他们使用需要小于或等于最小记账精度，但我个人认为把事情复杂化了。  
## 主资料