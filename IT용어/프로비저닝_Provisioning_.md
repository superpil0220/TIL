AWS공식문서에서 ECS의 관련된 문서를 보면 “Fargate 시작 유형은 프로비저닝 없이 컨테이너화된 애플리케이션을 실행하고 기본 인프라를 관리할 때 사용할 수 있습니다.”는 문장을 볼수있다.<br>여기서 프로비저닝이란 무엇일까?<br>
# 개념
* 인프라에서 많이 나오는 용어
* 사전적인 의미로는 
* 프로비저닝은 사용자의 요구에 맞게 시스템 자원을 할당, 배치, 배포해 두었다가 필요 시 시스템을 즉시 사용할 수 있는 상태로 미리 준비해 두는 것
* IaaS (Infrastructure as a Service)와 같이 컴퓨팅 리소스, 스토리지, 네트워크 등을 사용자 요구에 맞게 제공하는 것을 Provisioing

# 프로비저닝 종류
* Server Resource Provisioning : 
CPU, Memory, IO 등과 같은 실제 서버의 자원을 할당해주고 운영할 수 있게 제공해주는 것
* OS Provisioning : 
OS를 서버에 설치하고 구성작업을 해서 사용할 수 있도록 제공하는 것
* Software Provisioning : 
WAS, DBMS 등의 소프트웨어를 설치하고 세팅하여 실행할 수 있도록 제공하는 것
* Account Provisioning : 
접근 권한을 가진 계정을 제공해주는 것
* Storage Provisioning : 
데이터를 저장하고 관리할 수 있는 Storage 를 제공하는 것

# Reference
1. https://jins-dev.tistory.com/entry/프로비저닝Provisioning-이란
1. https://web-front-end.tistory.com/104
1. https://hong-yp-ml-records.tistory.com/125
