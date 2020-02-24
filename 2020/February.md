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

## 05일
- CSS, Bootstrap으로 로그인, 회원가입 페이지를 디자인하고 스타일을 적용했습니다.
  - CSS의 기본적인 속성들을 복습하며 공부했습니다.
    - `!important`: 스타일 적용 우선 순위를 무시하고 `!important`를 선언한 속성에 우선 순위를 부여합니다.
      > `!important`는 세미콜론(;)을 붙여줘야 하며, `!important`는 스타일의 자연스런 흐름을 방해하기에 사용하지 않는게 좋습니다. `!important`를 사용하지 않는다는 것은 css를 제대로 이해하고 있다는 의미라는 걸 배웠습니다.
    - `background: url()`로 배경 이미지를 넣으려 했으나 되지 않아서 많은 삽질을 통해 해결했습니다.
      > express에서 정적 파일을 제공한다는 선언을 해야 했었고, `app.use(express.static(__dirname + '/public'))`를 통해 public 디렉토리 안에 있는 파일들(Image, CSS, JavaScript)을 제공합니다.
    
## 06일
- CSS, Bootstrap으로 CRUD 페이지 일부 디자인 및 스타일을 적용했습니다.
  - `opacity: number`: 0.0부터 1.0까지의 수를 넣어 요소의 투명도를 정할 수 있으며 숫자가 낮을수록 투명해집니다.
    > `opacity`를 사용해서 배경사진과 함께 나타낼 수 있게 스타일을 적용했습니다.
  - `!important`를 쓰지 않고 CSS를 적용하려 했으나 코드의 흐름을 잘 이해하지 못한 탓에 사용하게 되었습니다.
  
## 07일
- 수정, 글 상세보기 페이지는 배경사진을 적용하지 못했습니다.
  - 두 개의 페이지는 id값을 가져와서 화면에 출력하기에 문제가 있었던 것 같습니다.
    > 위의 의견은 개인적인 생각이며, 아직 해결하지 못했습니다 =ㅅ=;
- `!important`를 사용하지 않고 코드를 refactoring 했습니다.
- refactoring이란?
  > 결과의 변경 없이 코드의 구조를 재조정함을 뜻하며 주로 가독성을 높이고 유지보수를 편하게 합니다.
- 아직도 기본적인 CSS 속성을 이해 못한 것 같습니다. 최대한 완성도를 높여서 만들고 회고(반성)를 작성해야겠습니다.

## 09일
- 아직 해결 못한 작업들을 해결하기 위해 구글링 및 시도를 해봤으나 성공하지 못했습니다.
- 지금 공부하는 방법이 시간 투자 대비 효율이 별로인 것 같습니다..

## 10일
- background가 고정되지 않는 현상을 fixed 추가 하여 수정했습니다.
  > `background: url(diary.jpg) no-repeat center center fixed`로 수정
- 일기장 번호를 DB의 id값으로 줘서 번호가 34,35로 나와서 id값을 초기화하는 시도를 해봤습니다.
  ```
  ALTER TABLE [테이블명] AUTO_INCREMENT=[시작 값];
  SET @COUNT = 0;
  UPDATE [테이블명] SET [컬럼명] = @COUNT:=@COUNT+1;
  ```
  > 초기화는 된 것 같지만, 최종 id값이 남아있어서 실패로 끝이 났습니다.
- 구글링을 통해 hbs의 `{{ @index }}`로 해보니 비록 시작 값은 0이지만, 내일 시작 값이 1이 될 수 있게 해보겠습니다.

## 11일
- edit, journals page에 background를 적용했습니다.
  > `app.use(express.static(__dirname + '/public'))` 상대경로로 지정해줬지만 `background: url(OOO.jpg)` 루트를 지정해주지 않아서  `background: url(/OOO.jpg)`로 수정했습니다.
- diaryList page에서 delete기능을 넣으려고 시도 중입니다.

