# 쓰레드 우선순위
* 작업의 중요도에 따라 쓰레드의 우선순위를 다르게 하여 특정 쓰레드가 더 많은 작업시간을 갖게 할 수 있다.
* 자바에서 우선순위를 1 ~ 10까지 가질수있다. 숫자가 높을수록 우선순위가 높다
* 쓰레드를 만들고 우선순위를 지정하지 않으면 5로 설정된다
* 우선순위가 높을수록 작업시간 할당량이 많다.

```java
public static void main(String[] args) {
  SpringApplication.run(SpringDemoApplication.class, args);

  ThreadDemo1 threadDemo1 = new ThreadDemo1();
  threadDemo1.setPriority(10);
	threadDemo1.getPriority();
  
	threadDemo1.start();
}

static class ThreadDemo1 extends Thread {

  public void run() {
    for (int i = 0; i < 5; i++) {
      System.out.println("11111111111 : " + this.getName());
    }
  }
}
```
* setPriority로 우선순위를 설정할 수 있다.
* getPriority로 우선순위를 확인 할 수 있다.

# 참고자료
1. https://www.youtube.com/watch?v=KWZjeW6zkyY&list=PLW2UjW795-f6xWA2_MUhEVgPauhGl3xIp&index=151

