# StringBuffer와 StringBuilder

String은 한번 만들어지면 더 이상 그 값을 바꿀수 없다. 더하기를 이용하여 값을 바꾸는 것은 기존 객체를 버리고 새로운 String 객체를 생성된 것이다. 따라서 더하는 작업을 반복한다면 버려진 객체들은 계속해서 만들어지고 GC(가비지 컬랙션)이 대상이 될 것이다. **StringBuffer와 StringBuilder**는 이러한 String 클래스의 단점을 보완하기 위해서 나온 클래스이다.
*  StringBuffer와 StringBuilder에서 제공하는 메소드는 동일하다
* StringBuffer가 StringBuilder보다 안전하다
* StringBuilder가 StringBuffer보다 빠르다

```java
StringBuilder sb = new StringBuilder();
sb.append("hello");
sb.append(" world");
```
문자열을 더할때 더하기(+) 기호 대신 append() 메소드를 이용하면된다.(hell world가 출력될 것이다.)

```java
StringBuilder sb = new StringBuilder();
sb.append("hello").append(" world");
```
append() 메소드를 연속으로 붙여서 써도 같은 결과가 출력된다.



