```bash
kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic superpil-topic
```
* kafka-topics.sh --create --bootstrap-server [주소] --replication-factor [복제개수] --partitions [파티션개수] --topic [토픽명]