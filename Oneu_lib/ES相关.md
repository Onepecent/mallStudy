官方文档：https://www.elastic.co/guide/cn/elasticsearch/guide/current/foreword_id.html

# 序言

介绍了作者与Zach和Clint的不解之缘与ES的关系

# 前言

Elasticsearch 是一个分布式、可扩展、实时的搜索与数据分析`引擎`。它能从项目一开始就赋予你的数据以搜索、分析和探索的能力，这是通常没有预料到的。 它存在还因为原始数据如果只是躺在磁盘里面根本就毫无用处。

## 为什么我们要写这本书

 （个人认为这里解释了书本真正面向的对象）

我们写这本书，因为 Elasticsearch 需要更好的阐述。 现有的参考文档是优秀的 — 前提是你知道你在寻找什么。它假定你已经熟悉信息检索、分布式系统原理、Query DSL 和许多其他相关的概念。

这本书没有这样的假设。它的目的是写一本即便是什么都不懂的初学者（不管是对于搜索还是对于分布式系统）也能拿起它简单看完几章，就能开始搭建一个原型。

我们采取一种基于问题求解的方式：这是一个问题，我该怎么解决？ 如何对候选方案进行权衡取舍？我们从基础知识开始，循序渐进，每一章都建立在前一章之上，同时提供必要的实用案例和理论解释。

现有的参考文档解决了 *如何* 使用这些功能，我们希望这本书解决的是 *为什么* 和 *什么时候* 使用这些功能。

## 如何读这本书（importance）

Elasticsearch 做了很多努力和尝试来让复杂的事情变得简单，很大程度上来说 Elasticsearch 的成功来源于此。 换句话说，搜索以及分布式系统是非常复杂的，不过为了充分利用 Elasticsearch，迟早你也需要掌握它们。

恩，是有点复杂，但不是魔法。我们倾向于认为复杂系统如同神奇的黑盒子，能响应外部的咒语，但是通常里面的工作逻辑很简单。 理解了这些逻辑过程你就能驱散魔法，理解内在能够让你更加明确和清晰，而不是寄托于黑盒子做你想要做的。

这本权威指南不仅会帮助你学习 Elasticsearch，而且希望能够带你接触一些更深入、更有趣的话题，如 [*集群内的原理*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/distributed-cluster.html) 、 [*分布式文档存储*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/distributed-docs.html) 、 [*执行分布式检索*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/distributed-search.html) 和 [*分片内部原理*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/inside-a-shard.html) ，这些虽然不是必要的阅读却能让你深入理解其内在机制。

本书的第一部分应该按章节顺序阅读，因为每一章建立在上一章的基础上（尽管你也可以浏览刚才提到的章节）。 后续各章节如 [*近似匹配*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/proximity-matching.html) 和 [*部分匹配*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/partial-matching.html) 相对独立，你可以按需选择性参阅。

## 本书导航

这本书分为七个部分：

- 章节 [*你知道的, 为了搜索…*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/intro.html) 到 [*分片内部原理*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/inside-a-shard.html) 主要是介绍 Elasticsearch。介绍了 Elasticsearch 的数据输入输出以及 Elasticsearch 如何处理你的文档数据。 如何进行基本的搜索操作和管理你的索引。 本章结束你将学会如何将 Elasticsearch 集成到你的应用程序中。 章节：[*集群内的原理*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/distributed-cluster.html)、[*分布式文档存储*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/distributed-docs.html)、 [*执行分布式检索*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/distributed-search.html) 和 [*分片内部原理*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/inside-a-shard.html) 为附加章节，目的是让你了解分布式处理的过程，不是必读的。

- 章节 [*结构化搜索*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/structured-search.html) 到 [*控制相关度*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/controlling-relevance.html) 带你深入了解搜索，如何借助一些更高级的特性，如邻近词（word proximity）和部分匹配（partial matching）来索引和查询你的数据。你将了解相关度评分是如何工作的以及如何控制它来确保第一页总是返回最佳的搜索结果。

- 章节 [*开始处理各种语言*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/language-intro.html) 到 [*拼写错误*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/fuzzy-matching.html) 解决如何有效使用分析器和查询来处理人类语言的棘手问题。我们会从一次简单的语言分析下手，然后逐步深入，如字母表和排序，还会涉及到词干提取、停用词、同义词和模糊匹配。

- 章节 [*高阶概念*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/aggs-high-level.html) 到 [*Doc Values and Fielddata*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/docvalues-and-fielddata.html) 讨论聚合（aggregations）和分析，对你的数据进行摘要化和分组来呈现总体趋势。

- 章节 [*地理坐标点*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/geopoints.html) 到 [*地理形状*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/geo-shapes.html) 介绍 Elasticsearch 支持的两种地理位置检索方式：经纬坐标点和复杂的地理形状（geo-shapes）。

- 章节 [*关联关系处理*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/relations.html) 到 [*扩容设计*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/scale.html) 谈到了为了高效使用 Elasticsearch，应当如何为你的数据建立模型。在搜索引擎里表达实体间的关系可能不是那么容易，因为它不是用来设计做这个的。这些章节还会阐述如何设计索引来匹配你系统中的数据流。

- 最后，章节 [*监控*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/cluster-admin.html) 到 [*部署后*](https://www.elastic.co/guide/cn/elasticsearch/guide/current/post_deploy.html) 将讨论生产环境上线的重要配置、监控点以及如何诊断以避免出现问题。

  

# 基础入门

*Elasticsearch* 是一个实时的分布式搜索分析引擎，它能让你以前所未有的速度和规模，去探索你的数据。 它被用作全文检索、结构化搜索、分析以及这三个功能的组合。

Elasticsearch 鼓励你去探索与利用数据，而不是因为查询数据太困难，就让它们烂在数据仓库里面。

## 安装并运行 Elasticsearch

想用最简单的方式去理解 Elasticsearch 能为你做什么，那就是使用它了，让我们开始吧！

安装 Elasticsearch 之前，你需要先安装一个较新的版本的 Java，最好的选择是，你可以从 [*www.java.com*](http://www.java.com/) 获得官方提供的最新版本的 Java。之后，你可以从 elastic 的官网 [*elastic.co/downloads/elasticsearch*](https://www.elastic.co/downloads/elasticsearch) 获取最新版本的 Elasticsearch。