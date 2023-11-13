# 개념
* 샤드 PubSub은 기존 Redis Cluster에서의 PubSub의 단점을 해결하기 위해 도입
* 우선 기존 Cluster의 문제점은 Cluster에 PubSub은 모든 노드에 데이터를 뿌림
* 하나의 노드에 Pub을하면 모든 노드(Primary + Replica)들에 Pub를 broadcast하게 되고, 어떤 노드에 Sub을 하든 해당 broadcast되는 메시지를 받을 수 있음
* broadcast 는 클라이언트가 Primary에 Sub 를 하든 Replica 에 Sub 를 하든 상관없습니다. 물론 Pub 역시 상관이 없음
* 네트워크에서도 broadcast는 성능상 문제가 발생하며, redis에서도 동일하게 성능문제를 야기시킴
* 보통 메시지 전달은 채널 수 + 채널에 붙은 클라이언트 수 만큼 루프를 돌아야함
* 항상 모든 서버에 broadcast해야 한다는게 전체 성능에 영향을 미칠 수 있음(클러스터가 커지면 커질수록 문제가 더욱 발생 가능성이 높아짐)
* 이런 문제점을 해결하기 위해 샤드군(shard)해서 특정 노드에만 해당 채널의 정보를 Pub함
* 특정 샤드에만 메시지를 보내짐
* 따라서 기존의 Pub, Sub은 모든 노드에 데이터를 보내기 때문에 아무 노드에만 Sub을 해도 메시지를 전달 받을 수 있지만 샤드 PubSub은 불가능
* 샤드 PubSub은 ssubscribe, spublish 등의 명령을 가짐
* 샤드 PubSub는 broadcast를 줄여서 실제 부하를 줄이는 컨셉

# Reference
1. https://dev.to/rueian/using-redis-7s-new-sharded-pubsub-in-go-2bi
1. https://redis.io/docs/manual/pubsub/
1. https://docs.aws.amazon.com/ko_kr/AmazonElastiCache/latest/red-ug/BestPractices.PubSub.html
1. https://charsyam.wordpress.com/2022/04/18/입-개발-redis-7-x-에서의-shardedpubsub/
