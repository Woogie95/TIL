## 클래스와 객체

### 클래스와 객체의 정의와 용도

> 클래스 (설계도)
> 
- 정의 : 객체를 정의해 놓은 것
- 용도 : 객체를 생성하는데 사용

> 객체
> 
- 정의 : 실제로 존재하는 것, 사물 or 개념
- 용도 : 객체가 가지고 있는 기능과 속성에 따라 다름

### 객체와 인스턴스

- 어떤 클래스로부터 만들어진 객체를 그 클래스의 `인스턴스` 라고 한다.
- 클래스 → 인스턴스화 → 인스턴스 (객체)

### 객체의 구성요소 - 속성과 기능

- 객체는 `속성과 기능`을 가지고 있으며 이를 그 객체의 멤버라고 한다.
- `변수와 메소드`로 표현한다.

### 인스턴스의 생성과 사용

```java
클래스명 변수명;          // 클래스의 객체를 참조하기 위한 참조변수를 선언 
변수명 = new 클래스명();  // 클래스의 객체를 생성 후, 객체의 주소를 참조 변수에 저장

Tv t = new Tv();
```

```java
class Tv {
    // Tv의 속성(멤버변수)
    String color;         // 색상
    boolean power;        // 전원상태(on/off)
    int channel;          // 채널

    // Tv의 기능(매소드)
    void power() {         // TV를 켜거나 끄는 기능을 하는 메소드 
        power = !power; 
    }   

    void channelUp() {     // TV의 채널을 높이는 기능을 하는 메소드
        ++channel; 
    }
        
    void channelDown() {   // TV의 채널을 낮추는 기능을 하는 매소드
        --channel; 
    }
}

class TvTest{
    public static void main(String[] args) {
        Tv t = new Tv();
        t.channel = 7;
        t.channelDown();
        System.out.println("현재 채널은 " + t.channel + "입니다.");
    }
}
```

### 객체 배열

- 많은 수의 객체를 다뤄야 할때 배열로 다루는데 이를 ‘`객체 배열`' 이라고 한다.
- 객체 배열 안에 객체가 저장 되는 것은 아니고, `객체의 주소가 저장`된다.

```java
// 방법 1
Tv[] tvArr = new Tv[3];    // 객체 배열 생성

tvArr[0] = new Tv();
tvArr[1] = new Tv();
tvArr[2] = new Tv();

// 방법 2
Tv[] tvArr = {new Tv(), new Tv(), new Tv()} 

// 방법 3
Tv[] tvArr = new Tv[10];

for(int i = 0; i < tvArr.length; i++){
    tvArr[i] = new Tv();
    }
}
```

### 클래스의 또 다른 정의

> 클래스
> 
- 변수 : 하나의 데이터를 저장할 수 있는 공간
- 배열 : 같은 종류의 데이터를 하나의 집합으로 저장할 수 있는 공간
- 구조체 : 서로 관련된 여러 데이터를  종류에 관계없이 하나의 집합으로 저장할 수 있는 공간
- 클래스 : 데이터와 함수의 결합 (객체 + 메소드)

## 변수와 메소드

### 선언위치에 따른 변수의 종류

- 변수는 `클래스변수, 인스턴스변수, 지역변수` 모두 세 종류가 있다. 멤버변수를 제외한 나머지 변수들은 `모두 지역변수`이며, 멤버변수 중 `static이 붙은 것은 클래스 변수`, `붙지 않은 것은 인스턴스 변수`이다.

> 인스턴스변수(instance variable)
> 
- `클래스 영역에 선언`되며, 클래스의 `인스턴스를 생성할 때 만들어진다`. 또한 `독립적인 저장공간을 가지므로 서로 다른 값을 가질 수 있다`.

> 클래스변수(class variable) , static 변수
> 
- 클래스 변수를 선언하는 방법은 인스턴스변수 앞에 `static을 붙이기만 하면 된다`. 인스턴스변수와 달리 `모든 인스턴스가 공통된 저장공간을 공유`하게 된다. 클래스 변수는 `인스턴스를 생성하지 않고도 사용가능` 하며 클래스가 메모리에 `'로딩(loading)'될 때 생성되며 프로그램이 종료될 때 까지 유지` 된다.

> 지역변수(local variable)
> 
- `메서드 내에 선언`되어 메서드 내에서만 사용 가능하며, `메서드가 종료되면 소멸`된다.

### 클래스 변수와 인스턴스 변수

- 인스턴스변수는 `인스턴스가 생성될 때 마다 생성되므로 인스턴스마다 각기 다른 값을 유지`할 수 있지만,
`클래스 변수는 모든 인스턴스가 하나로 저장공간을 공유`하므로, `항상 공통된 값`을 갖는다.

### 메소드 사용 이유

1. 코드 재사용성 2. 중복 코드 제거 3. 프로그램의 구조화

### 메소드 선언과 구현