## 12일
- 청년취업지원금 신청 및 교육, 카드 발급을 했습니다.

## 13일
- React 공부를 시작했는데 내용 이해가 잘 가지 않음
- 여러 가지 영어 영상들을 자막없이 보고 모르거나 호기심 갖는 단어들을 찾아보며 영어 공부를 했습니다.

## 14~16일
- [hoseon.me](http://hoseon.me/) 도메인 구매 및 AWS에 연결을 했습니다.
- CSS 코드 분리 및 Write, Edit Page의 위치 수정을 했습니다.
  > px로 위치를 지정했더니 다른 컴퓨터에서 위치가 이상하게 나타나서 코드를 수정했습니다.
  ```
  margin-left: auto;
  margin-right: auto;
  ```
- md5를 이용해 암호화를 시켰습니다.
  > 암호화란? 평문을 암호문으로 변환하는 과정 `Ex) 평문("123456") → 암호화 → 암호문("aBD#fefa$fae!")`<br>
  > 복호화란? 암호문을 평문으로 변환하는 과정 `Ex) 암호문("aBD#fefa$fae!!") → 복호화 → 평문("123456")`
- username이 중복되는 버그가 있어서 Sequel Pro를 이용해 UNIQUE KEY값을 주어서 해결했습니다.

## 19일
- github blog를 만들기 위해 공식문서를 따라했습니다.
  ``` 
  $ gem install bundler
  ERROR:  While executing gem ... (Gem::FilePermissionError)
  You don't have write permissions for the /Library/Ruby/Gems/2.3.0 directory.
  ```
  - 오류에 대해 알아보니 시스템 ruby를 이용하고 있기 때문에 권한이 없어서 gem설치가 안됐습니다.
  sudo 를 통해 root 권한으로 실행하면 설치가 가능하겠지만, 보안상 이유로 권장하지 않는 설치법이기에 rbenv를 통해 에러 해결을 시도해봤습니다.

- 시도 및 에러 
  - `rbenv install -l` 을 통해 최신 버전을 골라서 설치했습니다.
    ```
    $ rbenv install 2.7.0
    ruby-build: using readline from homebrew // 여기서 설치가 멈춤
    ```

- `RUBY_CONFIGURE_OPTS=--with-readline-dir="$(brew --prefix readline)" rbenv install 2.7.0`
	> 구글링을 통해 이러한 방법으로 시도해보니 정상적으로 설치가 이루어짐

- rbenv로 글로벌 버전 2.7.0으로 변경 `rbenv global 2.7.0`
  > `rbenv versions`로 변경 확인

- 쉘 설정 파일에 들어간 후 `vim ~/.zshrc` 코드를 추가했습니다.
  ```
  [[ -d ~/.rbenv  ]] && \
    export PATH=${HOME}/.rbenv/bin:${PATH} && \
    eval "$(rbenv init -)"
  ```
## 21~22일
- 놀았음..

## 23일
- github push를 하던 중, 에러가 발생했습니다.
	```
	ERROR:
	remote: Permission to indante/indante.github.io.git denied to HOSEON-LEE. fatal: unable to access
	'MyUrl': The requested URL returned error: 403
	```
	> Keychain에 들어가 계정 이름과 패스워드를 변경해줘서 해결했음
- 요즘 영어 공부를 많이 하고 있는데 영어 공부 기록장을 만들어야겠다.

## 24일
- 정보처리기능사 기출문제 은행에서 공부를 했음
	> 분명 고등학교 때 논리회로 다 외웠던거 같은데 하나도 기억이 안남..;
- "베껴쓰기로 끝내는 영작문"으로 빡세게 영어 공부를 했음
- 엑셀에 적힌 다수의 url들을 방문하여 해당 html 코드에서 특정 문자열이 포함되어 있는지 확인하는 크롤러를 만들어 볼 예정
	> Fact = 오늘은 검색만 함
