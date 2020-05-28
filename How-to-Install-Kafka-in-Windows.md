# How to Install Kafka in Windows
# Download Apache Kafka binary download
## https://www.apache.org/dyn/closer.cgi?path=/kafka/2.5.0/kafka_2.12-2.5.0.tgz

# Update file config/server.properties, fill in log.dirs with :
## d:/Kafka-212-250/kafka-logs (your kafka folder location)

# Update file config/zookeeper.properties, fill in dataDir with :
## d:/Kafka-212-250/zookeeper-data (your kafka folder location)

# Run Zookeeper with open cmd, type:
## ./bin/windows/zookeeper-server-start.bat ./config/zookeeper.properties, then minimize

# Run Kafka with open other cmd, type:
##./bin/windows/kafka-server-start.bat ./config/server.properties, then minimize

# Try to create Topics, open other cmd, type:
## ./bin/windows/kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic TestTopic

#Check available topics, type:
## ./bin/windows/kafka-topics.bat --list --zookeeper localhost:2181

# Send message, type:
## ./bin/windows/kafka-console-producer.bat --broker-list localhost:9092 --topic TestTopic

# Read message, open another cmd, type:
##./bin/windows/kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic TestTopic --from-beginning

# Done
