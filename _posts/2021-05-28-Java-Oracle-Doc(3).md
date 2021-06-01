---
title: ☕️ [Java] Oracle 매뉴얼 번역 (3)
author: Yon Kim
date: 2021-05-28 15:00:00 +0900
categories: [☕️Java, Java-Oracle Official Manual]
tags: [java, 변수이름규칙]
---



**👀 본 포스팅은 Oracle-Java Documentation 원문을 의역한 내용입니다.(오역이 있을 수 있음)** 


<br><br>

# **Variables**

## `🧭Recall`

- 🧙‍♂️ ****

<br><br>

## `📜Note`

### Java 프로그래밍 언어에서는 `"필드(field)"` 와 `"변수(variables)"` 라는 용어가 둘 다 사용된다. Java에서는 변수의 종류를 다음과 같이 정의한다.
<br>

* ### **인스턴스 변수: Instance Variables (Non-Static Fields)**
> 엄밀히 말하면, 객체는 각각의 상태를 "비정적 필드" 즉, 정적 키워드 없이 선언된 필드에 저장한다. 비정적 필드는 클래스의 각 인스턴스(즉, 각 개체)에 고유한 값이기 때문에 인스턴스 변수라고도 한다. <p>예를 들어 한 자전거의 현재 속도는 다른 자전거의 현재 속도와 독립적이다.</p>

<br>

* ### **클래스 변수: Class Variables (Static Fields)**
> <p>클래스 변수는 정적 수식어로 선언된 모든 필드이며, 이것은 컴파일러에게 클래스가 인스턴스화된 횟수에 관계없이 이 변수의 복사본이 정확히 한 개 존재한다는 것을 알려준다.</p>예를 들어, 특정 종류의 자전거에 대한 기어 수를 정의하는 필드는 개념적으로 모든 경우에 동일한 수의 기어가 적용되기 때문에 정적 키어로 표시될 수 있다. static intnumGears = 6; 코드는 이러한 정적 필드를 생성한다. 또한 'final' 키워드를 추가하여 기어 수가 편하지 않음을 나타낼 수 있다.

<br>

* ### **로컬 변수: Local Variables**
><p>개체가 지닌 상태를 필드에 저장하는 것과 같이, 메소드 역시 일시적인 상태를 로컬 변수에 저장한다. 로컬 변수를 선언하는 것은 필드를 선언하는 것과 비슷한 형태를 띈다(int count =0;)</p> 어떠한 변수를 로컬로 지정하는 키워드는 따로 없다. 로컬 변수가 결정되는 것은 전적으로 변수가 선언된 위치(메소드의 열기-닫기 중)에서 나온다. 따라서 로컬 변수는 선언된 메소드에서만 볼 수 있으며 나머지 클래스들에서는 액세스할 수 없다.

<br>

* ### **매개변수(파라미터): Parameters**
><p>매개변수의 대표적인 예시는 "Hello World!"의 main 메소드에서 발견할 수 있다. main 메소드의 시그니처 형태는 public static void main(String[] args)로, args 변수가 바로 이 메소드의 매개변수이다. 매개변수에 대해 주의해야 할 점은, 매개변수는 언제나 "변수"로 분류된다(필드가 아님) </p>

<br>

* ### **정리**

```java
    
    일반적으로 "필드" 라 하면, 로컬 변수와 매개 변수를 제외한 단순 "필드"를 의미한다.
    만약 로컬 변수와 매게 변수를 포함하면 "변수" 라고 부르면 된다. 
    그렇기 때문에 'static field', 'local variables' 와 같이 구체적으로 명명하여 사용한다.

    또한 "멤버(member)" 는 타입의 필드, 메소드 및 중첩된 타입을 "멤버" 라고 한다.
```

<br><br>

## **변수 이름 규칙(Naming)**
---



 * ### **모든 프로그래밍 언어는 사용자가 쓸 수 있는 이름의 종류에 대한 규칙이 있다. 변수 이름을 지정하는 규칙은 다음과 같이 요약할 수 있다.**
 

 ```java
    // 변수 이름 규칙 (1)
    
    변수 이름은 "대소문자"를 구분한다
    "유니코드 문자" 및 "숫자", "문자", "달러기호($)" 
    또는 "_" 을 포함하는 이름이 가능하다

    변수의 시작은 언제나 "문자"로 시작해야 하며, 
    "달러기호($)"는 관례상 전혀 사용되지 않는다.
    "_" 는 관례상 변수 이름의 시작위치에 사용되지 않는다.
    "공백"을 사용할 수 없다
 ```

 ```java

    // 변수 이름 규칙 (2)
    
    변수 이름을 선택할 때는 약어 대신 전체 단어를 사용할 것(직관성/가독성)
    대부분의 경우 코드 자체를 문서화한다.

    예를 들어 cadence, speed, gear 라는 필드는 s,c,g 같은 약어 버전보다 훨씬 직관적이다.
    또한 선택한 이름은 키워드 또는 Java에서 예약된 단어가 아니어야 한다.

    // Java Language Keywords(예약어)

    abstract    	continue	for	    new	    switch
    assert	default	goto	package	synchronized
    boolean	do	if	private	this
    break	double	implements	protected	throw
    byte	else	import	public	throws
    case	enum	instanceof	return	transient
    catch	extends	int	short	try
    char	final	interface	static	void
    class	finally	long	strictfp	volatile
    const*	float	native	super	while

 ```

 ```java
 
    // 변수 이름 규칙 (3)

    만약 변수 이름이 한 단어라면, 모든 철자를 소문자로 작성할 것        
    (ex. math)

    두 단어 이상이라면, 두 번째 단어의 첫 번째 글자를 대문자로 작성할 것
    (ex. mathExample)

    지정 값을 포함하는 변수라면, 모든 단어를 대문자로 작성하고 단어 사이에 "_"를 추가할 것
    중요: 이 경우를 제외한 어떠한 경우에도 변수명에 "_"가 사용되지 않는다.
    (ex. static final int NUM_GEARS = 6)

 ```
