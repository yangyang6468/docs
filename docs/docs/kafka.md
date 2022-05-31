## kafka概念:

kafak是一种高吞吐量的分布式发布订阅消息系统

## kafka的特性:

1.高吞吐量、低延迟 : 每秒数据处理几十万

2.可拓展性：支持集群拓展

3.持久性、可靠性：数据持久化到磁盘，并支持数据备份防止丢失

4.容错性：允许集群中节点失败

5.高并发：支持数千客户端同时读写

## 基本概念：

Producer : 消息和数据的生产者

Consumer : 消息和数据的消费者

Consumer Group : 消费同一个topic的consumer的一个集合

Broker : Kafka集群中对应的每个kafka节点，一个服务器的实例就是一个broker

Topic : 消息的种类

Partition : kafka下数据存储的基本单元，一个topic数据会被存储到多个parttiion，每一个partition        

 上的数据都是有序的(同一个topic下的不同partition之间是没有主次之分，都是同等重

 要且存储不同数据的)。

Replication: 副本集；是Kafka高可用的一种保障机制(leader follower）

leader: 每个partition中有且只有一个replica可以作为leader (负责处理所有的Producer和

Consumer的请求 ， 还负责监管和维护ISR（副本同步队列）中所有的follower的滞

   后状态)

follower:每个partition中除leader以外的所有replica均为follower(只处理数据同步）

详细解释：有一个Topic，分区(partitions)数为3(分别为a, b, c)，副本因子(replication-factor)

  数也为3；其本质就是该Topic一共有3个a分区，3个b分区，3个c分区。这样的设

  计在某种意义上就很大程度的提高了系统的容错率。

延伸问题：一个Topic下a分区一共有三个，既然是副本集，那这三个所包含的数据都

  完全一样吗？作用都一样吗？

 

## kafka分区的规则：

## 1.所有的replica要尽可能的平均分配到集群中的每一台broker上

​    2.尽可能保证同一个partition的leader和follower分在不同的broker上

​    3.如果集群跨机架，尽可能的保证每个partition的replica分配到不同的机架上

 ![clip_image002](.\assets\clip_image002.gif)

## 发送流程：

![clipboard.png](.\assets\clip_image004.gif)

producer采用push进行模式将消息发布到Broker，每条消息将append到partition中，属于顺序写磁盘。Producer会将消息发送到到broker时候，会根据分区算法将其存储到哪一个partition。

#### 数据存入到partition的具体流程：

  1.Producer先从zk中找到partition的leader。

  2.producer将数据发送给leader。

  3.leader将消息写入本地log。

  4.followers从leaderpull消息，写入本地log向leader发送ack。

  5.leader收到所有的ISR中的replicas的cas后，增加HW，并像producer发送ack。

#### Kafak集群处理流程：

   接收到producer发送过来的消息，将其持久化到硬盘，并保留消息指定时长。物理上将Topic分为多个partition,每个partition物理上对应一个文件夹（文件夹存储改partition的所有消息和索引文件）

#### 消费者消费数据流程：

 从kafak集群pull数据，并控制获取消息的offset.至于消费的进度，可手动或者自动提交给kafak集群。pull模式可以自主控制消费的速率，同时Consumer可以控制消费方式，可批量消费也可以逐条消费。同时还能选择不同的提交方式。一个消息只能被group内的一个comsumer所消费，且consumer消费消息时不关注offset,最后一个offset有zk保存。下次消费时，该group中的Consumer将从offset记录的位置开始消费。

注意：1.如果消费线程大于Partition数量，有些线程将收不到消息。

  2.如果partition数量大于消费线程数，那么一个线程将会接收多个partition的消息。

  3.如果一个消费线程消费多个partition，则无法保证你接受到消息的顺序，而一个partition内的消息是有序的。

![clipboard.png](.\assets\clip_image006.gif)

简单操作指令：

启动kafka服务

![clipboard.png](.\assets\clip_image008.gif)

 

![clipboard.png](.\assets\clip_image010.gif)

新建topic

![clipboard.png](.\assets\clip_image012.gif)

查看topic列表

![clipboard.png](.\assets\clip_image014.gif)

 topic描述具体

![clipboard.png](.\assets\clip_image016.gif)

 

发布订阅消息

![clipboard.png](.\assets\clip_image018.gif)

收到订阅消息

![clipboard.png](.\assets\clip_image020.gif)

## kafka与python的相关操作解读：

https://cloud.tencent.com/developer/news/202116

 