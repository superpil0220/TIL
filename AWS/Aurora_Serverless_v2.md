# 개념
* 온디맨드 방식의 자동 크기 조정 구성
* 워크로드(주어진 기간에 실행되는 작업의 할당량)를 모니터링하고 데이터베이스의 용량을 조정하는 프로세스를 자동화하는데 도움
* 수동으로 용량을 관리하는 Aurora프로비저닝된 DB클러스터와 달리, Aurora Serverless DB클러스터는 애플리케이션의 필요에 따라 컴퓨팅 용량이 확장 또는 축소되는 DB클러스터
* 자동으로 시작하고 애플리케이션의 사용량에 맞춰 컴퓨팅 용량을 확장하고, 사용하지 않는 경우 종료되기 때문에 비용 효율적
* 용량은 애플리케이션 수요에 따라 자동으로 조정
* 요금은 DB클러스터가 사용하는 리소스에 대해서만 청구

# Reference
1. https://docs.aws.amazon.com/ko_kr/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.html
1. https://support.bespinglobal.com/ko/support/solutions/articles/73000544760--aws-amazon-aurora-cluster에서-aurora-serverless로-전환
