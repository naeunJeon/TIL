# java.util 패키지

## 날짜를 처리하기 위한 Date와 Calendar
1. Date 생성자
`Date()` : 객체가 생성된 시간을 갖는 Date객체 생성
`Date(long date)` : 매개 변수로 넘어온 long 타입 시간을 갖는 Date객체 생성

2. Date 관련 메소드
`long getTime()` : Date 객체의 시간을 long타입으로 리턴
`void setTime(long time)` : Date 객체의 시간을 매개 변수로 받은 시간으로 변경

3. Calendar 객체 생성 메소드<br>
Calendar 클래스는 생성자들이 protected로 선언되어 있어 클래스를 확장하여 구현하지 않으면 생성자로 객체를 만들어 낼 수 없다. 그렇지만 Calendar 객체를 생성해주는 getInstance() 메소드가 있다.<br>
`getInstance()` : 기본 객체 생성 메소드, 모든 값은 기본 값이며, 현재 시간으로 지정된 Calendar 객체를 생성<br>
`getInstance(Locale aLocale)` : 지정된 지역의 Calendar 객체를 생성<br>
`getInstance(TimeZone zone)` : 지정된 타임존의 Calendar 객체를 생성<br>
`getInstance(TimeZone zone, Locale aLocale)` : 지정된 타임존과 지역의 Calendar 객체를 생성<br>

## 임의의 값을 생성하기 위한 Random
임의의 난수를 만들때 사용한다. Random 객체를 만들고 Random 클래스의 메소드를 사용하여 임의의 수를 구할 수 있다.<br>
1. Random 클래스의 메소드<br>
`nextBytes(byte[])`<br>
`nextInt()`<br>
`nextLong()`<br>
`nextBoolean()`<br>
....<br>
nextInt(100)의 의미는 0부터 100사이의 난수를 하나 리턴한다는 의미이다.

## 문자열을 자르기 위한 StringTokenizer
(String 클래스의 split()메소드 사용을 권장)
```java
pakage d.util;

import java.util.StringTokenizer;

public class StringTokenizerSample{
    public static void main(String[] args){
        StringTokenizerSample sample = new StringTokenizerSample();
        String data = "This is a basic java book";
        sample.parseString(data);
    }
    public void parseString(String data){
        StringTokenizer st1 = new StringTokenizer(data);         //StringTokenizer 객체 생성
        StringTokenizer st2 = new StringTokenizer(data, "a");         //StringTokenizer 객체 생성
        while(st1.hasMoreElements){
            String tempData = st1.nextToken();
            System.out.println("["+tempData+"]");
        }
        while(st2.hasMoreElements){
            String tempData = st2.nextToken();
            System.out.println("["+tempData+"]");
        }
    }
}
```
