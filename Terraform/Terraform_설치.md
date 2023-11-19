# Mac에서 설치
---
```shell
brew install terraform # 테라폼 설치

terraform version # 버전확인
```

# 특정 버전 테라폼 설치 또는 여러 버전 사용
---
```shell
brew install tfenv
```
* 특정 버전 또는 여러 버전을 사용하고 싶은 경우 tfenv를 사용하기
* tfenv는 테라폼 매니저로 맥에서는 테라폼과 마찬가지로 홈브류를 사용해 설치 가능
* 홈브류에서 terraform과 tfenv패키지를 동시에 설치하면 문제가 발생될 수 있으니 한가지만 설치하기

```shell
tfenv install 0.12.23 # 특정 버전 설치
tfenv use 0.12.23 # 특정 버전 사용

terraform version # 버전확인
```
* tfenv로 특정 버전 설치 및 사용

