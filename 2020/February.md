## 02일
- AWS 서버 배포 시도를 하던 중 오류를 겪게 됨
  - ssh: connect to host (public DNS): Operation timed out
  - 문제 해결을 위해 삽질을 하고 있음
  
## 03일
- 전날 발생했던 ssh접속 오류를 인스턴스 재시작을 통해 해결 했습니다. 
- [일기장](https://github.com/indante/secret-Diary) 코드를 ssh에 clone을 해왔습니다. 
  - npm install, MySQL설치 및 db, tb 생성 하고 서버 시작을 했지만 오류가 발생했습니다.
  ```
  code: 'ER_ACCESS_DENIED_ERROR',
  errno: 1045,
  sqlMessage: "Access denied for user ''@'localhost' (using password: NO)",
  sqlState: '28000',
  fatal: true
  ```
  - 비밀번호에 문제가 있는 줄 알고 비밀번호 설정, 비밀번호 초기화 등 여러 시도를 해봤지만 다 실패했습니다.
  - 알고보니 .gitignore에 .env가 들어있어서 DB에 필요한 값들이 없어서 발생했던 것..ㅠㅠㅠㅠㅠㅠㅠㅠ
  - `touch .env`로 `.env` 생성 후 `vim .env`로 DB값을 넣어줘서 오류 해결을 했습니다.
- 보안 그룹에서 인바운드 설정을 하고 도메인에 접속해보니 배포가 정상적으로 이루어 졌습니다!

## 04일
- 일기장에서 글 작성이 되지 않는 오류가 발생했습니다.
  - 해결하기 위해 시도했던 방법:
  > `cd /etc/mysql/mysql.conf.d` 경로로 들어가 `sudo vi mysqld.cnf`를 통해 bind-address 값 127.0.0.1을 0.0.0.0으로 수정했습니다.
  >  일시적인 오류였던건지, 시도한 방법을 통해 해결이 됐는지는 모르겠지만 해결 완료!
- 무료 도메인을 받아오려 했지만 실패했습니다.
  - freenom 사이트에서 오랜 시간 삽질을 했으며 로그인 에러가 발생했습니다.
  > Google login error: Your social login could not be determined.<br>
  > 검색해보니 쿠키를 활성화해야 한다길래 [*.]freedom.com을 쿠키 허용 값에 넣어주고 다시 시도해봤으나 실패했습니다.
- 오늘의 깨달음: 공짜는 어렵다
