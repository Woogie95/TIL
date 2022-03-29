#### Git Bash Commands

- ls : 현 디렉토리 내 파일과 디렉토리들을 표시한다.
- ls -a : 디렉토리의 숨긴 파일과 디렉토리까지 출력한다.
- pwd : 현재 작업 중인 디렉토리를 표시한다.
- cd : 경로 이동
- cd .. : 부모 디렉토리 이동
- cd . : 상위 디렉토리 이동
- mkdir : 새로운 디렉토리(폴더) 생성 ex) mkdir README.txt
- touch : 새로운 파일 생성 ex) touch keyboard.txt
- cat : 파일 내용 표시
- clear : 앞 서 입력한 내용 지우기
- cp : 파일 복사
- vi : 편집기로 파일을 작성 ex) vi README.txt
- rm : 파일 삭제
- rm -d : 디렉토리 삭제 (서브 파일 있으면 삭제 불가)
- rm -r : 디렉토리 삭제 (서브 파일까지 무사히고 삭제)
- * : 에터리스트
- vim (vi) : 파일 수정

#### Git User interlock

- git config --list 설정 상태 확인
- git config --global user.name "사용자명"
- git config --global user.email "사용자 이메일"

#### clone git interlock

- Github 사이트에서 Repository 생성하고 README 체크
- GitBash 창에서 git clone 깃허브 주소 입력
- git status로 상태 확인
- git add {fileName}
- git commit {fileName}
- git push origin master or main