> **메소드 선언부(method delaration, method header)**
> 
- 메소드 선언부는 '메소드 이름'과 '매개변수 선언', 그리고 '반환타입'으로 구성되어 있다.

> **매개변수 선언(parameter declaration)**
> 
- `작업을 수행하는데 필요한 값을 제공받기 위한 것`, 필요한 개수만큼 변수를 선언하며 각 변수 간의 구분은 쉼표','를 사용한다.

> **메소드의 이름(method name)**
> 
- 메소드의 이름도 변수의 명명규칙대로 작성하면 되며 일반적으로 `동사` 작성하는 경우가 많다.

> **반환타입(return type)**
> 
- 메소드의 작업수행 결과인 '반환값(return value)'의 타입을 적으며 `반환값이 없는 경우 'void'`를 적어야 한다.

> **메소드의 구현부**
> 
- 메소드의 선언부 다음에 오는 괄호{}를 '메소드의 구현부'라고 하는데. 여기에 메소드를 호출했을 때 수행될 문장들을 넣는다.

> **return문**
> 
- 메소드의 반환타입이 'void'라 아닌 경우 구현부 안에 반드시 포함되어 있어야 하며 `반환값은 최대 하나만 허용`한다.

> **지역변수**
> 
- 메소드 내에 선언된 변수를 말한다.

### 메소드의 호출

- ****인자(argument)와 매개변수(parameter)****
- 호출 할때 보내주는 값을 ****`인자(argument)`**** 라고 하고, 메소드에서 받는 값을 ****`매개변수(parameter)` 라고 한다.**

### JVM의 메모리 구조

> 메소드 영역
> 
- 프로그램 실행 중 어떤 클래스가 사용되면, `JVM은 해당 클래스의 클래스파일(*.class)을 읽어서 분석하여 클래스에 대한정보를 이곳에 저장한다`. 이 때, 그 클래스의 `클래스변수도 이영역에 함께 저장`된다.

> 힙 영역 (heep)
> 
- 프로그램 실행 중 생성되는 인스턴스는 모두 이곳에 생성.

> 호출스택
> 
- `호출스택은 메소드의 작업에 필요한 메모리 공간을 제공`, 메소드가 호출되면, `호출스택에 메서드를 위한 메모리가 할당`되며, `작업을 마치면 할당되었던 메모리 공간은 반환`된다.

```
호출스택의 특징
1 메소드가 호출되면 수행에 필요한 만큼의 메모리를 스택에 할당받는다.
2 메소드가 수행을 마치고나면 사용했던 메모리를 반환하고 스택에서 제거된다.
3 호출스택의 제일 위에 있는 메소드가 현재 실행 중인 메소드이다
4 아래에 있는 메소드가 바로 위의 메소드를 호출한 메소드이다.
```

### 기본형 매개변수와 참조형 매개변수

- 메소드를 호출할 때 매개변수로 지정한 값을 메소드의 매개변수에 복사해서 넘겨준다. `매개변수의 타입이 기본형일 때는 기본형 값이 복사` 되겠지만, `참조형 이면 인스턴스 주소`가 복사된다. (`배열도 참조변수`)

```
기본형 매개변수 - 변수의 값을 읽기만 할 수 있다.(read only)
참조형 매개변수 - 변수의 값을 읽고 변경할 수 있다.(read & write)
```

### 참조형 반환타입

- 반환타입이 참조형이라는 것은 반환하는 값의 타입이 참조형이라는 얘긴데. 모든 참조형 타입의 값은 '객체의 주소'이므로 그저 `정수값이 반환되는 것`일 뿐 특별한 것이 없다.

```java
class ReferenceReturnEx {
    public static void main(String[] args) {
        Data d = new Data();
        d.x = 20;

        Data d2 = copy(d);
        System.out.println("d.x =" + d.x);
        System.out.println("d2.x =" + d2.x);
        }

    static Data copy(Data d){
        Data tmp = new Data();
        tmp.x = d.x;

        return tmp;
        }
    }

class Data{
    int x;
}

[실행결과]
d.x =20
d2.x =20
```

### 재귀호출

- `메소드 내부에서 자기 자신을 호출하는 것`. 재귀호출하는 것을 재귀 메소드라고 한다.
- 재귀호출을 사용하기 위해서는 `입력에 따라 종료 조건이 필요`하다.
    - `종료 조건이 없거나 성립하지 않는 입력이 있다면` 무한히 자기 자신을 호출해서 `StackOverflowError`가 발생한다.
    - 종료 조건이 성립하지 않는 경우가 있는지 매개변수를 잘 검사해야한다.
- 재귀호출은 계산 이외에 메서드를 `호출/반환하는 과정을 필요로 하기 때문에 일반적으로 반복문보다 느리다.`
- 그러나 특정 상황에서 재귀호출은 반복문보다 훨씬 단순한 구조로 문제를 풀 수 있다.
    - 재귀호출의 간결함이 주는 이득이 충분히 큰 경우에만 사용해야한다.

