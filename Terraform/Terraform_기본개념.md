# 프로바이더(Provider)
* 테라폼과 외부 서비스를 연결해주는 기능을 하는 모듈
* 예를 들어 테라폼에서 AWS서비스를 생성하기 위해서는 AWS프로바이더를 먼저 셋업해야함
* 프로바이더로는 AWS, 구글 클라우드 플랫폼, 마이크로소프트 애저, 깃허브, 데이터 도그, DNSimple, Mysql, 레빗MQ, 도커 등 지원

# 리소스(Resource)
* 특정 프로바이더가 제공해주는 조작 가능한 대상의 최소 단위
* 예를 들어 AWS 프로바이더는 AWS_instance 리소스 타입을 제공하고 리소스 타입을 사용해 EC2의 가상 머신 리소스를 선언하고 조작 가능
* EC2 인스턴스, 시큐리티 그룹, 키 페어 모두 AWS 프로바이더가 제공해주는 리소스 타입

# HCL
* 테라폼에서 사용하는 설정 언어
* HCL 파일의 확장자는 .tf를 사용

# 계획(Plan)
* 테라폼 프로젝트 디렉터리 아래의 모든 .tf파일의 내용을 실제로 적용 가능한지 확인하는 작업을 “계획”임
* “terraform plan” 명령어로 제공되며, 이 명령어를 실행하면 어떤 리소스가 생성, 수정, 삭제될지 계획을 보여줌

# 적용(Apply)
* 테라폼 프로젝트 디렉토리 아래의 모든 .tf파일의 내용대로 리소스를 생성, 수정, 삭제하는 일을 “적용”임
* “terraform apply”명령어로 제공되며, 이 명령어를 실행하기 전에 변경 예정 사항은 plan명령어를 사용해 확인 할 수 있음

# Reference
1. https://www.44bits.io/ko/post/terraform_introduction_infrastrucute_as_code
1. https://developer.hashicorp.com/terraform/language/providers

