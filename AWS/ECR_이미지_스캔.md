# 개념
* 이미지 스캔 기능은 ECR에 저장 되어있는 이미지나, 이미지를 푸시할 때 이미지를 스캔하는 기능이며, 도커의 이미지의 취약점 검사를 수행하는 도구 중 하나
* 이런 도구는 이미 
* 취약점 스캐닝 기능은 바이러스 검사 앱과 유사하며, 서비스나 도구 별로 서로 다른 결과를 내놓기 때문에 어떤 도구를 선택하고 그 결과를 신뢰할지, 그리고 어느 정도까지 대응할지는 사용자가 판단해야함
* ECR의 이미지 스캔 기능은 무료이며, 이미지 당 24시간 동안 1번만 스캔가능하고 추가로 스캔을 하려고 시도하는 경우 ThrottlingException발생
* 이미지 스캔 결과는 console, cli로 볼 수 있음
* ECR이미지 스캔 설정을 활성화하지 않더라도 AWS CLI로 수동으로 이미지 스캔이 가능함

# Reference
1. https://www.44bits.io/ko/post/news--amazon-ecr-docker-image-vulnerabilities-scanning
1. https://sarc.io/index.php/aws/2159-ecr-image-scanning
