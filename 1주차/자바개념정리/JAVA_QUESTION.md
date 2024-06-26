
# 자바 핵심 개념 정리 1
<details>
<summary>Java에서 제공하는 원시 타입들에 무엇이 있고, 각각 몇 바이트를 차지하나요?</summary>
<div markdown="1">
- cf) 원시타입: 실제 데이터 값을 저장하는 타입 vs 참조타입: 메모리 번지 값을 통해 객체를 참조하는 타입 <br/>
1. boolean: 1바이트 <br/>
2. char: 2바이트 <br/>
3. byte: 1바이트 <br/>
4. short: 2바이트 <br/>
5. int: 4바이트 <br/>
6. long: 8바이트 <br/>
7. float: 4바이트 <br/>
8. double: 8바이트 <br/>
- 1: 논리형 <br/>
- 2: 문자형 <br/>
- 3-6: 정수형 <br/>
- 7-8: 실수형 <br/>
</div>
</details>
<br>

<details>
<summary>오버라이딩(OverRiding)과 오버로딩(OverLoading)에 대해 설명해주세요.</summary>
<div markdown="1">
오버로딩: 한 클래스 내에 이미 사용하려는 이름과 같은 이름을 가진 메소드가 있더라도, 매개변수의 개수 또는 타입이 다르면, 같은 이름을 사용해서 메소드를 정의할 수 있다. (리턴값만 다른 경우에는, 오버로딩 불가능) <br/>
오버라이딩: 부모 클래스로부터 상속받은 메소드를 자식 클래스에서 재정의하는 것, 상속받은 메소드를 자식 클래스에서 상황에 맞게 변경해서 사용해야할 때 활용 가능. 메소드의 이름, 매개변수, 리턴 값이 모두 같아야 한다. <br/>
</div>
</details>
<br>

<details>
<summary>객체지향 프로그래밍(OOP)에 대해 설명해주세요</summary>
<div markdown="1">
객체지향프로그래밍: 객체지향 프로그래밍은 실세계에 존재하고 인지하고 있는 객체(Object)를 소프트웨어의 세계에서 표현하기 위해 객체의 핵심적인 개념 또는 기능만을 추출하는 추상화(abstraction)를 통해 모델링하려는 프로그래밍 패러다임을 말한다. <br/>
</div>
</details>
<br>

<details>
<summary>추상 클래스와 인터페이스에 대해 설명해주시고, 차이에 대해 설명해주세요.</summary>
<div markdown="1">
- 추상클래스: 하나 이상의 추상 메소드를 포함하는 클래스 <br/>
( 추상 메소드: 자식 클래스에서 반드시 **오버라이딩해야만** 사용할 수 있는 메소드. 사용하는 목적은 추상 메소드가 포함된 클래스를 상속받는 자식 클래스가 **반드시 추상 메소드를 구현하도록** 하기 위함. (문법: abstract 반환타입 메소드이름(); ← 구현부 없이 **선언부만 존재**) ) <br/>
- 인터페이스: 다른 클래스를 작성할 때 기본이 되는 틀을 제공하면서, 다른 클래스 사이의 중간 매개 역할까지 담당하는 일종의 추상 클래스. 다중 상속시 발생하는 문제(ex 메소드 출처의 모호성)를 막기 위해, 자바에서는 다중상속을 허용하지 않음. → 다중상속의 이점은 취하기 위해, 인터페이스를 통해 다중 상속을 지원 <br/>

</div>
</details>
<br>

<details>
<summary>가비지 컬렉션(gc)란 무엇일까요?</summary>
<div markdown="1">
Heap 영역에서 동적으로 할당했던 메모리 중 필요 없게 된 메모리 객체를 모아 주기적으로 제거하는 프로세스
</div>
</details>
<br>

