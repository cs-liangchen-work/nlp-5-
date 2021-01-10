### 代码框架借鉴其他代码：
文本处理成列表（lower，split，Tokenizer） +  torchtest对数据封装  +  搭建模型  +  train && dev && test
### 词向量：
使用300d的glove词向量，unk，pad均使用其中自带的。
### 数据处理：
lower 和 Tokenizer把符号分开。
label处理：- 认为作为无关（neutral）的处理比较合理，
### 模型：
在模型搭建时，linear，bilstm等中都设置了，
自己测试原始模型：\n
test_accuracy 0.896800  dev_accuracy 0.895100

尝试再增加一个卷积核，结果基本没有提升。（结果未保存）

尝试在动态词向量后添加一个bilstm，（hidden//2,保障和静态深度相同）
dev_accuracy 0.906250  test_accuracy 0.907000
