---
title: ☕️ [Java] Oracle 매뉴얼 번역 (1)
author: Yon Kim
date: 2021-05-19 20:00:00 +0900
categories: [☕️Java, Java-Oracle Official Manual]
tags: [java]
---



**👀 본 포스팅은 Oracle-Java Documentation 원문을 의역한 내용입니다.(오역이 있을 수 있음)** 


<br><br>

**클래스란?**
============


현실 세계에서, 우리는 같은 종류의 서로 다른 객체들을 자주 발견할 수 있습니다.

수 천가지 종류의 "자전거" 처럼요. 각각의 자전거들은 약간씩 차이는 있지만, 

"자전거"의 기본 뼈대가 같고, 공통된 종류의 부품이 들어갑니다. (패달, 기어, 안장 등)

객체지향 프로그래밍에서 이러한 "자전거"라는 하나의 `인스턴스`는 

자전거를 이루는 `객체들의 클래스`로 이루어져있다고 말할 수 있는데요. 

클래스는 개별 객체가 생성되는 청사진 같은 것입니다.

<br><br>

**What Is a Class?: 클래스란?**
------------

<br>


아래의 `자전거(Bicycle) 클래스` 는 자전거가 구현 가능한 기능들을 포함하고 있습니다.

```java

class Bycicle {

		int cadence = 0; // 자전거의 패달 rpm
		int speed = 0;   // 자전거의 속도
		int gear = 1;    // 자전거의 기어

		void changeCadence(int newValue) {
				 cadence = newValue;
		}

		void speedUp(int increment) {
				 speed = speed + increment;
		}

		void applyBrakes(int decrement) {
				 speed = speed - decrement;
		}

		void printStates() {
				 System.out.println("cadence:" + cadence + "speed:" + speed + "gear:" + gear);
		}
	}
```

<br>

지금 당장, 위와 같은 자바 문법은 낯설 수 있어요.

하지만 자전거(Bycicle)의 클래스는 우리가 앞서 이야기했던 자전거 객체를 기초로 만들어졌습니다.

`cadence(패달 rpm)`, `speed(속도)`, `gear(기어)` 필드는 객체(자전거)의 상태를 나타내고,

`changeCadence(패달 rpm 변경)`, `speedUp(속도 변경)`, `changeGear(기어 변경)`과 같은 메소드들은

바깥 세상과 어떻게 상호작용할지 정의하죠

<br>

`자전거(Bicycle) 클래스` 가 `main` 메소드를 포함하지 않고 있다는 사실을 눈치채셨나요?

그 이유는, 위 소스코드는 완전한 어플리케이션 형태가 아니기 때문입니다.

어플리케이션에서 "사용이 될 수도 있는 `자전거`" 에 대한 청사진을 만들어 놓은 것이죠.

새로운 자전거 객체를 만들고, 사용하는 것에 대한 책임은 우리가 만드는 어플리케이션의 다른 클래스에 있을 것입니다.

아래는 두 개의 서로 다른 `자전거`의 메소드를 발동시키는 `자전거 데모(Bicycle Demo)` 클래스입니다.
<br>
<br>

```java
class Bicycle eDemo {
	public static void main(String[] args) {

	// Create two different
	// Bicycle objects
	Bicycle bike1 = new Bicycle();
	Bicycle bike2 = new Bicycle();

	// Invoke method on
	// those objects
	bike1.changeCadence(50);
	bike1.speedUp(10;
	bike1.changeGear(2);
	bike1.printStates();

	bike2.changeCadence(50);
	bike2.speedUp(10);
	bike2.changeGear(2);
	bike2.changeCadence(40);
	bike2.speedUp(10);
	bike2.changeGear(3);
	bike2.printStates();
	}
}
```

위 소스코드를 테스트 해 보면, 두 자전거의 최종 rpm, 속도, 그리고 기어가 출력됩니다.

```java
cadence:50 speed:10 gear:2
cadnece:40 speed:20 gear:3
```