# DataBase란 ?
- 데이터베이스는 컴퓨터 시스템에 전자적으로 저장된 체계적 데이터 모음

### 데이터베이스 관리 시스템 (DBMS) : DataBase Mangement System

- 다수의 사용자들이 데이터베이스 내의 데이터를 접근할 수 있도록 해주는 소프트웨어 도구 집합
- DBMS 는 사용자 또는 다른 프로그램의 요구를 처리하고 적적히 응답하여 데이터를 사용 할 수 있도록 함

> 데이터베이스 특징
> 
- 실시간 접근성
- 계속적인 변화
- 동시 공유
- 내용에 따른 참조

> 데이터베이스 기본 기능
> 
- 가장 중요한 기능 : 삽입, 삭제, 수정, 조회
- `동시성 제어가 보장 되어야 한다`
- 장애 대응 기능
    - 데이터 손실이 발생한 경우 복원이 가능해야 함
    - 보호와 장애에 대한 방안이 있어야 함

> 데이터베이스의 종류
> 
- 계층형 데이터베이스
- `관계형 데이터베이스`
    - Oracle
    - 2차원 표 형식으로 데이터 관리, 가장 널리 사용됨
- 객체 지향형 데이터베이스
- NOSQL 데이터 베이스

# 관계형 데이터베이스

- RDBMS : Realtional DataBase Management System)
    - 관계형 데이터베이스 관리 시스템
    - Oracle, MySQL, H2
- 키와 값 들의 간단한 관계를 테이블화 시킨 매우 간단한 원칙의 전산정보 데이터베이스임 보통 `RDB라고 불림`
- 2차원 표 이용한 데이터 목록화 관리를 하는 것이 주 목적 (Excel)

> 관계형 모델
> 
- 집합론에 기반을 둔 일종의 데이터베이스 모델
- 컬럼(열)과 로우(행) 을 이루는 `하나 이상의 테이블이 존재` 하고 `테이블에 데이터가 저장됨`
- 각각의 테이블은 각각의 로우를 식별하는 기본 키(Primary Key)가 있음
- 컬럼은 필드 or 속성 라고 불림, 로우는 레코드 or 튜플

> SQL 이란?
> 
- 관계형 데이터베이스 관리 시스템의 `데이터를 관리하기 위해 설계된 특수 목적의  프로그래밍 언어`

> SQL 용도
> 
- 사용자
- SQL 작성 및 명령 수행
- DBMS
- 데이터베이스

> SQL 장점
> 
- 코드 간결
- 간단한 기본 조작 명령어 (SELECT, INSERT, UPDATE, DELETE)

> 테이블, 행, 열
> 
- 관계용 데이터베이스와 SQL 의 용어
- TABLE
    - 관계형 데이터베이스의 2차원 표
    - 데이터 관리하는 유일 단위
    - 테이블 설계는 데이터베이스 설계의 중요 부분
- ROW(행)
    - 테이블 가로축
- COLUMN(열)
    - 테이블 세로축

> 관계형 데이터베이스 소프트웨어
> 
- 관계형 데이터베이스를 사용하기 위해 DBMS를 설치해야 한다.
- 대표적인 관계형 데이터베이스 소프트웨어는
    - Oracle
    - MySQL
    - SQL Server

> 데이터베이스와 DBMS 차이
> 
- 데이터베이스 : 추상적 개념
- DBMS : 실체적 개념 (구체적인 방안)
- 데이터베이스를 구체화 시킨게 DBMS 이다.

# 아키텍처 (Architecture)

- 시스템을 만들기 위한 물리 레벨의 조합
- 데이터베이스 설계에서 시스템의 구성
- 아키텍처 통해 시스템의 용도와 목적 추측 가능
- 개발하는 서버 애플리케이션 계층(아키텍쳐)으로 계층별로 나누어 개발한다. 이유는 계층을 분리해야 유지보수가 쉽고 로그파악이 쉽다.

> IT 아키텍처
> 
- 정보시스템을 효율적으로 구성하기 위한 방법

> 가용성
> 
- 서버와 네트워크, 프로그램 등의 정보 시스템이 `정상적으로 사용 가능한 정도`를 말함

> 확장성
> 
- 확장성은 IT 시스템에서 대규모적인 재설계 및 재설치가 필요없이 `확장이 얼마나 쉽고 가능한지에 대한 용이성을` 뜻함
- DBMS 설계자는 DBMS의 확산이나 거대한 성장을 도모해야 됨

> DB 서버의 다중화
> 
- 다른 컴포넌트에 비해 다중화 어려움
- 영속 계층의 특성
    - 데이터 장기간 보존 필요
    - 데이터 다중화 시 갱신 통한 정합성 중요

> DB 서버 다중화 유형
> 
- Active-Active
    - 성능이 가장 유리
    - 두개의 DBMS 엔진 서버가 동시에 가동
    - 저장소는 한곳만 바라봄 (저장소 1개)
- Active-Standby
    - 저장소를 동시에 공유하지 않고 한곳에하 진행 할 때 다른 한 곳은 쉬어야 함
    - 평소에는 Active 만 운영하고 나머지 서버는 Standby 상태
    - 저장소는 한곳만 봄
- 리플리케이션
    - 다중화 : 서버를 여러개 가져간다는 의미
    - DB 서버와 저장소를 하나 세트로 미리 준비
