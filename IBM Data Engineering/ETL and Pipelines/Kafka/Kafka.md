[[Kafka]]

### Distributed event streaming platforms components

What is an event? An event describes the entity's observable state updates over time 
- GPS coordinates of a car
- Temperature of a room
- Blood pressure of a patient
- RAM usage of an application


Common event formats: 

- Primitive like "hello" , a key-value pair, key-value with a time stamp.
- Event source: Event streaming from one event source to one destination
	- Event Source: Sensors, devices, databases, applications. 
	- Event Destination: File system, databases, applications

![[Pasted image 20260819003845.png|607]]

![[Pasted image 20260819004022.png|606]]

![[Pasted image 20260819004052.png|609]]

### **Popular ESP solutions**
- Apache Kakfa
- Amazon Kinesis
- Apache Flink
- IBM Event Stream
- Azure Event Hub
---

**Apache Kafka Common Use Cases**

![[Pasted image 20260819162320.png|634]]

![[Pasted image 20260819162622.png|640]]

Mian features Apache Kafka:

- Distribution system 
- Highly scalable
- Highly reliable
- Permanent persistency 
- Open source 
![[Pasted image 20260819184521.png|465]]

- Tuning Kafka is demanding and requires professional assistance, however there are some on demand services for this: 
	- Confluent Cloud
	- IBM Event Streams
	- Amazon MSK

---
### Building Event Streaming Pipelines using Kafka 

A Kafka cluster contains one or many brokers as a dedicated server to receive, store, process, and distribute events. 
Brokers are synchronized controllers and use kRaft controller nodes that use the consensus rotocol to manage the Kafka metada logs that contains information about each change to the cluster metadata. 

![[Pasted image 20260819224002.png|504]]

- You can think of a topic as a database to store specific types of events. 

- Partition and replication to increase fault tolerance and throughput 

### Kafka topic CLI 

![[Pasted image 20260819224504.png|553]]

Kafka producers

- Client application that publish events to topic partition
- An even can be optionally associated with a key 
- Events associated with the same key will not be published to the same topic partition
- Events not associated with any key will be published to topic partitions in rotations.

![[Pasted image 20260819225332.png|572]]

Kafka producer CLI

![[Pasted image 20260819225437.png|574]]

Kafka Consumer
- Clients subscribed to topics 
- Consume data in the same order
- Store an offset record for each partition
- Can read all events from the begining again by resetting the offset to zero 

![[Pasted image 20260819235131.png|573]]


Kafka Consumer CLI


![[Pasted image 20260819235256.png|578]]

![[Pasted image 20260819235432.png|578]]

--- 

Kafka Stream Process

