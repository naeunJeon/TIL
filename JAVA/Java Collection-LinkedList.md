# LinkedList(연결리스트)
```java
class{
    Node next;      //다음 요소의 주소를 저장
    Object obj;     //데이터를 저장
}
```
LinkedList의 각 요소들은 자신과 연결된 다음 요소에대한 참조(주소값)와 데이터로 구성되어 있다.

### 1. LinkedList 클래스의 상속관계<br>
java.lang.Object<br>&nbsp;└─
java.lang.Abstractcollection<E><br>&nbsp;&nbsp;&nbsp;└─ java.util.AbstractList<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.AbstractSequentialList<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.LinkedList<E>

### 2. LinkedList 생성자
- `LinkedList()` : 비어 있는 LinkedList 객체를 생성한다.
- `LinekdList(Collection<? extends E> c)` : 매개변수로 받은 컬랙션 객체의 데이터를 LinkedList에 담는다.

### 3. LinkedList에 데이터 담기
- `void add(int index, E e)` : 매개변수로 넘어온 데이터를 지정된 index 위치에 담는다.
 - `boolean addAll(Collection<? extends E> c)` : 매개변수로 넘어온 컬렉션 데이터를 가장 끝에 담는다.
 - `boolean addAll(int index, Collection<? extends E> c)` : 매개변수로 넘어온 컬렉션 데이터를 index에 기정된 위치부터 담는다.
 - `void addFirst(E e)` : 매개변수로 넘어온 데이터를 LinkedList의 첫 번째 요소 앞에 추가한다.
 - `void addLast(E e)` : 매개변수로 넘어온 데이터를 LinkedList의 마지막 요소 뒤에 추가한다.


### 4. LinkedList 데이터 삭제
 - `void clear()` : 모든 데이터를 삭제
 - `Object remove()`<br>
 - `Object removeFirst()`<br>
 - `object pop()`<br>
 : LinkedList의 가장 앞에 있는 데이터를 삭제하고 리턴한다.
 - `Object remove(int index)` : index에 위치한 데이터를 삭제하고 삭제한 데이터를 리턴한다.
 - `boolean remove(Object o)` : 매개변수에 넘어온 객체와 동일한 첫번째 데이터를 삭제
 - `Object removeFirst()` :  LinkedList의 첫 번째 요소를 삭제
 - `Object removeLast()` :  LinkedList의 마지막 요소를 삭제


### 5. LinkedList 데이터 꺼내기
 - `Object getFirst()`<br>
 - `Object peek()`<br>
 - `Object peekFirst()`<br>
 - `Object element()`<br>
 : LinkedList의 맨 앞에 있는 데이터를 리턴한다.
 - `Object getLast()`<br>
 - `Object peekLast()`<br>
 : LinkedList의 맨 뒤에 있는 데이터를 리턴한다.
 - `Object get(int index)` : index에 위치한 데이터를 리턴한다.

### 6. Doubley LinkedList(이중연결리스트)
```java
class{
    Node next;      //다음 요소의 주소를 저장
    Node previous;  //이전 요소의 주소를 저장
    Object obj;     //데이터를 저장
}
```
- 단순히 링크드리스트에 참조변수를 하나 더 추가하여 다음 dy소에 대한 참조뿐 아니라 이전 요소에 대한 참조가 가능하도록 했다.
- 링크드리스트보다 각 요소에 대한 접근과 이동이 쉽기 때문에 링크드리스트보다 더 많이 사용된다.

### 7. Doubley Circular LinkedList(이중원형연결리스트)
- 더블 링크드리스트의 접근성을 보다 향상시킨 것으로 더블링크드리스트의 첫번째 요소와 마지막 요소를 서로 연결시킨 것이다.
- 링크드리스트의 단점인 낮은 접근성을 높이기 위함이다. 