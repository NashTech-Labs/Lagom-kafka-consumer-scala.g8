# lagom-kafka-consumer

A Giter8 template for Lagom Kafka Consumer. It is a simple application to show how we can consume from any kafka topic through lagom

Simply run: **sbt new knoldus/lagom-kafka-consumer.g8**


**Prerequisite**: Kafka
If you do not have Kafka already, download it from here: <https://www.apache.org/dyn/closer.cgi?path=/kafka/1.1.0/kafka_2.11-1.1.0.tgz>

**1) Extract the folder**

tar -xzf kafka_2.11-1.1.0.tgz

cd kafka_2.11-1.1.0

**2) Start the Zookeeper**

bin/zookeeper-server-start.sh config/zookeeper.properties

**3) Start the Kafka Server**

bin/kafka-server-start.sh config/server.properties
 
**4) Create a topic (eg. employee in this case)**

bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic employee

**5) Produce some data into this topic**

- To start producer
   bin/kafka-console-producer.sh --broker-list localhost:9092 --topic employee 
   {"id": "101", "employeeType": "Permanent", "name": "Daniel", "designation": "Full stack Developer", "salary": 60000}
   

**How to Set up?**

**1. Clone the application**
     sbt new knoldus/lagom-kafka-consumer.g8
   
**2. Compile the application**
      sbt clean compile
      
**3. Run the application**
       sbt "project system-impl" lagomServiceLocatorStart run


Template license
Written in 2019 by Ramandeep Kaur

To the extent possible under law, the author(s) have dedicated all copyright and related and neighboring rights to this template to the public domain worldwide. This template is distributed without any warranty. See http://creativecommons.org/publicdomain/zero/1.0/.

Template license
Written in 2019 by Ramandeep Kaur

