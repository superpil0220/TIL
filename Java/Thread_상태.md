# 쓰레드의 상태
1. new : 쓰레드가 생성되고 아직 start()가 호출되지 않은 상태
1. sunnable : 실행 중 또는 실행 가능한 상태
1. blocked : 동기화블럭에 의해서 일시정지된 상태(lock이 풀릴 때까지 기다리는 상태)
1. waiting, time_waiting : 쓰레드의 작업이 종료되지는 않았지만 실행가능하지 않은 일시정지상태, time_waiting은 일시정지시간이 지정된 경우를 의미
1. terminated : 쓰레드의 작업이 종료된 상태

# 쓰레드 라이프사이클
* new로 Thread를 생성 → start()를 호출하면 → 실행대기상태로 빠진다 → 자기 순서가 되면 실행 → 자기가 할당받은 실행 시간이 끝나면 다시 실행대기 상태로 빠짐 →다시 자기 순서가 되면 실행 → 이렇게 반복하다가 stop()이 호출되거나 모든 작업이 끝난경우 소멸된다.
* suspend(), sleep()등으로 thread를 일시 정지 할 수 있다.

# 쓰레드 실행제어
1. static void sleep(long millis) : 현재 쓰레드를 지정된 시간동안 일시정지 시킨다.
1. void join() : 다른 쓰레드을 기다린다.
1. void interrupt() : sleep(), join()에 의해 일시정지상태인 다른 쓰레드를 깨운다.
1. stop() : 쓰레드를 즉시 종료시킨다.
1. suspend() : 쓰레드를 일시정지시킨다. resume()을 호출하면 다시 실행대기상태가 된다.
1. resume() : suspend()에 의해 일시정지상태에 있는 쓰레드를 실행대기상태로 만든다.
1. static void yield() : 실행 중에 자신에게 주어진 실행시간을 다른 쓰레드에게 양보하고 자신은 실행대기상태가 된다.

# 참고자료
1. https://www.youtube.com/watch?v=W0v3Gwx92hc&list=PLW2UjW795-f6xWA2_MUhEVgPauhGl3xIp&index=152
