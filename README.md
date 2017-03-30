1. start zookeper  (/Downloads/kafka_2.11-0.10.1.0)
bin/zookeeper-server-start.sh config/zookeeper.properties
ps aux | grep zookeeper.properties
2. start Kafka server
bin/kafka-server-start.sh config/server.properties
3. create a topic
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
4. to check whether the topic created is listed or not
bin/kafka-topics.sh --list --zookeeper localhost:2181
5. Send message through producer
Compile the class 
javac -cp “/Users/avakil/Downloads/kafka_2.11-0.10.1.0/libs/*” SimpleProducer.java
run the class
java -cp “/Users/avakil/Downloads/kafka_2.11-0.10.1.0/libs/*”:. SimpleProducer test2
6. Start the consumer


* to run producer from executable jar through terminal
java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.SimpleProducer <topic name>
//my local 
java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.SimpleProducer test1125

* to run Consumer from executable jar through terminal
java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.CosumerKafka <topic name>
//my local
java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.CosumerKafka test1125

To run the project jar from terminal 
java -cp dl4j-examples-0.5-SNAPSHOT-bin.jar org.deeplearning4j.examples.dataExamples.DdosDLRun


For multiple brokers
bin/kafka-server-start.sh config/server_1.properties
bin/kafka-server-start.sh config/server_2.properties

For multiple replication
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 1 --topic outdl


java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.KafkaConsumerInJavaForLocal input DLOutput
java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.KafkaProducerInJavaForLocal test19
java -cp messaging-1.0-SNAPSHOT-bin.jar com.kafka.ConsumerKafkaToES DLOutput
