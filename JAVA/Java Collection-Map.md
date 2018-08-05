# Map 인터페이스
- *key-value*로 이루어져있다.
- 모든 데이터는 키와 값이 존재한다.
- 키가 없이 값만 저장될 수 없다.
- 값이 없이 키만 저장될 수 없다.
- 키는 해당 Map에서 고유해야만 한다.
- 값은 Map에서 중복되어도 전혀 상관없다.

## HashMap
### 1.클래스의 상속관계<br>
java.lang.Object<br>&nbsp;└─
java.lang.AbstractMap<K,V><br>&nbsp;&nbsp;&nbsp;└─ java.util.HashMap<K,V><br>

### 2. HashMap 생성자
- `HashMap( )` : 객체를 저장할 공간이 16개인 HashMap을 만듦
- `HashMap( int initialCapacity ) `: 매개변수 initialCapacity 개수만큼 저장공간을 갖는 HashMap 객체를 생성한다.(담을 데이터의 개수가 많은 경우 초기 크기를 지정하는 것을 권장한다.)

 ### 3. HashMap 관련 메소드
 - `V put(K key, V value)` : 첫번째 매개변수인  키를 갖고 두번째 매개변수인 값을 갖는 데이터를 저장한다.
 - `V get(Object Key)` : 매개변수로 넘어온 키에 해당하는 값을 넘겨준다.
 ```java
 public void checkHashMap(){
     HashMap<String, String> map = new HashMap<String, String>();
     map.put("A", "a");
     System.out.println(map.get("A"));         // a 출력됨
     System.out.println(map.get("B"));          // null 출력됨
     map.put("A", "1");
     System.out.println(map.get("A"));         // 1 출력됨
 }
 ```
 Collection에서는 해당 위치에 값이 없을 때는 *ArrayIndexOutOfBoundsException* 예외가 발생한다. 하지만 Map에서는 없는 키로 get()을 할 경우에 null을 리턴한다.<br>
 또한 이미 존재하는 키로 값을 넣을 때는 기존의 값을 새로운 값으로 대치한다.
 - `Set<K> keySet()` : 키의 목록을 Set타입으로 리턴
 - `Collection<V> values()` : 값의 목록을 Collection 타입으로 리턴
 - `Set<Map.Entry<K,V> entrySet()` : Map안에 Entry라는 타입의 Set을 리턴
 - `boolean containsKey(Object key)` : 매개변수로 넘긴 키가 존재하는지 확인
  - `boolean containsValue(Object value)` : 매개변수로 넘긴 값이 존재하는지 확인
  - `V remove(Object key)` : 매개변수로 넘어온 키에 해당하는 값을 넘겨주며, 해당 키와 값은 Map에서 삭제한다.