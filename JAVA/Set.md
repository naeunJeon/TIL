# Set 인터페이스
Set 인터페이스은 중복되는 것을 방지하고 원하는 값이 포함되어 있는지를 확인하는 것이 주 용도이다. 또한 List와 달리 순서를 유지하지 않기 때문에 저장한 순서대로 출력되지 않는다.

## HashSet
### 1. HashSet 상속관계
java.lang.Object<br>&nbsp;└─
java.lang.Abstractcollection<E><br>&nbsp;&nbsp;&nbsp;└─ java.util.AbstractSet<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.HashSet<E><br>
AbstractSet을 확장했으며 중복을 체크하는 **equals()**와 **hashCode()** 가 구현되어 있다.

### 2. HashSet 생성자
- `HashSet( )` : 데이터를 저장할 수 있는 16개의 공간과 0.75의 로드팩터를 갖는 객체를 생성한다.
- `HashSet(Collection<? extends E> c)` : 매개변수로 받은 컬렉션 객체의 데이터를 HashSet에 담는다.
- `HashSet(int initialCapacity)` : 매개변수로 받은 개수만큼의 데이터 저장 공간과 0.75의 로드팩터를 갖는 객체를 생성한다.<br>
(로드팩터 : **데이터의개수/저장공간**)

### 3. HashSet 관련 메소드
- `boolean add(E e)` : 데이터를 추가한다.
- `void clear()` : 저장된 모든 객체를 삭제한다.
- `Object clone()` : HashSet 객체를 복제한다. 하지만 담겨있는 데이터를 복제하지 않는다.
- `boolean contains(Object o)` : 저장한 객체가 존재하는지를 확인한다.
- `boolean isEmpty()` : 데이터가 있는지 확인한다.
- `Iterator<E> iterator()` : 데이터를 꺼내기 위한 Iterator 객체를 리턴한다.
- `boolean remove(Object o)` : 지정된 객체를 HashSet에서 삭제한다.
- `int size()` : 데이터의 개수를 리턴한다.

```java
public void printCarSet(HashSet<String> carSet){
    Iterator<String> iter=carSet.iterator();
    while(iter.hasNext()){
        System.out.print(iter.next()+ " ");
    }
}
```
 **iterator()** 라는 메소드를 사용하여 Iterator 객체를 생성<br>
 **hasNext()** 라는 메소드를 사용하여 다음 데이턱 존재하는지를 확인<br>
 **next()** 라는 메소드를 사용하여 다음 값을 얻어낸다.

## Set 비교
- **HashSet** : 순서가 전혀 필요 없는 데이터를 hash table에 저장한다.
- **TreeSet** : 저장된 데이터의 값에 따라서 정렬되는 셋이다. red-black이라는 트리타입으로 값이 저장된다.
- **LinkedHashSet** : 연결된 목록 타입으로 구현된 hash table에 데이터를 저장한다. 저장된 순서에 따라서 값이 정렬된다.<br>
- 성능은 `HashSet, TreeSet, LinkedHashSet` 순으로 빠르다.
