# 개념
* VPC와 인터넷 간에 통신을 할 수 있게 해줌
* IPv4, IPv6를 지원
* 예를 들어 인터넷 게이트웨이를 사용하면 로컬 컴퓨터로 AWS의 EC2 인스턴스에 연결할 수 있음
* 인터넷 게이트웨이는 VPC 라우팅 테이블에서 인터넷 라우팅 가능 트래픽에 대한 대상을 제공
* 즉, Internet Gateway는 VPC 내부에 있는 리소스(EC2, RDS 등)가 외부 인터넷과 소통하기 위한 통로(인바운드, 아웃바운드 모두 포함)
* 인터넷 게이트웨이를 생성하는 경우 추가 요금이 부과되지 않음

# Reference
1. https://docs.aws.amazon.com/ko_kr/vpc/latest/userguide/VPC_Internet_Gateway.html
