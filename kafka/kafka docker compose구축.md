```yml
version: '3'
services:
  zookeeper:
    image: zookeeper:latest
    ports:
      - '2181:2181'
  kafka:
    image: bitnami/kafka:latest
    ports:
      - '9092:9092'
    environment:
      - KAFKA_BROKER_ID=1
      - KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper:2181
      - KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092
    depends_on:
      - zookeeper
    restart: always
```
1. KAFKA_BROKER_ID  
카프카 브로커 고유ID값
2. KAFKA_CFG_ZOOKEEPER_CONNECT  
주키퍼 연결 주소
3. KAFKA_ADVERTISED_LISTENERS  
외부 접속 주소