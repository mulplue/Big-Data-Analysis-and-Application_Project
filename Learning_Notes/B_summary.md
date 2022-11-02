## 大作业的框架

#### 数据预处理

```python
df.info()
df.head()
```

- 查看下数据信息

  删除第一列、列名错误的纠正

- 时间处理

  按年、月、日、周几、一年中的第几天处理下

  按照季节处理，数据采集自南美洲的许多国家，以巴西为例，推测事故发生和季节有关，按照月份分季节，

- NLP处理

  通过观察`Description`列中的文字来定义 `handmade-stopwords list`

  预处理函数（比较复杂还需了解）

  调用API，情绪分析，

  ```python
  SentimentIntensityAnalyzer()..polarity_scores(text)
  ```

  传回neg, neu, pos, compound

#### EDA数据探索性分析

对每个特征变量进行单独分析

多变量分析

NLP分析

#### 特征工程

##### [TF-IDF算法](https://blog.csdn.net/asialee_bird/article/details/81486700)

 **TF-IDF（term frequency–inverse document frequency，词频-逆向文件频率）**是一种用于信息检索（information retrieval）与文本挖掘（text mining）的常用**加权技术**。

==**字词的重要性随着它在文件中出现的次数成正比增加，但同时会随着它在语料库中出现的频率成反比下降**==

TF-IDF的==主要思想==是：如果某个单词在一篇文章中出现的频率TF高，并且在其他文章中很少出现，则认为此词或者短语具有很好的类别区分能力，适合用来分类。

==不足==

（1）没有考虑特征词的位置因素对文本的区分度，词条出现在文档的不同位置时，对区分度的贡献大小是不一样的。

（2）按照传统TF-IDF，往往一些生僻词的IDF(反文档频率)会比较高、因此这些生僻词常会被误认为是文档关键词。

（3）传统TF-IDF中的IDF部分只考虑了特征词与它出现的文本数之间的关系，而忽略了特征项在一个类别中不同的类别间的分布情况。

（4）对于文档中出现次数较少的重要人名、地名信息提取效果不佳。

##### 标签编码

直接编码（例子采用）或者独热编码等等

#### 建模

分类任务

[如何解决NLP分类任务的11个关键问题](https://zhuanlan.zhihu.com/p/183852900)

- ==类别不平衡==处理（[长尾分布学习处理](https://www.zhihu.com/question/372186043/answer/1393735908)）
  - **重采样**：对少样本的过采样，或是对多样本的欠采样，容易信息丢失，过拟合
  - **数据合成**：
    - 对少类样本加随机高斯噪声，做data smoothing
    - SMOTE
  - **重加权**：重加权不同类别的loss
    - 按照类别数目的倒数来做加权
    - 按照“有效”样本数加权
    - 根据样本数优化分类间距的loss加权
  - **阀值调整**
  - **模型融合**
  - **迁移学习（transfer learning）**：这类方法的基本思路是对多类样本和少类样本分别建模，将学到的多类样本的信息/表示/知识迁移给少类别使用。

事故等级

数据列`Accident Level`作为输出标签

潜在事故等级

数据列`Potential Accident Level`作为输出标签

lgb--------GBDT

[lgb调参](https://blog.csdn.net/u012735708/article/details/83749703)

[lgb原理理解](https://zhuanlan.zhihu.com/p/99069186)

==[GBDT](https://zhuanlan.zhihu.com/p/144855223)==

- 集成模型

  - Baggle，e.g.随机森林

    回归类任务:  预测值平均一下

    分类任务: 投票

  - stacking

    Stacking模型比bagging模型更进2步

    (a) 允许使用不同类型的模型作为base model

    (b) 使用一个机器学习模型(元模型)把所有base model的输出汇总起来，形成最终的输出

    Stacking模型认为，各个基础模型的能力不一，投票的时候不能给以相同的权重，而需要用一个“元模型”对各个基础模型的预测值进行加权

  - boosting

    把基础模型组合起来——串联

    第K个CART拟合前k-1个CART留下的残差，从而不断的缩小整个模型的误差

- CART回归树

- GBDT

[shap黑盒模型解释](https://zhuanlan.zhihu.com/p/106320452)



#### 结论









**Critical Risk**: some description of the risk involved in the accident

<b>Description</b> : Detailed description of how the accident happened

这两个部分需要自然语言处理



