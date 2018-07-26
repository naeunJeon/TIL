# 제네릭(Generic)
제네릭은 JDK1.5부터 도입되어 메소드나 클래스에서 사용되는 객체의 다양한 타입들을 컴파일시 타입체크 수행한다.

- 객체의 타입 안정성을 제공
- 반환값에 대한 타입체크와 형변환을 생략할 수 있어 코드가 간결해짐<br>
(타입 안정성을 높인다는 것은 의도하지 않은 타입의 객체를 저장하거나 저장된 객체를 꺼내 올때 원래의 타입과 다른 타입으로 형변환되어 발생하는 오류를 줄여 준다는 것이다.)

```java
class Person<T>{
    public T info;
}
Person<String> p1 = new Person<String>();
Person<StringBuilder> p2 = new Person<StringBuilder>();
```
클래스 Person의 'T'는 데이터 타입이 아닌 어떠한 참조형 타입이 가능하다는 의미이다. 따라서 p1.info와 p2.info의 데이터 타입은 'T'가 아니라 인스턴스 생성시 < >안에 지정해준 String과 StringBuilder가 된다.
타입을 지정하지 않으면 Object타입으로 간주된다.

1. 제네릭의 선언 및 생성<br>
**컬랙션클래스<저장할 객테의 타입> 변수명 = new 컬랙션클래스<저장할 객테의 타입>()**
```java
ArrayList<Tv> tvList = new ArrayList<Tv>();
tvList.add(new Tv());
tvList.add(new Audio());    //컴파일 에러 발생 !!
```
Java SE 7부터는 인스턴스 생성시 타입을 추정할 수 있는 경우에는 아래와 같이 타입을 생략할 수 있음
```java
ArrayList<Tv> tvList = new ArrayList<>();
```

2. 다형성을 사용해야하는 경우
```java
class product{}
class Tv extends Product{}
class Audio extends Product{}

ArrayList<product> list = new ArrayList<Product>();
list.add(new Product());
list.add(new Tv());
list.add(new Audie());

Product p = list.get(0);        //형변환이 필요없음
Tv t = (Tv)list.get(1);         //형변환이 필요
```
<>에 부모타입을 지정하면 여러 종류의 객체를 저장할 수 있다. ArrayList가 Product타입의 객체를 저장하도록 지정하면 이들의 자식인 Tv와 Audio 타입의 개체도 저장할 수 있다. 꺼내올 때만 원래의 타입으로 형변환해주면 된다.