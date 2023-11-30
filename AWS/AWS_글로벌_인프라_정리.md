# 개념
* 리전(Region), 가용영역(AZ, Availability Zones), 엣지 로케이션(Edge Location), 리전 엣지 캐시(Regional Edge Cache)로 구성

# 리전
* AWS 서비스들이 제공되는 서버의 물리적인 국가/도시 단위의 위치를 의미
* 여러 국가에 여러개의 리전을 두는 이유는 네트워크 속도가 가장 큰 이유
* 두번째로는 각종 재해에 대비, 미국 본사에 재해가 발생해 문제가 생겨도 각 세계에 퍼져있는 리전이 대신 서비스를 유지 가능
* AWS 리전마다 사용료가 다름

# 가용영역
* 리전이 국가/도시 단위의 지리적 위치면, 가용영역은 각 리전안의 데이터 센터를 의미
* 서버 컴퓨터들이 모여있는 건물로 이해
* 기본적으로 AWS리전에는 2개 이상의 가용영역을 가지고 있음
* 가용영역끼리 일정 거리 떨어져 있어 각종 재해, 정전, 화재에 대비 가능
* 다만 모든 AZ는 서로 100Km이내의 거리에 위치(속도측면 때문)

# 엣지 로케이션
* AWS의 CDN들의 여러 서비스들을 가장 빠른 속도로 제공(캐싱)하기 위한 거점
* 전 세계에 여러 장소에 흩어져 있음
* 리전과 가용영역과 별개로 CloudFront, Route53의 캐시 서버를 의미

# 리전 엣지 캐시
* CDN서비스인 Cloudfront를 위한 캐시 서버들
* 리전 엣지 캐시는 CloudFront 배포에서 기본적으로 활성화되어 있기 때문에 이 기능을 사용하기 위해 배포를 변경해야 할 필요는 없음. 이 기능을 사용하는 데 따른 추가 비용도 없음

# Reference
1. https://inpa.tistory.com/entry/AWS-📚-아마존-웹-서비스-구조-Region-AZ-Edge-Location-Cache-완벽-정리
1. https://aws.amazon.com/ko/about-aws/whats-new/2016/11/announcing-regional-edge-caches-for-amazon-cloudfront/
