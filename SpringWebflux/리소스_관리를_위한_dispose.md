# dispose
* subscribe를 취소할 수 있다.
* dispose는 구독을 취소하는 것이 아니라, 구독자가 이벤트를 받는 것을 중지하는 역할을 한다.
* dispose를 호출하더라도 Flux가 중지되는 것을 보장되지 않는다.

```java
Flux<Long> flux =
        Flux
          .interval(Duration.ofSeconds(1))
	        .doOnComplete(() -> log.info("doOnComplete"));

Disposable subscribe1 = flux.subscribe(data -> log.info("data1 : {}", data));
Thread.sleep(5000);
subscribe1.dispose();

/*
data1 : 0
data1 : 1
data1 : 2
data1 : 3
data1 : 4
*/
```
* interval로 1초에 한번씩 숫자가 발행된다.
* thread를 5초동안 잠들게하고 이후 subscribe1를 dispose를 사용해 구독을 취소시킨다.
* 더이상 subscribe1은 데이터를 받을 수 없다.
* 구독이 완료되었기 때문에 flux의 doOnComplete가 실행되지 않을까? 아니다. 
* dispose는 구독을 취소하는게 아니라 구독자가 이벤트를 받는 것을 중지하는 역할을 하기 때문에 flux는 발행이 완료된 상태가 아니라서 doOnComplete가 실행되지 않는다.
* 비유하면, 스트림을 라디오 방송으로, 구독자를 라디오 수신기로 생각해보세요. 라디오 방송은 계속해서 신호를 전송하고 있습니다. 라디오 수신기를 켜면 방송을 들을 수 있고, 라디오 수신기를 끄면 방송을 듣지 못하게 됩니다. 하지만 이것은 방송이 중단된 것이 아니라, 단지 우리가 그것을 듣지 못하게 된 것뿐입니다. 방송 자체는 계속해서 진행되고 있습니다.
이것이 바로 dispose()가 하는 일입니다.
dispose()를 호출하면 구독자는 더 이상 스트림에서 데이터를 수신하지 않습니다.
하지만 이것은 스트림이 완료되었다는 것을 의미하지 않습니다.
스트림은 여전히 데이터를 생성하고 있을 수 있습니다.
이것은 dispose()가 구독을 취소하는 것이지, 스트림을 중단하는 것이 아니라는 것을 의미합니다.
따라서 doOnComplete() 콜백은 스트림이 완료되었을 때만 호출되므로, dispose()를 호출한 후에는 호출되지 않습니다. 왜냐하면 dispose()는 스트림을 완료하는 것이 아니라, 구독자가 더 이상 데이터를 수신하지 않도록 하는 것이기 때문입니다.

# TODO
- [ ] Disposables.swap(), Disposables.composite(…) 공부필요   

# 참고자료
1. https://projectreactor.io/docs/core/release/reference/#_from_imperative_to_reactive_programming

