## *Deep Content*: Unveiling Video Streaming Content From Encrypted WiFi Traffic

#### 解决问题

被动嗅探WiFi帧监听加密流量来识别视频流(即使不连接WiFi网络)(传输层（TLS）和MAC层（WPA2）)

将模型与最新的基于卷积神经网络（CNNs）的有线流量分类器进行了比较，在获得相似结果的同时，所需的计算能力和时间大约减少了三倍



#### 实现方法

基于DASH streaming特点

##### ![image-20210201170521741](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210201170521741.png)



实现了三种神经网络结构：卷积神经网络（CNN）、递归神经网络（RNN）和多层感知器（MLP）

训练集和测试集比率:80%和20%



CNN模型适用于无线环境，但比MLP的架构需要更多的计算资源(MLP模型的训练速度至少是CNN模型的三倍)



#### MLP部分

MLP结构

![image-20210201172141676](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210201172141676.png)

视频流被表示为一个500×1的阵列输入到MLP模型，只选择一个特征。

结果表明，具有500×1输入（即仅选择一个特征）和2个隐藏层的MLP结构可以提供优异的性能



