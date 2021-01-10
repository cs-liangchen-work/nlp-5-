### 代码框架借鉴其他代码：
文本处理成列表（lower，split，Tokenizer） +  torchtest对数据封装  +  搭建模型  +  train && dev && test
### 词向量：
使用300d的glove词向量，unk，pad均使用其中自带的。
最初用50d的进行训练，300d的效果明显优于50d的。但训练20轮左右模型train_accuracy就98%甚至更高了。
### 模型参数：
直接使用原论文中的模型参数。
### 数据处理：
lower 和 Tokenizer把符号分开。
自己在进行测试的时候将dev中选出5000句作为test。
### 尝试修改及效果：
自己测试原始模型：
test_accuracy 0.896800  dev_accuracy 0.895100

尝试再增加一个卷积核，结果基本没有提升。（结果未保存）

尝试在动态词向量后添加一个bilstm，（hidden//2,保障和静态深度相同）
dev_accuracy 0.906250  test_accuracy 0.907000
