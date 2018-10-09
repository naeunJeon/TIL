# 자바 컬렉션(Java Collection)
자바에서 컬렉션은 목록성 데이터를 처리하는 자료구조를 통칭한다.

- 순서가 있는 목록인 **List**형
- 순서가 중요하지 않은 목록인 **Set**형
- 먼저 들어온 것이 먼저 나가는 **Queue**형
- keyp-value으로 저장되는 **Map**형


자바에서 List, Set, Queue는 Collection이라는 인터페이스를 구현하고 있다. 이 Collection인터페이스는 **java.util 패키지** 에 선언되어 있으며 여러 개의 객체를 하나의 객체에 담아 처리할 때 공통적으로 사용되는 여러 메소드들을 선언해 놓았다. Map만 유일하게 Collection과는 관련이 없다. 

```java
public interface Collection<E> extends Iterable<E>
```
이 Collection 인터페이스 선언문에서는 `Iterable<E>`라는 인터페이스를 확장했고 **Iterable** 인터페이스에 선언되어 있는 메소드는 iteratior() 하나 뿐이다.<br> 따라서 Collection인터페이스가 Iterable 인터페이스를 확장했다는 의미는, Iterator 인터페이스를 사용하여 데이터를 순차적으로 가져 올 수 있다는 의미이다.