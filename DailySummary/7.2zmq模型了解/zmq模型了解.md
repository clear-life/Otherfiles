### zmq模型了解

##### zmq主要有四种模型：

1. 一对一模型(**Exclusive-Pair**)

   ​	只能一对一连接，但**数据双向流动**

2. 请求回应模型(**Request-Reply**)

   ​	一对多连接，client发起请求，server响应请求

3. 发布订阅模型(**Publish-Subscribe**)

   1. Publish端单向发布数据
   2. Subscribe只有在连接进来时才能收到信息
   3. Subscribe只能接收，不能反馈

4. 管道模型(**Push-Pull**)

   1. 从Push端单方面向Pull端推送数据流

   2. Push做出**负载均衡**，保证Pull端正确收到消息

   3. 用于多任务并行

      

##### 四种模型在程序中的区分	

​	四种模型的差别体现在socket，创建socket时会根据type参数确定模型

**函数原型**

```
void *zmq_socket(void *context, int type);
```



#### 学习总结：

1. ​	zmq：由于时间关系，今天并没有继续深入学习zmq，只是简单了解一下四种模型和官网的教程中的basics部分
2. ​	算法：学完函数部分



#### 明天规划：

1. ​	zmq：继续了解请求回应模型的详细过程和细节
2. ​	算法：总结字符串部分的函数