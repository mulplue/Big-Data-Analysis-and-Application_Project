# Final Project


6min / ren
## Presentation

- 20min

### 1 Background 1

- 工业事故

==C==

### 2 Motivation 1

- 希望从事故的一些数据中解析出信息，指导之后的工业生产安全问题

==C==

### 3 Problem definition 1

- 数据集来源
- 数据集简介

==C==

2-3min


### 4 主线

#### Part 1：数据预处理与NLP

- 划分：客观属性+文本
- 客观属性--预处理
- 文本--NLP

| 客观属性 | 文本 |
| -------- | ---- |

2

| 客观属性 | 事故等级 | 事故类别 |
| -------- | -------- | -------- |

==A: NLP之外的EDA
B: NLP预处理==

#### Part 2：数据解析

客观原因EDA

- 客观属性

==A==

NLP词元分析

- 事故类别

==B==

#### Part 3：数据应用

- 目标：减少损失的期望

- 如何定义损失？
  $$
  \huge loss=f(事故等级，该等级事故发生概率)
  $$

- 给数据加入损失列，进行分析

| ￼￼￼￼￼￼ 客观属性 | 事故等级 | 事故类别 |
| --------------- | -------- | -------- |

2

| 客观属性 | 事故等级 | 事故类别 | 损失 |
| -------- | -------- | -------- | ---- |



双项

- 损失--事故类别
- 损失--客观属性


- 画时序-损失函数图
- 损失函数--区间划分
- 事故类别/客观原因--损失函数多分类模型
- SVM、SGBoost多分类模型


## 总结

- 原因分析
- 建议






## C

- 画时序-损失函数图
- 损失函数--区间划分
- 事故类别/客观原因--损失函数多分类模型
- SVM、SGBoost多分类模型