# 예외처리(Exception Handling)
* 프로그램 실행 시 발생할 수 있는 예외에 대한 코드를 작성하여 비정상 종료를 막고 정상적인 실행상태를 유지하는 것
* 예외처리는 try-catch문을 통해 가능

## 기본구조
```java
try {
	// 정상코드(예외발생 가능성있는 코드)
} catch (Exception1 error) {
	// 정상코드에서 Exception1 예외가 발생 시 실행될 코드
} catch (Exception2 error) {
	// 정상코드에서 Exception2 예외가 발생 시 실행될 코드
} catch (Exception1 error) {
	// 정상코드에서 Exception3 예외가 발생 시 실행될 코드
}
```
* 이 중 발생한 예외의 종류와 일치하는 단 한 개의 catch블럭만 수행
* 발생된 예외가 catch에 포함되지 않으면 예외 처리 안됨

```java
try {

	try {
		// 코드
	} catch (Exception error) {
		// 코드
	}

} catch (Exception error) {
	String error = "superpil"; // error 동일한 변수 선언으로 에러!
	try {
		// 코드
	} catch (Exception error) { // error 동일한 변수 선언으로 에러!
		// 코드
	}

}
```
* try-catch 내부에서 또 try-catch를 사용할 수 있음
* catch 내부에서 또 다른 예외가 발생할 수 있어 try-catch 사용 가능
* catch블럭에서 선언된 변수는 catch블럭 내부에서 유효하며, catch블럭에서 사용된 변수는 내부에 동일한 변수명으로 사용할 수 없음(Exception error에서 error변수는 catch블럭 내부에서 중복으로 변수 사용 불가능)

## try-catch 흐름
```java
public void handleException() {
  System.out.println(1);
  System.out.println(2);
  try {
    System.out.println(3);
    System.out.println(4);
  } catch (Exception error) {
    System.out.println(5);
  }
  System.out.println(6);
}

/*
실행결과
1
2
3
4
6
*/
```
* try블럭 내부에서 예외가 발생하면 일치하는 catch가 있는지 찾고 catch블럭을 실행
* try블럭 내부에서 예외가 발생하지 않으면 catch블럭을 생략하고 다음 코드를 수행
* 위 예제에서 try블럭에 예외가 발생하지 않아 catch블럭은 실행되지않고 다음 코드(System.out.println(6))이 실행


