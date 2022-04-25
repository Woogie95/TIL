## java.io 패키지

- 입출력 Input / Output
- java.io 패키지에서 제공하는 클래스들을 사용하려면 스트림(Stream)이라는 개념을 이해 해야함.
- HashSet 에 데이터를 저장할 때, `중복 되는 데이터를 허용하지 않게끔 하려면, 항상 hashCode 메소드, equals 메소드를 오버라이딩 해주어야 한다.`

> 입출력 클래스의 분류
> 
1. Object
    1. file
    2. Input Stream
        1. File Input Stream
        2. Filter Input Stream
            1. Buffered Input Stream
    3. Output Stream
        1. File Output Stream
        2. Filter Output Stream
            1. Buffered Output Stream
            2. Print Stream
    4. Reader
        1. Buffered Reader
        2. Input Stream Reader
            1. File Reader
    5. Writer
        1. Buffered Writer
        2. Output Stream Writer
            1. File Writer
        3. Print Writer

### 스트림

- 스트림은 단방향 이고, 입력 스트림으로 연결 되어 있어야 한다.
- 입력 스트림은 Input Stream && `Reader`
- 출력 스트림은 Output Stream && `Writer`

## SQL

1**) DDL(Data Definition Language)**

- DDL은 사전적 의미 그대로 데이터가 저장되는 공간을 정의

```sql
CREATE TABLE STUDENT1(
	No VARCHAR(100) PRIMARY KEY,
	NAME VARCHAR(100) NOT NULL,
	SCORE NUMBER(10)
	MAJOR VARCHAR(100) NOT NULL
);
```

2**) DML(Data Manipulation Language)**

- **데이터 등록**

```sql
// ex)
INSERT INTO 테이블이름(컬럼목록) VALUES(값목록);

// ex)
INSERT INTO STUDENT1(No, NAME, SCORE, MAJOR) 
VALUES('22-000001', '할아버지', 100, '전자 공학');
```

- 현재 상태에서 학생정보가 잘 등록되어 있는지 확인하기 위해서 SELECT를 실행한다.

```sql
SELECT * FROM STUDENT1;
```

- 데이터 수정

```sql
UPDATE 테이블이름 SET 컬럼이름 = 수정값, 컬럼이름 = 수정값;

//ex 전부다 바뀜
UPDATE STUDENT SET SCORE = 100, MAJOR = '산업 공학';

// ex  WHERE 구절 추가 해서 지정해 줌
UPDATE STRDENT1 SET MAJOR = '컴퓨터 공학', WHERE NO='22-000006;'
```

- 데이터 삭제

```sql
// 이렇게 하면 모든 테이블에 있는 값 삭제
DELETE 테이블이름;

// ex
DELETE STUDENT1 WHERE NO = '22-000002';
```

3) **DQL(Data Query Language)**

- 테이블에 저장된 데이터를 검색하기 위해서는 SELECT문을 사용하며 쿼리(Query)라고 한다.
- 데이터 조회

```sql
SELECT 컬럼이름, 컬럼이름, …

FROM 테이블이름

WHERE 제약조건;

// ex 보고싶은 컬럼
SELECT NO, NAME, MAJOR FROM STUDENT1

// ex 저징된 사람 컬럼 다 보기
SELECT * FROM STUDENT1

WHERE NO='22-000005'
```

- 정렬

```sql
ORDER BY SCORE DESC
```
