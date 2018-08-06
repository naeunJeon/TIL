# Thread
java 명령어를 사용하여 클래스를 실행시키는 순간 자바프로세스가 시작되고, main()메소드가 수행되면서 하나의 쓰레드가 시작된다. 프로세스가 하나 시작하려면 많은 자원을 필요로 하고 하나의 작업을 동시에 수행하려고 하면 여러 개의 프로세스를 띄워서 실행하면 각각 메모리를 할당해주어야 하지만 쓰레드를 하나 추가하려면 1MB이내의 메모리를 점유할 뿐이다.

## 1. 스레드를 실행하는 방법
### Runnable 인터페이스 사용<br>
**Runnable 인터페이스에 선언되어 있는 메소드**<br>
`void run()` : 스레드가 시작되면 수행되는 메소드
```java
public class RunnableSample implements Runnable{
    public void run(){
        
    }
}
```
### Thread 클래스를 사용<br>
(Runnable 인터페이스를 구현한 클래스이다.)
```java
public class ThreadSample extends Thread{
    public void run(){
        
    }
}
```

```java
public class RunThreads{
    public static void main(String[] args){
        RunThreads threads = new RunThreads();
        thread.runBasic();
    }
    public void runBasic(){
        RunnableSample runnable = new RunnableSample();
        ThreadSample thread = new ThreadSample();
        new Thread(runnable).start();           //Runnable 실행방법
        thread.start();                 //Thread 실행방법
    }
}
```
**start( )** 메소드를 만들지 않아도 알아서 자바에서 **run()** 메소드를 수행하도록 되어 있다.
```java
new Thread(runnable).start();
```
Runnable 인터페이스를 구현한 RunnableSample 클래스를 스레드로 바로 시작할 수 없다. 따라서 Thread 클래스의 생성자에 해당 객체를 추가하여 시작해야한다.

## 2. sleep() 메소드
`static void sleep(long millis)` : 매개변수로 넘어온 시간(1/1,000초) 만큼 대기
`static void sleep(long millis, int nanos)` : 첫번째 매개변수로 넘어온 시간(1/1000) + 두번째 매개변수로 넘어온 시간(1/1000,000,000초) 만큼 대기<br>
**Thread.sleep()** 메소드를 사용할때는 **try-catch**로 묶어주어야한다.(InterruptedException)

## 3. Thread클래스 관련 메소드
`long getId()` : 스레드의 고유 ID를 리턴, JVM에서 자동으로 생성
`String getName()` : 스레드의 이름을 리턴
`void setName(String name)` : 스레드의 이름을 지정
`int getPrioirty()` : 스레드의 우선순위를 확인
`int setPrioirty(int newPriority)` : 스레드의 우선순위를 지정
`boolean isDaemon()` : 스레드가 데몬인지 확인한다.
`Thread.State getState()` : 스레드의 상태를 확인
`ThreadGroup getThreadGroup()` : 스레드의 그룹을 확인