```java
int factorial(int n) {
    if (n==1) return 1;

    return n * factorial(n-1);
}
```

### 클래스 메소드 (static 메소드) 와 인스턴스 메소드

- static이 붙어있으면 클래스 메소드, 아니면 인스턴스 메소드이다.

> 클래스 메소드
> 
- [클래스 이름].[메소드 이름]으로 호출할 수 있다.
- 모든 인스턴스에 `공통적으로 사용해야하는 메서드를 클래스 메서드`로 정의
- 클래스 메소드는 `인스턴스 변수를 사용할 수 없다`.
- 클래스 메소드는 `클래스가 메모리에 올라갈 때 자동으로 생성된다.`
- 인스턴스 변수를 사용하지 않는다면 인스턴스 메서드를 클래스 메서드로 바꿀 것을 고려한다.
    - 클래스 메서드 호출 시 인스턴스 메서드와는 다르게 찾는 과정 없이 바로 호출 가능하므로 더 좋은 성능을 보여준다.

```java
  class NewMath {
      static int add(int a, int b) {
          return a + b;
      }
  }

  class NewMathTest {
      public static void main(String args[]) {
          System.out.println(NewMath.add(3, 4)); // 7
      }
  }
```

### 클래스 멤버와 인스턴스 멤버간의 참조와 호출

- 클래스 메소드에선 `인스턴스 변수와 인스턴스 메소드를 사용 불가`!!!

## 오버로딩 (****overloading****)

- 한 클래스 내에 같은 `이름의 메소드를 여러개 선언하는 것`

> 오버로딩의 조건
> 
- 메소드 이름 동일 해야 함
- 매개변수 개수 또는 타입이 달라야 함
- 매개변수 순서가 달라도 되지만 애매한 경우가 생길 수 있으므로 주의해야 한다.

```java
void println()
void println(boolean x)
void println(char x)
void println(char[] x)
void println(double x)
void println(float x)
void println(int x)
void println(long x)
void println(Object x)
void println(String x)
```

```java
// 매개변수의 타입이 같고 이름만 다른 경우 (X)
int add(int a, int b) { return a+b; }
int add(int x, int y) { return x+y; }

// 반환 타입만 다른 경우 (X)
int add(int a, int b) { return a+b; }
long add(int a, int b) { return (long)(a + b); }

// 매개변수의 순서가 다른 경우 (O)
long add(int a, long b) { return a+b; }
long add(long a, int b) { return a+b; }
```

```java
class Adder {
  long add(int a, long b) { System.out.println("add(int, long)"); return a+b; }
  long add(long a, int b) { System.out.println("add(long, int)"); return a+b; }
}

class OverloadingTest {
  public static void main(String[] args) {
      Adder adder = new Adder();

      adder.add(3, 3);
  }
}

// [출력 결과]
~ $ javac OverloadingTest.java
OverloadingTest.java:10: error: reference to add is ambiguous
  adder.add(3, 3);
       ^
  both method add(int,long) in Adder and method add(long,int) in Adder match
1 error
```

### 오버로딩의 장점

- 다른 매개변수에 대해 같은 기능을 하는 메서드를 같은 이름으로 나타낼 수 있다.
    - 다 다른 이름을 가져야 한다면 만들기도 어렵고 기억하기도 어렵다.
- 메서드의 이름을 절약할 수 있다.
- 코드 재사용성

## 생성자 (Constructor)

- 클래스 인스턴스가 생성될 때 사용
- 반환 타입이 없고 이름이 클래스 이름과 동일해야 한다.
- 생성자도 오버로딩이 가능하다.
- 인스턴스 변수 초기화 할 때 사용

### 기본 생성자

- 하나의 클래스는 반드시 하나 이상의 생성자를 가진다.
- 클래스에 따로 생성자를 정의하지 않았다면, 컴파일러가 기본 생성자를 정의한다.

### 매개변수가 있는 생성자

- 초기값을 받아서 클래스 멤버를 초기화할 때 사용할 수 있다.

```java
class Car  {
      String color; 
      String gearType;
      int door;
    }
      Car() { 
          color = "white"; 
          gearType = "auto"; 
          door = 4; 
    }
      Car(String c) { 
          color = c; 
          gearTyep = "auto";
          door = 4; 
    }
      Car(String c, String g, int d) { 
					color = c; 
					gearType = g; 
					door = d; 
    }
}
```

### 생성자에서 다른 생성자 호출하기 this(), this

> this()
> 
- 생성자에서 다른(부모) 생성자를 호출
    - 항상 첫 줄에서만 호출 가능

> this
> 
- 인스턴스 자신을 가리키는 참조변수
    - this를 사용하면 매개변수와 인스턴스 변수 이름을 같은 이름으로 사용 가능 (매개변수 이름과 구별하기 위해 사용)
