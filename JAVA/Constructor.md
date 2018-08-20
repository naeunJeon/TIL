# 생성자(Constructor)
 생성자는 인스턴스가 생성될 때 호출되는 '인스턴스 초기화 메서드'이다. 따라서 인스턴스 변수의 초기화 작업에 주로 사용하며, 인스턴스 생성 시에 실행되어야 할 작업을 위해서도 사용된다.

 생성자는 메서드처럼 클래스 내에 선언되며, 구조도 메서드와 유사하지만 리턴값이 없다.(하지만 **void**를 사용하지 않는다.) 또한 생성자도 오버로딩이 가능하므로 하나의 클래스에 여러 개의 생성자가 있을 수 있다.

 #### 생성자의 조건
 1. 생성자의 이름은 클래스의 이름과 같아야한다.
 2.  생성자는 리턴 값이 없다.


### 기본생성자
모든 클래스에는 반드시 하나 이상의 생성자가 정의되어 있어야한다. 그러나 생성자를 정의하지 않고도 컴파일러가 자동적으로 **기본생성자**를 추가하여 컴파일 한다.<br>
`클래스 이름 () {   }`<br>
특별히 인스턴스 초기화 작업이 요구되어 지지않는다면 생성자를 정의하지 않고 컴파일러가 제공하는 기본 생성자를 사용해도 좋다.<br>
* 컴파일러가 자동적으로 기본 생성자를 추가해주는 경우는 '클래스 내에 생성자가 하나도 없을때' 뿐!!

### 매개변수가 있는 생성자
```java
class Car{
    String color;
    String gearType;
    int door;

    Car(){}                     //생성자
    Car(String c, String g, int d){      // 생성자
        color = c;
        gearType = g;
        door = d;
    }
}

class CarTest{
    public static void main(String[] args){
        Car c1 = new Car();
        c1.color = "white";
        c1.gearType = "auto";
        c1.door = 4;

        Car c2 = new Car("white", "auto", 4);
    }
}
```
Car 인스턴스를 생성할 때, 생성자 Car()를 사용한다면, 인스턴스를 생성한 다음에 인스턴스변수들을 따로 초기화해주어야 하지만, 매개변수가 있는 Car(String c, String g, int d)를 사용한다면 인스턴스를 생성하는 동시에 원하는 값으로 초기화 할 수 있게 된다.<br>
-> 후자의 경우가 코드를 보다 간결하고 직관적으로 만든다.

### 생성자에서 다른 생성자 호출하기 - this(), this
같은 클래스의 멤버들 간에 서로 호출할 수 있는 것처럼 생성자 간에도 서로 호출이 가능한다. 단, 두조건을 만족시켜야한다.
1. 생성자의 이름으로 클래스이름 대신 **this**를 사용한다.
2. 한 생성자에서 다른 생성자를 호출할 때는 반드시 첫 줄에서만 호출이 가능하다.
```java
class Car{
    String color;
    String gearType;
    int door;

    Car(){}                             this("white" "auto", 4);        //Car(String c, String g, int d)를 호출

    Car(String color){
        this(color, "auto", 4);
    }

    Car(String color, String gearType, int door){      // 생성자
        this.color = color;
        this.gearType = gearType;
        this.door = door;
    }
}

class CarTest2{
    public static void main(String[] args){
        Car c1 = new Car();
        Car c2 = new Car("blue");
    }
}
```
생성자 Car()에서 또 다른 생성자 Car(String color, String gearType, int door)를 호출하였다. 이처럼 생성자간의 호출에는 생성자 이름 대신 **this**를 사용했다(사용해야만한다!!)
<br>
`this` : 인스턴스 자신을 가리키는 참조변수, 인스턴스의 주소가 저장되어 있음, 모든 인스턴스메서드에 지역변수로 숨겨진 채로 존재한다.<br>
`this(), this(매개변수)` : 생성자, 같은 클래스의 다른 생성자를 호출할때 사용한다. 