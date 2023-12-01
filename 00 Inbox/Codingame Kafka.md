
# QCM

### [Kafka Core] Definition of Consumer Group
Kafka Core (40 pts)

Choose the correct definition of Consumer group.

- A set of consumers connected together to distribute the load across partition.
- A set of consumers connected together to distribute the load across topics.
- All consumers connected to a topic are considered to be consumer group
- All consumers connected to a Kafka cluster are considered to be a consumer group

### [Kafka Core] Partitioner
Kafka Core (20 pts)

How does Kafka distribute records over multiple partitions if the key is not available?

- 32-bit murmur2 Hash Partitioner
- Round-robin fashion
- Least Recently Used (LRU) algorithm
- An error will occur: the key is mandatory
- The first partition will always be selected

### [Schema Registry] Architecture
Kafka Schema Registry (20 pts)

What is the **architecture** of the **Schema Registry**?

- Distributed architecture, using single-primary
- Distributed architecture, using multi-primary
- Centralized architecture
- Master-Slave architecture
- Localized architecture: there's one instance on each broker

### [Kafka Core] Format of configuration files
Kafka Core (20 pts)

What is the format of configuration files in Kafka?

- JSON
- AVRO
- XML
- Key-value properties file

### [Kafka Core] Partitions
Kafka Core (20 pts)

Can we have multiple records with the same key in Kafka?

- Yes, keys do not need to be unique
- No, keys must be unique

### [Schema Registry] Architecture
Kafka Schema Registry (20 pts)

What is the **architecture** of the **Schema Registry**?

- Distributed architecture, using single-primary
- Distributed architecture, using multi-primary
- Centralized architecture
- Master-Slave architecture
- Localized architecture: there's one instance on each broker

### [Kafka Core] Format of configuration files
Kafka Core (20 pts)

What is the format of configuration files in Kafka?

- JSON
- AVRO
- XML
- Key-value properties file

### [Kafka Core] Partitions
Kafka Core (20 pts)

Can we have multiple records with the same key in Kafka?

- Yes, keys do not need to be unique
- No, keys must be unique

### [Schema Registry] Architecture
Kafka Schema Registry (20 pts)

What is the **architecture** of the **Schema Registry**?

- Distributed architecture, using single-primary
- Distributed architecture, using multi-primary
- Centralized architecture
- Master-Slave architecture
- Localized architecture: there's one instance on each broker

### [Kafka Core] Format of configuration files
Kafka Core (20 pts)

What is the format of configuration files in Kafka?

- JSON
- AVRO
- XML
- Key-value properties file

### [Kafka Core] Partitions
Kafka Core (20 pts)

Can we have multiple records with the same key in Kafka?

- Yes, keys do not need to be unique
- No, keys must be unique

### [Kafka Streams] KTable
Kafka Core (20 pts)

How can we create a stream for which a data record is interpreted as an "UPDATE" of the last value for the same record key?

- By using a KStream
- By using a KTable
- By creating a materialized view of the KStream
- By dealing with this manually
- By using a KSet

### [Kafka Brokers] Cluster Performance
Kafka Sizing (40 pts)

We have a Kafka topic with a **replication factor of 3** and **10 partitions**. It stores **50 GB of data** and is consumed by **10 consumer groups**.

The data has been increased to **50 TB** and the **number of consumer groups to 100**.

How will the performance of the Kafka cluster be impacted by these changes?

- Performance will be reduced due to an increase in total size
- Performance will be improved due to an increase in consumer groups
- No change in Kafka’s performance, data will be distributed and consumers will increase offset tracking
- Performance will be reduced because Kafka has to push each record to a higher number of consumers

### [Kafka Core] Synchronous Send
Kafka Core (40 pts)

In the given code, we need to send the record over Kafka in a **synchronous manner**:

```java
String key = "key";
String value = "value";

ProducerRecord<String,String> record = new ProducerRecord<String, String>("DATA_TOPIC", key, value);
```

What is the correct way to achieve this?

- `producer.send(record);`
- `producer.send(record).get();`
- `producer.send(record).wait();`

### [Kafka Core] Use Cases
Kafka Core (40 pts)

Choose all the correct options about **Kafka use cases**:

- Kafka is used for building real-time data pipelines and streaming apps
- Kafka can be used as a transactional database
- Kafka can be used as a database for OLAP
- Kafka can be used as an in-memory database

### [Schema Registry] Default name strategy
Kafka Schema Registry (40 pts)

What is the default **subject name strategy** in the schema registry?

- TopicNameStrategy
- RecordNameStrategy
- TopicRecordNameStrategy
- DefaultSubjectNameStrategy
- AvroSerDeNameStrategy

### [Kafka Connect] Plugin Path
Kafka Connect (40 pts)

Where does **Kafka connect** find the **plugins** to load?

- In a list of folders defined in `plugin.path`
- In a list of folders defined in `plugin.location`
- In the `<Kafka-connect-path>/lib/` folder

### [Kafka Zookeeper] Ephemeral nodes
Kafka Zookeeper (40 pts)

What is an **Ephemeral node**?

- The nodes that are created in Zookeeper
- A temporary node that only exists while the session that created the node is active
- A node that will be removed during the next compaction
- A node that is no longer available but not removed yet

### [Kafka Core] Message delivery guarantees
Kafka Core (20 pts)

What **guarantee** is provided by Kafka regarding **message delivery**?

- At-least-once
- At-most-once
- Exactly-once
- At-least-once by default and exactly-once using transactions

### [Zookeeper] Number of nodes
Kafka Zookeeper (20 pts)

What is the recommended number of Zookeeper nodes to be used in a cluster?

- 1
- 3
- Odd numbers
- Even numbers

# Text

# Code
