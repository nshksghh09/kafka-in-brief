# kafka-in-brief
## Date: Mar 18 2025 (Tue) 
🚀 Below are the things that I learnt in KAFKA
- What is the need of Kafka
- What is  Kafka
- The architecture of Kafka
- Consumer Groups
- Kafka data flow

 ### What is the need of Kafka?
 - Apache Kafka is essential in modern data architectures because it enables real-time data streaming, scalability, and fault tolerance. It serves as a ***distributed messaging system*** designed to handle ***high-throughput and low-latency*** event processing.
 - It prevents the crashing of databases such as postgres and sql from crashing due to very large amount of data saved in them at a particular time.

----

 ### What is Kafka
 - Apache Kafka is a distributed event streaming platform designed for high-throughput, fault-tolerant, and real-time data streaming. It is commonly used for messaging, log aggregation, real-time analytics, and event-driven applications.

Kafka works as a pub-sub (publish-subscribe) system where producers publish messages, and consumers subscribe to topics to process messages asynchronously. And also as a queue system using groups.

----

### The architecture of Kafka

- Producer
  - A producer is responsible for sending (publishing/ generating data) messages to Kafka topics.
  - Producers do not care which consumers will receive the messages.

- A broker is a Kafka server that stores and manages incoming data streams.
Kafka brokers handle:
  - Storing messages in partitions
  - Ensuring replication for fault tolerance
  - Serving consumer requests
A Kafka cluster usually has multiple brokers to distribute the load.

- Topic
  - A logical category where messages are published.
  - Producers write to topics, and consumers read from topics.
  - Topics are split into partitions to enable parallelism.

- Partitions 
   - A **topic** is divided into multiple **partitions** to allow **horizontal scaling**.  
   - Messages within a **partition** are ordered, but **Kafka does not guarantee global ordering** across partitions.  
   - Each **partition** is stored on a **broker** (a Kafka server).  

- Consumers & Consumer Groups
   - **Consumers** subscribe to topics and consume messages from partitions.  
   - A **consumer group** allows multiple consumers to **read messages in parallel**.  
   - Kafka ensures that **each partition is consumed by only one consumer in a group** to avoid duplicate processing.

----

- Consumer Groups
   - In Apache Kafka, a consumer group is a collection of one or more consumers that cooperate to consume messages from a topic or set of topics, enabling parallel processing and ensuring each 
      message is processed only once within the group.
     
**Note:** A single consumer can consume more than one partitions but a single partition can not be shared by multiple consumers. Groups solve this problem, by grouping consumers.

----

### Kafka Data Flow
1️⃣ Producers publish messages → send data to a specific topic.

2️⃣ Kafka brokers store messages in topic partitions.

3️⃣ Consumers subscribe to topics and process messages asynchronously.

4️⃣ Kafka ensures durability & fault tolerance using replication.

----
### Lastly real world application of Kafka
🔹 Log Aggregation – Collect logs from different microservices.

🔹 Real-time Analytics – Process streaming data from IoT, transactions, etc.

🔹 Event-driven Systems – Trigger actions based on events.

🔹 Data Pipelines – Move data between databases, data lakes, etc.





