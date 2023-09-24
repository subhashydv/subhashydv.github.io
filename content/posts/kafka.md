---
title: "Intro to Kafka"
date: 2023-09-17T20:26:12+05:30
draft: false

tags: 
  - Tech
  - Tutorial

categories: ["Tech", "Tutorial"]

description: A tool that allows devs to play with distributed system
thumbnail: "/images/kafka.png"
image: "/images/kafka.png"
---

<!-- ![img](/images/kafka.png) -->

<!-- # INTRO TO KAFKA -->

In this blog I will try to answer few question that we might have as a beginner. So let's start with our first question :   

### What is kafka?

So let's think kafka as a central hub that allows someone to host and consume the live data (stream). In kafka's term the host and consumer will be called producer and consumer respectively. There can be multiple producer and consumer to it.

#### Producer : 
An application that sends the data (messages) to kafka server.

#### Consumer : 
An application that reads the message from kafka server that has been sent by producer and process them.

![basic kafka](/images/basic_kafka.png)

As we can see the above picture, there are few producer and consumer to kafka. All the producer will keep sending the messages to kafka and consumer will keep reading them from kafka. But as we can see there are more than one producer and same with consumer so how are we going to identify our message at consumer level? Won't there be any conflict with messages? The answer to it is yes and kafka solves it by using **topic**.

### Topic : 
Topics are used to differentiate the events stored in kafka. Topics are like folder in a file system where only events related to the folder are stored for example user-data, invoices etc.

*Similar to Topic there are few more terms that get used in kafka. So lets get familiar with those first* : 

### Event : 
The messages that are produced to or consumed from the Kafka broker are called events. These messages are stored in the form of bytes in the broker’s disk storage. These messages can have any format. The common format is Json and Avro.

### Broker : 
A Broker is a server which has Kafka running on it and is responsible for the communication between multiple services. Multiple brokers will form a Kafka cluster. Kafka maintains multiple broker because of three main reason : speed, durability and scalability. The recommended minimum default broker is 3 in kafka cluster.

### Partition : 
A topic can be further divided into partitions in order to attain higher throughput. It is the smallest storage unit which holds a subset of data of a topic. In simple terms we create partitions to distribute the load on a topic.

![Topic Partition](/images/partition.png)

### Replication Factor : 
Replica of a partition is a backup for the partition. The replication factor of a topic decides that how many replicas of a partition in that topic should be maintained by the Kafka cluster. A topic with partition as 1 and replication factor as 2 would mean that two copies of the same partition with same data would be stored in the Kafka cluster.

### Offset :
When producer publish the message to the kafka each message get assigned a index. When consumer consume the message the index of that message get stored in kafka. This index helps kafka to keep track of which events have already been consumed by the consumer. In kafka's term this index is called offset.

### Zookeeper : 
 Zookeeper is an extra service present in the Kafka cluster that basically maintain metadata information. for example it keeps track of which brokers are part of the Kafka cluster. It is used by Kafka brokers to determine which broker is the leader of a given partition and topic and perform leader elections. Some default config are as follows : 

 ```
 dataDir=../tmp/zookeeper
 clientPort=2181
 ```


 ## Message Flow

As we have seen some basic term for kafka. Lets have a look on how a message will flow from producer to consumer. 

![flow diagram](/images/flow.gif)

As we can see in the above diagram there is 1 producer and 1 consumer to kafka. We have created a topic called *ORDER*. So the producer will be sending the event on a topic called ORDER and consumer will ask for all those event constantly. As we know kafka will maintain the offset for all the event so kafka will provide event in same order as they have received. To note down here kafka won't be pushing the message until consumer asks for it. After receiving the message by consumer it process the message.


### Some Common Q & A

**Q.1**  Does kafka works as a database as well?\
**Ans** Yes, Kafka works like a database system but it won't allow you all the capability that database has. And off course your data won't be available after retention period(that you defines in configuration) or size.

**Q.2** Does kafka push the event to consumer?\
**Ans** No, consumer polls on the kafka for unconsumed event.

**Q.3** How does kafka know that the event reached successfully on consumer?\
**Ans** Consumer acknowledge to kafka after reading the event successfully. After acknowledgement only kafka increase the offset.

 *This is all about the Basics of Kafka. will see you in next tutorial* :)