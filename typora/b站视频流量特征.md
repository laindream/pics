## b站视频流量特征

视频流量被分成大小为1500左右的tcp包

![image-20210204120550626](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204120550626.png)



视频流量ipv4与ipv6混杂

不同机器ipv4流量对比

![image-20210204123600582](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204123600582.png)



ipv6流量

![image-20210204123642185](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204123642185.png)



#### 过滤方案1(性能开销小)

中间视频包头部除必要信息外无其他特征,但tcp payload大小均在1430-1460之间(目前所知,或许范围更大一点)

![image-20210204122226749](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204122226749.png)



使用该字段过滤基本可以过滤所有视频流量包

![image-20210204124027727](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204124027727.png)



#### 过滤方案2(有性能开销,较准确)

可以抓取握手包知道准确tcp.len

![image-20210204130630725](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204130630725.png)

查看握手包tcp.len

![image-20210204130752960](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204130752960.png)

准确过滤

![image-20210204130842532](https://cdn.jsdelivr.net/gh/laindream/pics/typora/image-20210204130842532.png)