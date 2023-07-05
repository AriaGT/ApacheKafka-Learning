# Apache Kafka Basic Commands

### Recommendations:
- Based on my experience, work with the main Kafka file in the path closest to the main disk, to avoid errors when executing the commands, fo example in: `c:/kafka_2.13-3.5.0/`
- Inside `/config/zookeeper.properties` file, change 'dataDir' value for the path of Kafka and add **/zookeeper-data** to the path, for example:
```
    dataDir=c:/basic_commands/zookeeper-data
```
- Inside `/config/server.properties` file, change 'dataDir' value for the path of Kafka and add **/kafka-logs** to the path, for example:
```
    log.dirs=c:/basic_commands/kafka-logs
```

### 1. Start Zookeeper
```
    .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties`
```

### 2. Start Apache Kafka
```
    .\bin\windows\kafka-server-start.bat .\config\server.properties
```

### 3. Topics list
```
    .\bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092
```

### 4. Create topic
```
    .\bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic <topic-name>
```

### 5. Delete topic
```
    .\bin\windows\kafka-topics.bat --delete --bootstrap-server localhost:9092 --topic <topic-name>
```

### 5. Create producer
```
    .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic <topic-name>
```

### 6. Create consumer
```
    .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic <topic-name> -from-beginning
```

### 7. Stop Apache Kafka
```
    .\bin\windows\kafka-server-stop.bat
```

### 8. Stop Zookeeper
```
    .\bin\windows\zookeeper-server-stop.bat
```
