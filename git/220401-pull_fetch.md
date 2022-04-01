### 원격저장소와 로컬저장소 충돌 문제

- 다른 팀원이 개발한 내역이 있어 원격 저장소의 작업 내역이 나의 로컬의 작업 내역과 다를 때는 내 변경사항을 원격저장소에 push 하면 충돌 발생
- 원격 저장소의 최신 변경사항으로 맞추어야 내 로컬 변경사항을 업로드 할 수 있다. 이를 위한 명령어가 fetch 와 pull 이다.

### git pull

- git pull
- git pull origin {브랜치 이름}
- 원격 저장소에 있는 프로젝트의 변경사항을 그대로 로컬저장소에 옮겨와 자동으로 병합
- 변경 사항을 가져옴과 동시에 자동으로 병합이 되기 때문에 무엇이 추가되고 병합되었는지 확인이 안됨
- git pull = git fetch + git merge
- pull 과 fetch의 차이점은 병합을 하냐 안 하냐의 차이

### git fetch

- 원격저장소에 있는 프로젝트의 변경사항을 가져오기만 한 후 merge는 따로
- 다른 사람이 수정한 부분을 확인하고 병합할 수 있는 장점이 있음

### reset & revert 차이

- reset : 시간을 아예 과거의 특정 사건 (commit) 으로 되돌린다.
- revert : 현재에 있으면서 과거의 특정 사건 (commit) 들만 없던 일로 만든다.

### unstage

- add 했던걸 내리는 것

git push -f origin {브랜치 명}

### reset 종류

- git reset —soft {commit ID}
    - commit 된 파일들은 staging area로 돌려놓음 (커밋하기 전 상태)
- git reset —mixed {commit ID}
    - 커밋된 파일들을 add 하기 전상태로 돌림
- git reset —hard {commit ID}
    - 커밋 파일 중 파일들은 untracked로 남는다.
- git reset HEAD~{취소할 커밋 수}
    - 원하는 만큼 커밋이 취소
- git reset HEAD^
    - 가장 최근의 커밋이 취소

### git 명령어

- git merge origin/{브랜치명}

  - 변경내역에 출동이 없다면 바로 병합

- git commit —amend : 완료한 커밋을 수정 할 때 재작성 가능

- git mv {원본이름} {변경할 이름} : 파일 이름 변경

- mv {이동시킬 파일} {목적 경로}

- git restore {파일명}: 커밋하기전 최신으로 돌아감

  - 신버전

- git checkout — {파일명} : git restore 랑 기능 동일

  - 구버전
