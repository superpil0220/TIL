# main 쓰레드
```java
public class supepril {
	public static void main(String[] args) {
		System.out.println("Hello Superpil");
	}
}
```
* main메서드의 코드를 수행하는 쓰레드
* 쓰레드는 “사용자 쓰레드”, “데몬 쓰레드” 두 종류가 있다.
* 사용자 쓰레드는 메인쓰레드고 메인쓰레드를 보조해주는게 데몬 쓰레드다.
* 실행 중인 “사용자 쓰레드”가 하나도 없을 때 프로그램은 종료된다.
* 데몬 쓰레드는 보조 쓰레드라서 있어도 프로그램은 종료될 수 있다.

```java
public static void main(String[] args) {
  SpringApplication.run(SpringDemoApplication.class, args);

  ThreadDemo1 threadDemo1 = new ThreadDemo1();
  threadDemo1.start();

  ThreadDemo2 threadDemo2 = new ThreadDemo2();
  Thread thread = new Thread(threadDemo2);
  thread.start();

  System.out.println("Thread Name : " + Thread.currentThread().getName());
}

static class ThreadDemo1 extends Thread {

  public void run() {
    for (int i = 0; i < 5; i++) {
      System.out.println("11111111111 : " + this.getName());
    }
  }
}

static class ThreadDemo2 implements Runnable {

  @Override
  public void run() {
    for (int i = 0; i < 5; i++) {
      System.out.println("2222222222 : " + Thread.currentThread().getName());
    }
  }
}
```
* main쓰레드가 종료되어도 threadDemo1, threadDemo2 쓰레드가 살아있으면 프로그램은 종료되지 않는다.
* 모든 쓰레드가 작업이 종료되면 프로그램도 종료된다.

# 싱글 쓰레드와 멀티 쓰레드
```java
public static void main(String[] args) {
  SpringApplication.run(SpringDemoApplication.class, args);

  for (int i = 0; i < 5; i++) {
    System.out.println("1");
  }

  for (int i = 0; i < 5; i++) {
    System.out.println("2");
  }
}

/*
1
1
1
1
1
2
2
2
2
2

*/
```
* 싱글쓰레드 예제다.
* 첫번째 반복문이 모두 끝나면 두번째 반복문이 실행된다.

```java
public static void main(String[] args) {
  SpringApplication.run(SpringDemoApplication.class, args);
  
  ThreadDemo1 threadDemo1 = new ThreadDemo1();
  threadDemo1.start();

  ThreadDemo2 threadDemo2 = new ThreadDemo2();
  Thread thread = new Thread(threadDemo2);
  thread.start();

  System.out.println("Thread Name : " + Thread.currentThread().getName());
}

static class ThreadDemo1 extends Thread {

  public void run() {
    for (int i = 0; i < 5; i++) {
      System.out.println("11111111111 : " + this.getName());
    }
  }
}

static class ThreadDemo2 implements Runnable {

  @Override
  public void run() {
    for (int i = 0; i < 5; i++) {
      System.out.println("2222222222 : " + Thread.currentThread().getName());
    }
  }
}
```
* 첫번째 반복문과 두번째 반복문이 순차적으로 실행되지 않고 os스케줄러에 정한 순서로 실행된다.
* 싱글 쓰레드보다 멀티 쓰레드일경우 실행 시간이 더 걸린다.
* 멀티 쓰레드는 첫번째 반복문을 실행하다가 두번째 반복문을 실행하기 위해 작업을 전환시키는 시간이 필요하기 때문이다.
즉, context switching이 발생된다.
* 멀티 쓰레드가 싱글 쓰레드보다 상대적으로 시간이 걸려도 여러 작업을 동시에 할 수 있다는 이점을 가지고있다.

# 참고자료
1. https://www.youtube.com/watch?v=2eJc9ZdRe2c&list=PLW2UjW795-f6xWA2_MUhEVgPauhGl3xIp&index=150

