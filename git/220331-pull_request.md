# <220331>

### pull request 의미

- 내가 수정한 코드가 있으니 내 branch를 가져가 검토 후 병합해주세요! 코드 충돌을 최소화 할 수 있고 push 권한이 없는 오픈 소스 프로젝트에 기여할 때 많이 사용.

### pull request 사용 순서

1. fork
2. clone, remote 설정
3. branch 생성
4. 수정 작업 후 add → commit → push
5. pull request 생성
6. merge pull request
7. merge 이후 동기화 및 branch 삭제

### branch 종류 5가지

- Master (Main) : 제품으로 출시될 수 있는 브랜치
    - master 였으나 노예제를 연상시킨 다는 이유로 main 으로 변경 되었다.
- Develop : 다음 출시 버전을 개발하는 브랜치
- Feature : 기능을 개발하는 브랜치
- Release : 이번 출시 버전을 준비하는 브랜치
- Hotfix : 출시 버전에서 발생한 버그를 수정하는 브랜치

## Git 명령어

### branch 작업

- git branch : 현재 프로젝트의 브랜치를 확인
- git branch {브랜치명(develop)} : branch 생성
- git checkout {브랜치명} : 원하는 branch 시점으로 변경
- git checkout -b {브랜치명} : branch 를 만드는 동시에 이동
- git branch -d {브랜치명} : branch 삭제

### 변경하기

- git add {file명} : 파일의 변경 사항을 커밋
- git add . : 모든 변경 사항을 다음 커밋에 모두 반영
- git commit -m “commit message” : 메시지와 함께 커밋
- git commit -a : 모든 변경 사항을 반영하면서 커밋

### 동기화하기

- git fetch {remote} : 원격 저장소의 변경사항 가져오기
- git pull {remote} {branch명} : 원격 저장소의 변경사항을 가져오고 병합
- git pull —rebase : 원격 저장소의 변경사항을 가져오고 rebase
- git push : 원격 저장소에 변경사항 발행하기
- git push —tags : 원격 저장소에 태그 발행

### 병합하기와 리베이스 하기

- git merge {branch명} : 병합하기
- git rebase {branch명} : 시작할 곳 rebase로 재지정

### 변경사항 저장하고 복원하기

- git stash : 임시로 변경사항 저장
    - 작업 중에 다른 브랜치로 갔다가 다시 작업하고 싶을 때
- git stash pop : 임시 변경사항 복원
- git stash list : 임시 변경사항 보기

### <팀원으로 진행할 때>

1. 타겟 프로젝트의 저장소에서 자신의 저장소로 fork 를 누르고 자신의 github로 들어간다.
    - fork가 완료 되면 자신의 계정에 새로운 저장소가 생긴다.
2. 내 깃허브로 오면 fork로 생성한 프로젝트가 내 github 레파지토리에 생성
    - 해당 주소 clone 하여 주소 복사
3. Git Bash를 키고, 작업을 하기 위해 fork한 저장소를 로컬에 clone
    - git clone {fork 했던 주소}
    - dev 디렉토리에서 해주는 것이 좋다.
4. cd 해서 해당 레파지토리로 이동
5. banch 생성
    - git branch {브랜치명(develop)}
    - 자신의 로컬 컴퓨터에서 코드를 추가하는 작업은 branch를 만들어서 진행
    - 개발을 하다 보면 코드를 여러 개로 복사해야 하는 일이 자주 생긴다. 코드를 통째로 복사하고 나서 원래 코드와는 상관없이 독립적으로 개발을 진행할 수 있는데, 이렇게 독립적으로 개발하는 것이 branch
6. git  checkout develop 으로 이동
    - git checkout -b {브랜치명} : 브랜치 생성과 동시에 이동
7. git flow feature start (별명) : develop 에 기반한 새기능 브랜치를 생성하고 브랜치로 전환
8. 수정 작업 후 
    - git add {브랜치명}
    - git commit : vim 들어가서 커밋 메시지 작성
        - git commit -m “message” : 메시지 작성과 동시 커밋
    - git push origin {현재브랜치명}
9. git checkout develop
10.  pull request 생성

### <Github 팀원들끼리 충돌난 상황에 대처 방법>

1. 팀장 깃허브 코드와 동기화 git remote add {저장소_별칭} 내git 주소
2. git fetch {별명} 동기화할 브랜치 ex) develop
3. git rebase {별명/동기화할 브랜치}
4. 충돌난 파일 수정
5. add → commit 
6. git rebase —continue
7. git push -f  origin 내 브랜치
