### 1.把之前写的代码转换为Paddle实现，代码放到了notebook
### 2.在这次比赛中，感觉对我提分最大的trick是使用了二次训练的方法，帮助我直接从50分到70分：
+ 1）首先使用lr=1e-4的Adam优化器训练10个epoch，保存模型参数
+ 2）然后使用lr=5e-5的Adam优化器在第一次训练的基础上继续训练3个epoch
#### 训练记录：
+ 在不断调参的过程中，我一开始固定第一次训练epoch为5个epoch，逐渐增大第二次训练的epoch至20~25轮左右，分数逐渐升高然后没有太大变化
+ 接下来我又不断调小第二次训练的学习率，也会有提高
+ 当第二次训练的epoch和lr调整完之后，我又尝试降低第一次训练的lr，从5e-4到1e-4，发现1e-4得分最高
+ 最后我又尝试在第一次训练的epoch做文章，发现第一次训练epoch从5轮增大到15轮，模型分数也会逐渐提升，不过提交时间已经到了，继续增大epoch或者把gru单元换成lstm等也许还有提升的空间

