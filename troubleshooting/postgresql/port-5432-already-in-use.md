### Port 5432 is already in use
Postgres.app 에서 5432 Port 가 Not running 상태여서, Start를 눌렀으나
`Port 5432 is already in use` Error를 마주하였다.

### Solution
- `brew services stop postgresql` 실행

아마 데이터베이스 서버의 5432 포트가 이미 실행 중인 상태여서, Postgres.app이 접근할 수 없어서 발생한 오류 같다.
