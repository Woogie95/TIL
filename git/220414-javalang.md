## java.lang 패키지

- 자바 프로그래밍에 가장 기본이 되는 클래스들 포함
- import 문 없이 사용 가능

> Object 클래스
> 
- 모든 클래스의 최고 조상
- Object클래스의 멤버들은 모든 클래스에서 사용 가능
- 멤버변수는 없고 11개의 메서드만 가짐 (인스턴스가 가져야 할 기본적인 것들)

> Object 클래스 메소드
> 
- equals : 매개변수로 객체의 참조변수를 받아서 비교하여 그 결과를 boolean으로 알려준다.
- hashCode : 객체의 주소값을 변환하여 생성한 객체의 고유한 정수값
- toString : 객체 자신의 정보를 문자열로 반환

> String 클래스
> 
- 문자열을 저장하고 이를 다루는데 필요한 메소드 제공
- 변경 불가능한 immutable 클래스
- 문자열간의 결합이나 추출 등의 작업은 `StringBuffer`클래스를 사용하는 것이 좋다.

### 래퍼 클래스 (wrapper)

- 기본형을 클래스로 다루어야 할 경우를 위한 클래스
- 래퍼 클래스들은 equals, toString이 오버라이딩 되어있다.
- 비교 연산자를 사용할 수 없는 대신 compareTo 를 제공

### 오토박싱 & 언박싱

- 오토박싱 : 기본형 값을 래퍼클래스의 객체로 자동 변환
- 언박싱 : 래퍼 클래스를 기본형 값으로 자동 변환