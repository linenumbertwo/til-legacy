## 발표
> 이번에 서비스 개발 기회를 얻게 돼서 Django를 공부 하는 중

## 1일
- Django 튜토리얼을 진행하고 있음
  > Node.js와 다르게 좀 편리한 것 같다(라이브러리가 되게 다양하고 특히 설치 없이 DB(SQLite)를 사용할 수 있는 점)

## 2일
- 마찬가지로 Django 튜토리얼을 진행 중
  > 진짜 편한건 느껴지는데 빨리 친해져야 할 것 같음
- 현재 진행중인 프로젝트 코드를 보면서 공부를 했음
  > 내가 짜던 코드와 달리 엄청 길고, 파일도 엄청 많아서 뭐가 어떤 역할을 하는지도 파악을 못했음

## 3일
- `virtualenv`툴로 가상환경을 만들었음
  > 인터넷에서 다운로드한 파이썬 라이브러리들이 충돌을 일으키는것을 방지하기 위해서이다. 외부 라이브러리들은 서로 의존성을 가지고 있는 경우가 많아 버전이 맞지 않을 경우 오작동을 일으킬 수 있기 때문임
  ```
  # 가상환경 활성화/비활성화 
  $ source .venv/bin/activate # 활성화
  $ deactivate # 비활성화
  ```
- `!1;`라는 코드가 있길래, 뭔지 찾아봄
  > minify는 코드를 경량화 하는 것이다. 코드로 예시를 들어보자면
  ```
  body {
    margin: 0;
    font-weight: bold;
    }
  ```
  이러한 css 코드에서 minify를 사용하면 불필요한 공백들이 사라짐
  ```
  body{margin:0;font-weight:700}
  ```
  용량이 줄어들면 사용자입장에서는 더 빠르게 로딩할 수 있고 서버측에서는 트래픽이 줄어들기 때문에 많은 이점을 가질 수 있음
  
## 4일
- Django 튜토리얼을 여러번 복습하다 보니 보이지 않던게 보였고 어느정도 익숙해진 것 같음
- 내가 생각하는 Django Web Frame Work의 작업 순서?를 정리해봤음
```
1. 현재 경로에서 프로젝트 시작
$ django-admin startproject my_project .

2. 설정 변경
TIME_ZONE=Asia/Seoul로 변경

3. app 만들고 등록하기
$ python3 manage.py startapp myApp

4. model 생성, 설정, 통합하기
$ python3 manage.py makemigrations
$ python3 manage.py migrate

5. Template 만들고, view, url 설정하기

6. app 폴더에도 url 파일 생성해주고 설정하기
```
- 전에 Node.js로 만들었던 CRUD를 Django를 이용해 똑같이 구현해보는 시간을 가짐
  > 생각보다 설정할 내용이 많아서 어려웠음.. 내일 다시 도전해봐야겠음
  
## 5일
- Django Pattern
  - MVC(Model-View-Controller): 개발 할 때 세 가지 형태로 역할을 나누어 개발하는 방법론입니다.
  ```
  장점: 비지니스 처리 로직과 사용자 인터페이스 요소를 분리시켜 서로 영향없이 개발 하기 수월하다는 장점이 있습니다.
  단점: Controller는 View와 강하게 연결되어 있어서 대규모 프로젝트에서 쉽게 분리할 수도 없고 코드 분석/수정이 힘들다는 단점이 있습니다.
  ```
  - MTV(Model-Template-View): MVC와 같지만 Django는 Template을 사용하기 때문에 MTV Pattern이 맞는 표현입니다.
