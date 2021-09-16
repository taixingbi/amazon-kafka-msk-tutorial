
#### basic 
```
./kafka-console-producer.sh --broker-list b-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094,b-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094 --producer.config client.properties --topic mp.inventory.v1

./kafka-console-consumer.sh --bootstrap-server b-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094,b-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094 --consumer.config client.properties --topic mp.inventory.v1 --from-beginning

```

#### yum install docker
```
https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html
```



#### ZookeeperConnectString
```
z-3.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181,z-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181,z-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181
```

#### BootstrapBrokerStringTls
```
b-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094,b-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094
```

### topic AWSKafkaTutorialTopic

###### create topic
bin/kafka-topics.sh --create --zookeeper ZookeeperConnectString --replication-factor 2 --partitions 1 --topic AWSKafkaTutorialTopic

```
bin/kafka-topics.sh --create --zookeeper z-3.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181,z-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181,z-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181 --replication-factor 2 --partitions 1 --topic mp.inventory.v1

bin/kafka-topics.sh --create --zookeeper z-3.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181,z-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181,z-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:2181 --replication-factor 3 --partitions 1 --topic mp.inventory.v1

bin/kafka-topics.sh --create --zookeeper z-2.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-3.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181,z-1.awskafkatutorialclust.bwvs6a.c10.kafka.us-east-1.amazonaws.com:2181 --replication-factor 3 --partitions 1 --topic test


```

##### jvm
```
java-1.8.0-openjdk-1.8.0.302.b08-0.amzn2.0.1.x86_64
-- User the Trust store 
cp /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.302.b08-0.amzn2.0.1.x86_64/jre/lib/security/cacerts /tmp/kafka.client.truststore.jks

-- client.properties
security.protocol=SSL 
ssl.truststore.location=/tmp/kafka.client.truststore.jks



```


###### produce
./kafka-console-producer.sh --broker-list BootstrapBrokerStringTls --producer.config client.properties --topic mp.inventory.v1

```
./kafka-console-producer.sh --broker-list b-1.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094,b-2.test-cluster-1.qvtxwq.c7.kafka.us-east-2.amazonaws.com:9094 --producer.config client.properties --topic mp.inventory.v1

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


# MSK Comands For Creating a Cluster and Streaming Data

Install Java:
sudo yum install java-1.8.0

Get Kafka:wget https://archive.apache.org/dist/kafka/2.2.1/kafka_2.12-2.2.1.tgz

Extract Kafka:
tar -xzf kafka_2.12-2.2.1.tgz

Get Cluster ARN:
aws kafka describe-cluster --region us-east-2 --cluster-arn "ClusterArn"  
aws kafka describe-cluster --region us-east-2 --cluster-arn arn:aws:kafka:us-east-2:159363735810:cluster/test-cluster-1/cc80ac7c-3edf-4c6d-95c7-bce68fd48023-7 

Create Topic:
bin/kafka-topics.sh --create --zookeeper "ZookeeperConnectString" --replication-factor 2 --partitions 1 --topic AWSKafkaTutorialTopic

User the Trust store:
cp /usr/lib/jvm/JDKFolder/jre/lib/security/cacerts /tmp/kafka.client.truststore.jks

client.properties:
security.protocol=SSL
ssl.truststore.location=/tmp/kafka.client.truststore.jks

Get Brokers:
aws kafka get-bootstrap-brokers --cluster-arn ClusterArn --region

Producer:
./kafka-console-producer.sh --broker-list BootstrapBrokerStringTls --producer.config client.properties --topic AWSKafkaTutorialTopic

Consumer:
./kafka-console-consumer.sh --bootstrap-server BootstrapBrokerStringTls --consumer.config client.properties --topic AWSKafkaTutorialTopic --from-beginning

