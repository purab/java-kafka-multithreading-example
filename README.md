#kafka

Use this command for kafka server

```docker-compose -f docker-compose.yml up```

stop docker images

```docker-compose -f docker-compose.yml down```

```docker exec -it kafka /bin/sh```

```cd /opt/kafka/```

create topic

```./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic mytopic```
```./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic demotopic```

see created topics - list
```./bin/kafka-topics.sh --list --zookeeper zookeeper:2181```

see comsumer logs printing..
```
./bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic mytopic --from-beginning
```

#JAVA Approch one - 
##Multiple consumers with their own threads


The source code for this part includes 4 classes:

* NotificationProducerThread.java is a producer thread, produces message to the Kafka brokers

* NotificationConsumerThread.java is a consumer thread, consumes message from Kafka brokers

* NotificationConsumerGroup.java create a group of NotificationConsumerThread(s)

* MultipleConsumersMain.java contains the main method, run the program to produce and consume messages.

#### Open the MultipleConsumersMain.java on the eclipse. Right click –> Run As –> Java Application or use the shortcut: Alt+Shift+x, j to start the main method.

```
cd /opt/kafka/
./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 3
--topic HelloKafkaTopic1
```

