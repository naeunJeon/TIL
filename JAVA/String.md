# String 클래스

1. 문자열을 만들때 두가지 방법
- 문자열 리터럴 지정하는 방법
```java
String str1= "test";        //문자열 리터럴 지정
String str2= "test";        //문자열 리터럴 지정

if(str1 == str2){
    System.out.println("str1과 str2은 같음");
} else {
    System.out.println("str1과 str2은 다름");
}
```
- String클래스의 생성자를 이용하는 방법
```java
String str3= new String("test");        //String클래스의 생성자 이용
String str4= new String("test");        //String클래스의 생성자 이용

if(str3 == str4){
    System.out.println("str3과 str4는 같음");
} else {
    System.out.println("str3과 str4는 다름");
}
```
위 두가지 예제 모두 문자열을 생성하는 코드이다. <br>
하지만 **str1과 str2는 같음**을 출력할 것이고 **str3과 str4는 다름**을 출력할 것이다. <br>
리터럴로 문자열을 생성한 경우는 같은 내용의 문자열들을 모두 하나의 String인스턴스를 참조하도록 되어 있지만 String클래스의 생성자를 이용하여 생성한 경우 new연산자에 의해서 메모리할당이 이루어져 새로운 String 인스턴스가 생성되기 때문이다.<br>

후자와 같은 경우 단순히 문자열을 비교하기 위해선 **equals 메소드**를 이용하면된다.
```java
if(str3.equals(str3)){
    System.out.println("str3과 str4는 같음");
} else {
    System.out.println("str3과 str4는 다름");
}
```
결과는 **str1과 str2는 같음**을 출력할 것이다.<br>

2. 빈 문자열(empty string)<br>
일반적으로 변수를 선언할 때, 각 타입의 기본값으로 초기화 하지만 String은 참조형 타입의 값인 null보다는 빈문자열로 초기화 하는것이 보통이다.

```java
String s= "";   //빈 문자열로 초기화
```

3. String관련 메소드<br>
`char charAt(int index)` : 지정한 위치(index)에 있는 문자를 알려줌<br>
`String concat(String str)` : 문자열(str)을 뒤에 덧붙임<br>
`boolean contains(CharSequence s)` : 지정된 문자열(s)이 포함되었는지 검사<br>
`boolean equals(Object obj)` : 매개변수로 받은 문자열(obj)과 String인스턴스의 문자열을 비교하여 같으면 true, 다르면 false를 반환<br>
`boolean equalsIgnoreCase(String str)` :  문자열과 String인스턴스의 문자열을 대소문자 구분없이 비교<br>
`int indexOf(String str)` : 주어진 문자열이 존재하는지 확인하여 그 위치(index)를 반환하고 없으면 -1를 반환<br>
`int length()` : 문자열의 길이를 반환<br>
`String replace(char oldChar, char newChar)` :  문자열 중의  문자열(oldChar)을 새로운 문자열(newChar)로 바꾼 문자열을 반환<br>
`String[] split(String regax)` : 문자열을 지정된 구분자(regax)로 나누어 문자열 배열에 담아 반환<br>
`String substring(int begin, int end) ` : 시작위치(begin)부터 끝위치(end) 범위에 포함된 문자열을 반환(begin<=x<end)<br>
`String toString()` : String인스턴스에 저장되어 있는 문자열을 반환
