# Daemon Thread
* 일반 쓰레드의 작업을 돕는 보조적 역할을 수행한다.
* 일반 쓰레드가 모두 종료되면 자동으로 종료된다.
* 가비지 컬렉터, 자동 저장, 화면 자동갱신 등에 데몬 쓰레드가 사용된다.
* 무한루프와 조건문을 이용해서 실행 후 대기하다가 특정조건이 만족되면 작업을 수행하고 다시 대기하도록 작성한다.
```java
public void run() {
	whiel(true){
		try {
			Thread.sleep(3000);
		} catch(InerruptedException e) {}
		if(autoSave) {
			autoSave();
		}
	}
}
```
* 데몬 쓰레드 패턴은 대부분 무한루프로 실행하고 특정 조건이 발생되면 작업을 수행하는 형태다.
* 일반 쓰레드가 종료되면 데몬 쓰레드는 자동종료되기 때문에 정확하게 말하면 무한루프는 아니다.

```java
void setDaemon(booleam on) // 쓰레드를 데몬 쓰레드로 또는 일반 쓰레드로 변경
booleam isDaemon() // 쓰레드가 데몬 쓰레드인지 확인한다. 쓰레드를 start()하기 전에 thread를 데몬 쓰레드로 할지 말지를 정해야된다.
```



# 참고자료
1. https://www.youtube.com/watch?v=W0v3Gwx92hc&list=PLW2UjW795-f6xWA2_MUhEVgPauhGl3xIp&index=152
