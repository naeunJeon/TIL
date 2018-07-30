# List 인터페이스
List 인터페이스는 Collection인터페이스를 확장하였다. Collection을 확장한 다른 인터페이스와 List 인터페이스의 가장 큰 차이점은 배열처럼 **순서**가 있다는 것이다.<br>

List 인터페이스를 구현한 클래스들 중에 java.util 패키지에서는 **ArrayList, Stack, LinkedList**를 가장 많이 사용한다.

## ArrayList
```java
import java.util.ArrayList;     //import문을 추가하고 사용하자
```
### 1. ArrayList 클래스의 상속관계<br>
java.lang.Object<br>&nbsp;└─
java.lang.Abstractcollection<E><br>&nbsp;&nbsp;&nbsp;└─ java.util.AbstractList<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.ArrayList<E>

### 2. ArrayList 생성자
 - `ArrayLsit( )` : 객체를 저장할 공간이 10개인 ArrayList를 만듦
 - `ArrayList( Collection<? extends E> c )` : 대부분의 ArrayList는 서로 다른 종류의 객체를 하나의 배열에 넣지 않고 한가지 종류의 객체만 저장한다. 따라서 이 생성자를 사용하여 선언하는 것이 권장된다.
 ```java
ArrayList<String> list = new ArrayList<String>();       //String만 담는 ArrayList 생성
```
 - `ArrayList( int initialCapacity ) `: 매개변수 initialCapacity 개수만큼 저장공간을 갖지만 잘 사용되지 않음

 ### 3. ArrayList에 데이터 담기
 - `boolean add(E e)` : 매개변수로 넘어온 데이터를 가장 끝에 담는다.
 - `void add(int index, E e)` : 매개변수로 넘어온 데이터를 지정된 index 위치에 담는다.
 - `boolean addAll(Collection<? extends E> c)` : 매개변수로 넘어온 컬렉션 데이터를 가장 끝에 담는다.
 - `boolean addAll(int index, Collection<? extends E> c)` : 매개 변수로 넘어온 컬렉션 데이터를 index에 기정된 위치부터 담는다.
 
 ```java
ArrayList<String> list = new ArrayList<String>();
list.add("A");
list.add("B");
list.add("C");

ArrayList<String> list2 = list;     //치환 수행
list2.add("test");                  //list, list2 모두 "test" 값이 추가된다.
``` 
 위와 같이 치환을 수행한다면 원본 객체의 값만 사용하겠다는 것이 아니라 참조되고 있는 주소까지도 사용하겠다는 말이다. 따라서 Collection 관련 객체를 복사할 일이 있을 떄에는 `addAll()` 메소드를 사용하면 된다.


  ### 4. ArrayList에 데이터 꺼내기
  - `int size()` : ArrayList 객체에 들어가 있는 데이터의 개수를 리턴한다.<br>
  (배열.length는 배열의 저장공간 개수를 의미하지만, size()는 ArrayList에 들어가있는 데이터 개수를 의미한다.)
  - `get(int index)` : index에 위치한 데이터를 리턴한다.
  - `int indexOf(Object o)` : 매개변수로 넘어온 객체와 동일한 데이터의 위치를 리턴한다.
  - `int lastIndexOf(Obejct o)` : 매개변수로 넘어온 객체와 동일한 마지막 데이터의 위치를 리턴한다.
  - `toArray(T[] a)` : ArrayList 객체에 있는 값들을 매개 변수로 넘어온 T타입의 배열로 만든다.  
  ```java
  String[] strList = list.toArray(new String[0]);
  ```
  ### 4. ArrayList 데이터 삭제
- `void clear()` : 모든 데이터를 삭제
- `E remove(int index)` : index에 위치한 데이터를 삭제하고 삭제한 데이터를 리턴한다.
- `boolean remove(Object o)` : 매개변수에 넘어온 객체와 동일한 첫번째 데이터를 삭제
- `removeAll(Collection<?> c)` : 매개변수로 넘어온 컬렉션 객체에 있는 데이터와 동일한 모든 데이터를 삭제

 ### 5. ArrayList 데이터 변경
- `set(int index, E element)` : index에 위치한 데이터를 두번째 매개변수로 넘긴 값으로 변경한다. 그리고 해당 위치에 있던 데이터를 리턴한다.


## Stack
### 1. Stack 클래스의 상속관계<br>
java.lang.Object<br>&nbsp;└─
java.lang.Abstractcollection<E><br>&nbsp;&nbsp;&nbsp;└─ java.util.AbstractList<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.Vector<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.Stack<E>

### 2. Stack 생성자
- `Stack()`: 아무 데이터도 없는 Stack객체를 만든다.


### 3. Stack 관련 메소드
- `boolea empty()` : 객체가 비어있는지 확인
- `peek()` : 객체의 가장 위에있는 데이터를 리턴한다.
- `pop()` : 객체의 가장 위에 있는 데이터를 지우고 리턴한다.
- `push(E item)` : 매개변수로 넘어온 데이터를 가장 위에 저장한다.
- `int search(Object o)` : 매개변수로 넘어온 데이터의 위치를 리턴한다.

참고) **Arraylist**와 **Vector**는 크기확장이 가능한 배열이라고 생각할 수 있다. 따라서 사용법과 기능은 거의 동일하다. 이 둘의 차이점은 ArrayList는 Thread Safe 하지 않고 Vector 는 Thread Safe하다는 것이다.
