# → ArrayList 객체 만들기

- ArrayList는 객체를 담기 위한 클래스.
- java.util 패키지에 존재, 사용하기 위해선 import를 통해 가져와야 함
- ArrayList 사용하기 위해서는 객체를 만들어야 한다. 저정할 객체의 타입을 꺽쇠 (<>) 안에 적어 주어야 한다. 이러한 기법을 generic 이라고 한다.

> 저장을 위한 객체 생성
> 

```java
ArrayList<String> names = new ArrayList();

// 객체 추가
names. add("Park");
names. add("Kim");
names. add("Choi");

// 객체 획득
System.out.println(names.get(0));
System.out.println(names.get(1));
System.out.println(names.get(2));
```

> 데이터 담기
> 
- 생성 시 담기 위한 객체의 타입 (클래스 타입) 을 명시 해야 한다.