<details>
<summary>JVM의 동작 방식에 대해 설명해 주세요.</summary>
<div markdown="1">
- JVM의 동작 방식: 실제 컴퓨터로 부터 JAVA 어플리케이션 실행을 위한 메모리를 할당 받아 Runtime Data Area를 구성한다. JVM은 인터프리터와 JIT 컴파일러를 통해 바이트 코드를 각 운영체제에 맞는 기계어로 해석시켜 실행시키고, 가비지 콜렉터를 통해 어플리케이션의 동적 메모리를 관리한다. <br/>
</div>
</details>
<br>

<details>
<summary>불변 객체란 무엇이고, final은 무엇일까요? 사용하는 이유와 함께 설명해주세요.</summary>
<div markdown="1">
- 불변 객체: 불변 객체란 객체 생성 이후 내부의 상태가 변하지 않는 객체이다. 불변 객체는 read-only 메소드만을 제공하며, 객체의 내부 상태를 제공하는 메소드를 제공하지 않거나 방어적 복사(defensive-copy)를 통해 제공한다. Java의 대표적인 불변 객체로는 String이 있다 <br/>
- final: 여러 컨텍스트에서 단 한 번만 할당될 수 있는 entity를 정의할 때 사용 <br/>
</div>
</details>
<br>

<details>
<summary>자바의 메모리 영역에 대해 설명해주세요.</summary>
<div markdown="1">
1. Static Area(Method Area): 클래스 변수나, static 으로 선언된 것들이 저장됨 <br/>
2. Heap Area: new를 사용해 객체를 생성할 때 or 참조형 데이터 타입이 저장된다. Reference를 통해서만 Heap 영역의 데이터들에 접근, 핸들링 할 수 있다. 가비지 컬렉터에 의해 메모리에서 해제된다. 쓰레드가 몇개가 존재하든, 단 하나의 영역만 존재한다. (≠ Stack) <br/>
3. Stack Area: 기본 자료형(원시 자료형, Primitive type), 지역변수, 매개변수가 저장됨. Heap 영역에 생성된 데이터의 참조값이 할당됨. 메소드가 호출될 때 할당, 메서드 종료시 삭제. Stack 구조이며, 각 쓰레드마다 자신만의 stack을 가진다. <br/>
4. PC Register: 스레드가 생성되면서 생기는 공간. 스레드가 어느 명령어를 처리하고 있는지 그 주소를 등록한다. JVM이 실행하고 있는 현재 위치를 저장하는 역할. <br/>
5. Native Method Stack: Java 가 아닌 다른 언어 (C, C++) 로 구성된 메소드의 실행이 필요할 때 사용되는 공간 <br/>
</div>
</details>
<br>

<details>
<summary>new String()과 리터럴(" ")의 차이에 대해 설명해주세요.</summary>
<div markdown="1">
- new String(): 객체로 생성, Heap메모리 영역에 저장 <br/>
- 리터럴: String constant pool 영역에 생성. 리터럴을 사용하여 생성할 때 constant pool에 같은 값이 존재한다면 생성되는 객체는 이미 존재하고 있는 값을 참조하게 된다. <br/>
</div>
</details>
<br>

<details>
<summary>⭐️ 추가 과제: 람다(lambda)에 대해 알아볼까요?</summary>
<div markdown="1">
 메서드를 "하나의 식"으로 표현한 것. 메서드를 변수처럼 다루는 것을 가능하게 함. <br/>
</div>
</details>
<br>

<details>
<summary>⭐️ 추가 과제: 스트림(stream)에 대해 알아볼까요?</summary>
<div markdown="1">
- 람다를 활용해 배열과 컬렉션을 함수형으로 간단하게 처리할 수 있는 기술. <br/>
- 스트림은 데이터 소스를 추상화하고, 데이터를 다루는데 자주 사용되는 메소드를 정의해 놓아서 데이터 소스에 상관없이 모두 같은 방식으로 다룰 수 있으므로 코드의 재사용성이 높아진다. <br/>
</div>
</details>
<br>
