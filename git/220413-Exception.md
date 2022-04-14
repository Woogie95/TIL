## 예외

> 프로그램 오류 종류
> 
- 컴파일 에러 : 컴파일 할 때 발생
- 런타임 에러 : 실행 할 때 발생
- 논리적 에러 : 작성 의도와 다르게 동작

> 자바에서는 런타임 오류를 두 종류로 나눈다.
> 
- 에러 : 수습될 수 없는 심각한 오류
- 예외 : 코드에 의해 수습될 수 있는 다소 미약한 오류

> 예외 종류와 계층 구도
> 
- 자바에서 실행시 발생 할 수 있는 오류는 예외, 에러 클래스로 정의 하였다.
- 모든 예외의 최고 조상은 Exception
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f84910a4-3dae-40f4-9176-94460667a79d/Untitled.png)
    

```
Exception
    |
    |--- IOException
    |--- ClassNotFoundException
    |--- ...
    |--- RuntimeException
            |--- ArithmeticException
            |--- ClassCastException
            |--- NullPointerException
            |--- ...
            |--- IndexOutOfBoundsException
```

- RuntimeException 도 Exception 의 자손이지만 두개로 나누는게 좋다. `RuntimeException 클래스들은 주로 프로그래머의 실수에서 발생 될 수 있는 예외`들이고, 그 외의 `클래스들은 외부의 영향, 프로그램의 사용자에 의해 발생`하기 때문이다.
    - FileNotFoundException : 존재하지 않는 파일의 이름을 입력
    - ClassNotFoundException : 클래스의 이름을 잘못 입력
    - DataFormatException : 데이터 형식이 잘못된 경우 발생

> try - catch 문
> 
- if else와 달리 try-catch는 블럭내에 포함된 문장이 하나여도 {} 를 생략할 수 없다.
- try 블럭 다음에는 여러 종류의 예외를 처리할 수 있도록 여러개의 catch블럭을 사용할 수 있다.
- catch 내에 또 다른 try-catch 블럭을 사용할 수 있는데 이때는 다음과 같이 변수 e를 중복해서 사용할 수 없다.

> try - catch 흐름
> 
- try 블럭 내에서 예외가 발생한 경우
    - 발생한 예외와 일치하는 catch 블락이 있는지 확인한다.
    - 일치하는 catch 블럭을 찾게 되면 그 catch블럭 내의 문장들을 수행하고 전체 try-catch문을 빠져나가고 그 다음 문장을 계속해서 수행한다. 만일 일치하는 catch블럭을 찾지 못하면 예외는 처리되지 못한다.
- try 블럭내에서 예외가 발생하지 않은 경우
    - catch블럭을 거치지 않고 전체 try-catch문을 빠져나가서 수행을 계속한다.

> 예외 메소드
> 
- printStackTrace() : 예외 발생 당시 호출스택에 있던 메소드의 정보와 예외 메시지를 출력
- getMessage() : 발생한 예외클래스의 인스턴스에 저장된 메시지를 얻을 수 있다.

> finally 블록
> 
- try-catch 블록이 끝날 때 항상 수행되는 블록

> throws
> 
- 메소드 오른쪽에 선언
- 호출한 쪽으로 예외를 던져주는 것

> throw
> 
- throw 키워드를 사용해 고의로 예외를 발생 시키는 것
- 먼저 연산자 new를 이용해서 발생시키려는 예외 클래스의 객체를 만들고
- 키워드 throw를 이용해서 예외 발생

```java
class ExceptionEx9 {
  public static void main(String args[]) {
      try {
          Exception e = new Exception("고의로 발생시킴");
          throw e; // 예외를 발생시킴
          // throw new Exception("고의로 발생시킴"); --> 위에 두줄을 한줄로 표현

      }catch (Exception e){
          System.out.println("예외메세지 : " + ae.getMessage());
          e.printStackTrace();
      }
      System.out.println("프로그램이 정상 종료되었음." );
  }
}
```
