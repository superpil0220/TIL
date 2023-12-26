# 상황설정
* 극장에서 추첨을 통해 선정된 관람객에게 공연을 무료로 관람할 수 있는 초대장을 발송했다.
* 공연 날 극장 앞은 손에 초대장을 쥐고 입장을 기다리는 이벤트 당첨자들과 표를 구매하려는 관람객으로 장사진을 이루고 있다.
* 관람객 입장 시 이벤트에 당첨된 관람객과 그렇지 못한 관람객은 다른 방식으로 입장해야된다.
* 이벤트에 당첨된 관람객은 초대장을 티켓으로 교환한후에 입장을 할 수 있다.
* 이벤트에 당첨되지 않음 관람객은 티켓을 구매해야만 입장할 수 있다.
* 즉, 관람객을 입장시키기 전에 이벤트 당첨 여부를 확인해야 하고 이벤트 당첨자가 아닌 경우에는 티켓을 판매한 후에 입장시켜야 한다.

# 등장 인물(클래스)
1. 초대장(Invitation)
1. 티켓(Ticket)
1. 관람객(Audience)
1. 관람객의 가방(Bag)
1. 매표소(TicketOffice)
1. 판매원(TicketSeller)
1. 극장(Theater)

# 구현하기
```java
// 초대장
public class Invitation {
	private LocalDateTime when;
}
```
* 공연을 관람할 수 있는 초대일자를 인스턴스 변수로 포함한다.

```java
// 티켓
public class Tickent{
	private Long fee;

	public Long getFee() {
		return fee;
	}
}
```
* 공연을 관람하기 원하는 모든 사람들은  티켓을 소지하고 있어야만 한다.

```java
// 관람객 가방
public class Bag{
	private Long amount;
	private Invitation invitation;
	private Ticket ticket;

	public Bag(long amount) {
		this(null, amount);
	}

	public Bag(Invitation invitation, long amount) {
		this.invitation = invitation;
		this.amount = amount;
	}

	public boolean hasInvitation() {
		return invitation != null;
	}

	public boolean hasTicket() {
		return ticket != null;
	}

	public void setTicket(Ticket ticket) {
		this.ticket = ticket;
	}
	
	public void minusAmount(Long amount) {
		this.amount -= amount;
	}

	public void plusAmount(Long amount) {
		this.amount += amount;
	}
}
```
* 이벤트 당첨자는 티켓으로 교환할 초대장을 가지고 있을 것이다.
* 이벤트에 당첨되지 않은 관람객은 티켓을 구매할 수 있는 현금을 보유하고 있을 것이다.
* 관람객이 가지고 올 수 있는 소지품은 초대장, 현금, 티켓 세 가지뿐이다.
* 관람객은 소지품을 보관할 용도로 가방을 들고 올 수 있다고 가장한다.
* Bag 인스턴스의 상태는 현금과 초대장을 함께 보관하거나, 초대장 없이 현금만 보관하는 두 가지 중 하나일 것이다.

```java
// 관람객
public class Audience {
	private Bag bag;

	public Audience(Bag bag) {
	  this.bag = bag;
	}

	public Bag getBag() {
		return bag;
	}
}
```
* 관람객은 소지품을 보관하기 위해  가방을 소지한다.

```java
// 매표소
public class TicketOffice {
	private Long amount;
	private List<Ticket> tickets = new ArrayList<>();

	public TicketOffice(Long amount, Ticket ...tickets) {
		this.amount = amount;
		this.tickets.addAll(Arrays.asList(tickets));
  }

	public Ticket getTicket() {
		return tickets.remove(0);
	}

	public void minusAmount(Long amount) {
		this.amount -= amount;
	}

	public void plusAmount(Long amount) {
		this.amount += amount;
	}
 }

```
* 관람객이 극장에 입장하기 위해서는 매표소에서 초대장을 티켓으로 교환하거나 구매해야 한다.
* 매표소는 판매하거나 교환해 줄 티켓의 목록과 판매 금액을 인스턴스 변수로 포함한다.
* 티켓을 판매하는 getTicket 메서드는 편의를 위해 tickets컬렉션에서 맨 첫 번째 위치에 저장된 Ticket을 반환하는 것으로 구현했다.

```java
// 판매원
public class TicketSeller {
	private TickeOffice ticketOffice;

	public TickSeller(TicketOffice ticketOffice) {
		this.tickeOffice = ticketOffice;
	}

	public TicketOffice getTicketOffice() {
		return ticketOffice;
	}
}
```
* 판매원은 매표소에서 초대장을 티켓으로 교환해 주거나 티켓을 판매하는 역할을 수행한다.
* 판매원은 매표소를 알고 있어야 한다.

```java
// 극장
public class Theater {
	private TicketSeller ticketSeller;

	public Theater(TicketSeller ticketSeller) {
		this.tickeSeller = ticketSeller;
	}

	public void enter(Audience audience) {
		if(audience.getBag().hasInvitation()) {
			Ticket ticket = ticketSeller.getTicketOffice().getTicket();
			audience.getBag().setTicket(ticket);
		}else{
			Ticket ticket = ticketSeller.getTicketOffice().getTicket();
			audience.getBag().minusAount(ticket.getFee());
			ticketSeller.getTicketOffice().plusAmount(ticket.getFee());
			audience.getBag().setTicket(ticket);
		}
	}
}
```
* 극장이 관람객을 맞이할 수 있도록 enter 메서드를 구현한다.
* 극장은 먼저 관람객의 가방 안에 초대장이 들어 있는지 확인한다.
* 만약 초대장이 들어 있다면 이벤트에 당첨된 관람객이므로 판매원에게서 받은 티켓을 관람객의 가방 안에 넣어준다.
* 가방 안에 초대장이 없다면 티켓을 판매해야 한다.
* 이 경우 극장은 관람객의 가방에서 티켓 금액만클을 차감한 후 매표소에 금액을 증가시킨다.
* 마지막으로 극장은 관람객의 가방 안에 티켓을 넣어줌으로써 관람객의 입장 절차를 끝낸다.
* 작성된 프로그램의 로직은 간단하고 예상대로 동작되지만 몇 가지 문제점을 가지고 있다.
