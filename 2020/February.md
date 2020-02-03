## 02일
- AWS 서버 배포 시도를 하던 중 오류를 겪게 됌
  - ssh: connect to host (public DNS): Operation timed out
  - 문제 해결을 위해 삽질을 하고 있음
  
## 03일
- 전날 발생했던 ssh접속 오류를 인스턴스 재시작을 통해 해결 했습니다. 
- [Diary](https://github.com/indante/secret-Diary)코드를 ssh에 clone을 해왔습니다. 
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
- 보안 그룹에서 인바운드 설정을 하고 [도메인](http://ec2-15-164-222-152.ap-northeast-2.compute.amazonaws.com:3000/)에 접속해보니 배포가 정상적으로 이루어 졌습니다!
