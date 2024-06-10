
# Kafka CLI Commands Cheat Sheet

## Topic Management

### List Topics
```sh
kafka-topics.sh --list --bootstrap-server <broker-host>:<port>
```
Lists all topics in the Kafka cluster.

### Create Topic
```sh
kafka-topics.sh --create --topic <topic-name> --bootstrap-server <broker-host>:<port> --partitions <num-partitions> --replication-factor <replication-factor>
```
Creates a new topic with specified number of partitions and replication factor.

### Describe Topic
```sh
kafka-topics.sh --describe --topic <topic-name> --bootstrap-server <broker-host>:<port>
```
Describes the configuration of a specific topic.

### Delete Topic
```sh
kafka-topics.sh --delete --topic <topic-name> --bootstrap-server <broker-host>:<port>
```
Deletes a specific topic.

## Producer and Consumer

### Produce Messages
```sh
kafka-console-producer.sh --topic <topic-name> --bootstrap-server <broker-host>:<port>
```
Starts a console producer that sends messages to the specified topic.

### Consume Messages
```sh
kafka-console-consumer.sh --topic <topic-name> --bootstrap-server <broker-host>:<port> --from-beginning
```
Starts a console consumer that reads messages from the specified topic from the beginning.

## Consumer Group Management

### List Consumer Groups
```sh
kafka-consumer-groups.sh --list --bootstrap-server <broker-host>:<port>
```
Lists all consumer groups.

### Describe Consumer Group
```sh
kafka-consumer-groups.sh --describe --group <group-id> --bootstrap-server <broker-host>:<port>
```
Describes the specified consumer group.

### Delete Consumer Group
```sh
kafka-consumer-groups.sh --delete --group <group-id> --bootstrap-server <broker-host>:<port>
```
Deletes the specified consumer group.

## Broker Management

### List Brokers
```sh
kafka-broker-api-versions.sh --bootstrap-server <broker-host>:<port>
```
Lists all brokers and their API versions.

### Describe Configurations
```sh
kafka-configs.sh --describe --entity-type brokers --entity-name <broker-id> --bootstrap-server <broker-host>:<port>
```
Describes configurations for the specified broker.

## Partition Reassignment

### Reassign Partitions
```sh
kafka-reassign-partitions.sh --bootstrap-server <broker-host>:<port> --reassignment-json-file <path-to-json-file> --execute
```
Reassigns partitions based on the provided JSON file.

## ACL Management

### Create ACL
```sh
kafka-acls.sh --add --allow-principal <principal> --operation <operation> --topic <topic-name> --bootstrap-server <broker-host>:<port>
```
Adds an ACL for the specified topic.

### List ACLs
```sh
kafka-acls.sh --list --bootstrap-server <broker-host>:<port>
```
Lists all ACLs.

### Remove ACL
```sh
kafka-acls.sh --remove --allow-principal <principal> --operation <operation> --topic <topic-name> --bootstrap-server <broker-host>:<port>
```
Removes an ACL for the specified topic.

## Utility

### Check Kafka Version
```sh
kafka-broker-api-versions.sh --bootstrap-server <broker-host>:<port>
```
Displays the API versions supported by the broker.

### Dump Log Segments
```sh
kafka-dump-log.sh --files <path-to-log-file> --print-data-log
```
Dumps the contents of a log file for debugging purposes.

### Mirror Maker
```sh
kafka-mirror-maker.sh --consumer.config <consumer-config-file> --producer.config <producer-config-file> --whitelist <topic-regex>
```
Runs the Kafka MirrorMaker tool for mirroring data between clusters.
