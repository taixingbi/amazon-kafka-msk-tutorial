
#### ZookeeperConnectString
z-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181

#### BootstrapBrokerStringTls
b-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094

### topic AWSKafkaTutorialTopic

###### create topic
bin/kafka-topics.sh --create --zookeeper ZookeeperConnectString --replication-factor 3 --partitions 1 --topic AWSKafkaTutorialTopic

```
bin/kafka-topics.sh --create --zookeeper z-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181 --replication-factor 3 --partitions 1 --topic AWSKafkaTutorialTopic

bin/kafka-topics.sh --create --zookeeper z-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181 --replication-factor 3 --partitions 1 --topic test

bin/kafka-topics.sh --create --zookeeper z-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181 --replication-factor 3 --partitions 1 --topic test

bin/kafka-topics.sh --create --zookeeper z-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181 --replication-factor 3 --partitions 1 --topic test
```


###### produce
./kafka-console-producer.sh --broker-list BootstrapBrokerStringTls --producer.config client.properties --topic AWSKafkaTutorialTopic

```
./kafka-console-producer.sh --broker-list b-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094 --producer.config client.properties --topic AWSKafkaTutorialTopic
```

###### consumer
./kafka-console-consumer.sh --bootstrap-server BootstrapBrokerStringTls --consumer.config client.properties --topic AWSKafkaTutorialTopic --from-beginning
```
./kafka-console-consumer.sh --bootstrap-server b-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094 --consumer.config client.properties --topic AWSKafkaTutorialTopic --from-beginning
```

### topic webCollectData
###### produce
./kafka-console-producer.sh --broker-list BootstrapBrokerStringTls --producer.config client.properties --topic webCollectData

```
./kafka-console-producer.sh --broker-list b-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094 --producer.config client.properties --topic webCollectData
```

###### consumer
./kafka-console-consumer.sh --bootstrap-server BootstrapBrokerStringTls --consumer.config client.properties --topic webCollectData --from-beginning
```
./kafka-console-consumer.sh --bootstrap-server b-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094,b-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:9094 --consumer.config client.properties --topic webCollectData --from-beginning
```
