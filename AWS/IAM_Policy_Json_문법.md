# 구조
```json
{
	"Version": "2012-10-17"
	"Statement": [
    {
			"Effect": "Allow",
      "Principal": {
        "AWS": "*"
      },
      "Action": "SQS:*",
			"Resource": "arn:aws:sqs:ap-northeast-2:1234444:test.fifo"
    }
  ]
}
```
## Version
* Version과 Statement속성은 항상 들어감
* 타입은 String
* default가 2008-10-17이지만 2012-10-17를 사용하기

## Statement
* 타입은 array
* 권한 부여 규칙의 나열

## Id
* 정책 식별자를 지정
* ID 요소를 설정할 수 있는 서비스의 경우에는 UUID를 값으로 사용하거나, UUID를 ID일부로 사용하여 고유성 확보하는게 좋음

## Effect
* 명시된 정책에 대한 허용 혹은 차단
* Allow 또는 Deny가 있음
* Allow는 허용, Deny는 차단

## Action
* 타입은 String 또는 Array<String>
* 하나 혹은 여러 개의 Action을 지정가능
* Action은 [서비스 접두사] : [작업] 형식으로 작성
* 예를 들어 s3:GetObject 등

## Resource
* Statement의 주제가 되는 리소스를 한정
* 리소스를 특정할 수 없는 일부 서비스에서는, Resource를 비워두는 대신 *
를 입력

## Principal
* 리소스 기반 정책에서, 보안 주체를 지정

## Sid
* 타입은 String
* Statement ID
* 각 요소에 Unique ID를 붙이고 싶은 때 사용

# Reference
1. https://blog.voidmainvoid.net/405
1. https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/reference_policies_elements.html
1. https://musma.github.io/2019/11/05/about-aws-iam-policy.html

