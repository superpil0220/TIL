# Thread를 Extends로 생성
```java
public static void main(String[] args) {
  SpringApplication.run(SpringDemoApplication.class, args);

  ThreadDemo1 threadDemo1 = new ThreadDemo1();
  threadDemo1.start();
}

static class ThreadDemo1 extends Thread {
	public void run() {
	  for (int i = 0; i < 5; i++) {
	    System.out.println("[Extends Thread] " + this.getName());
	  }
	}
}
/*
[Extends Thread] Thread-1
[Extends Thread] Thread-1
[Extends Thread] Thread-1
[Extends Thread] Thread-1
[Extends Thread] Thread-1
*/
```
* Thread를 상속받았기 때문에 this.getName()으로 현재 thread의 이름을 가져올 수 있다.
* start로 thread를 실행한다.

# Runnable로 생성
```java
public static void main(String[] args) {
	SpringApplication.run(SpringDemoApplication.class, args);

  ThreadDemo2 threadDemo2 = new ThreadDemo2();
  Thread thread = new Thread(threadDemo2);
  thread.start();
}

static class ThreadDemo2 implements Runnable {
  @Override
  public void run() {
    for (int i = 0; i < 5; i++) {
      System.out.println("[Runnable Thread] " + Thread.currentThread().getName());
    }
  }
}
/*
[Runnable Thread] Thread-2
[Runnable Thread] Thread-2
[Runnable Thread] Thread-2
[Runnable Thread] Thread-2
[Runnable Thread] Thread-2
*/
```
* Runnable는 상속을 받지 않았기 때문에 현재 thread의 이름을 Thread.currentThread()로 가져올 수 있다.
* start로 thread를 실행한다.

# Thread Start
---
```java
ThreadDemo1 threadDemo1 = new ThreadDemo1();
ThreadDemo2 threadDemo2 = new ThreadDemo2();

threadDemo1.start(); // threadDemo1실행
threadDemo2.start(); // threadDemo2실행
```
* threadDemo1을 먼저 start를 했지만 threadDemo2보다 start가 늦을 수 있다. 
* start 선언 상관없이 OS 스케줄러가 실행순서를 결정한다.
* 즉, 먼저 start 했다고 먼저 시작되는게 아니고 나중에 start 했다고 나중에 시작되는게 아니다.
* 따라서 thread는 os에 의존적이다.

# 참고자료
1. https://www.youtube.com/watch?v=P1zDndoy4pI&list=PLW2UjW795-f6xWA2_MUhEVgPauhGl3xIp&index=149&t=4s


