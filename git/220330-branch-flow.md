# Day 3

## Commit Convention

1. 커밋 제목은 50자 이내로 요약하여 작성
2. 제목과 내용사이 한칸
3. prefix를 사용하여 한눈에 커밋의 용도를 알기 쉽게 한다.
4. commit은 동작 가능한 최소 단위로 자주 할 것.

* feat: 새로운 기능을 추가할 경우
* fix: 버그를 고친 경우
* test: 테스트 추가, 테스트 리팩토링
* docs: 문서를 수정한 경우
* refactor: 프로덕션 코드 리팩토링
* comment: 필요한 주석 추가 및 변경
* conf: 환경설정 관련
* build: 빌드 관련

#### Commit Convention은 팀마다 다를 수 있으니 관련 문서 참조

## .gitignore

* Git 버전 관리에서 제외할 특정 파일 목록을 지정하는 파일이다.

## Node.js

* node -v : 버전 확인
* npm install : 모듈 설치
* npm init : npm 패키지를 활용하는 파일로 정의
* npm -h : npm에서 사용할 수 있는 명령어 모음
* npm list : 설치한 버전 정보
* npm remove : 설치한 모듈에 대한 삭제
* npm -v : 버전 확인

## HEXO

* hexo init [folder] : 웹 사이트를 초기화 하고 웹 사이트 세팅
* hexo server : 로컬 서버를 구동시킨다. (기본적으로 localhost:4000/)

## Branch

1. 분기점을 생성하여 독립적으로 코드를 변경할 수 있도록 도와주는 명령어

* git branch : 로컬의 branch 정보를 확인
* git branch -v : branch의 정보를 마지막 커밋 내역과 함께 확인
* git branch (이름) : 새로운 branch를 생성

## flow

* git flow init
* git checkout (branch 이름)

### git flow의 5가지 branch
* release : develop에서 개발을 마치고 main에서 출시하기 전에 준비하기 위한 branch
* develop : 다음 출시 버전을 위해 개발하는 branch
* feature : 단위 기능 개발
* master(main) : 실제 배포 될 수 있는 버전의 branch


* git flow init 하고 초기화
* git flow featuer start (이름) : 새 기능을 시작한다.
* git branch : 수시로 확인
* git flow featuer finish (이름) : 기능 개발을 완료.
* git flow featuer publish (이름)

