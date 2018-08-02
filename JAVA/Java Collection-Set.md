# Set 인터페이스
Set 인터페이스의 특징은 중복된 요소를 저장하지 않는 것이다. 또한 List와 달리 순서를 유지하지 않기 때문에 저장한 순서대로 출려되지 않는다.

## HashSet
### 1. HashSet 상속관계
java.lang.Object<br>&nbsp;└─
java.lang.Abstractcollection<E><br>&nbsp;&nbsp;&nbsp;└─ java.util.AbstractSet<E><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─ java.util.HashSet<E><br>
AbstractSet을 확장했으며 중복을 체크하는 `equals()`와 `hashCode()` 가 구현되어 있다.

### 2. HashSet 생성자
- `HashSet( )` : HashSet객체를 생성
- `HashSet(Collection<? extends E> c)` : 주어진 컬렉션을 포함하는 HashSet객체를 생성한다.

### 3. HashSet에 데이터담기
- `boolean add(E e)` : 매개변수 넘어온 값을 담는다.
- `boolean addAll(Collection<? extends E> c)` : 매개변수로 넘어온 컬렉션 데이터를 담는다.

### 4. HashSet에 데이터 꺼내기
- `int size()` : HashSet에 들어가있는 객체의 개수를 반환한다.
- `toArray(T[] a)` : HashSet 객체에 있는 값들을 매개 변수로 넘어온 T타입의 배열로 만든다.

### 5. HashSet 데이터 삭제
- `void clear()` : 저장된 모든 객체를 삭제한다.
- `boolean remove(Object o)` : 지정된 객체를 HashSet에서 삭제한다
- `boolean removeAll(Collection<?> c)` : 매개변수로 넘어온 컬렉션 객체에 있는 데이터와 동일한 모든 데이터를 삭제
- `boolean retainAll(Collection<?> c)` : 매개변수로 넘어온 컬랙션 객체와 동일한 것만 남기고 삭제

