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
  
## 6일
Today is my birthday, so I played Maple Story and League of Legends :)

## 7~8일
> showmethatcode는 함께 개발 공부를 하는 팀 이름이고 네 명으로 구성되어 있습니다.
```
저희는 매일 공부한 내용을 데일리 미팅에서 공유하고 Notion에 TIL, Action Plan을 적는 문서를 작성합니다.
이렇게 하다가 Notion처럼 내용을 기록할 수 있는 웹을 만들어 보자 해서 해커톤(?)을 진행했습니다.
디자이너, 프론트엔드, 백엔드 두 명으로 진행했으며 저는 백엔드를 담당했습니다.
브랜치를 백엔드, 프론트엔드로 나눠서 작업했고 아무래도 이렇게 프로젝트를 처음부터 끝까지 진행하는게 처음이다보니 의미있고 재미있었습니다.
```
```
Django로 작업을 했고 MySQL로 하기로 해서 기본 세팅을 하던 중 MySQL password 관련 오류가 발생해서 몇 시간동안 해결을 못해 SQLite로 넘어갔습니다.
우선 제가 맡은 sharing, sharing_detail page에 필요한 모델 및 앱 생성을 했습니다.
구글 로그인 환경변수 값 ~/.zshrc에 넣어주고 로그인 후 root page로 redirect 시켜주는 기능 구현을 했습니다.
임의로 html 파일 만들어서 프론트 개발자님한테 파일 받으면 템플릿 적용 바로 할 수 있게 작업해 놨습니다.
파일 받고 난 후, 코드만 넣으면 바로 될 줄 알았는데 HTML 파일에서 정적인 파일을 불러와야 할 수 있다는걸 알게 됐습니다.

아직 기능 구현까지는 완성시키지 못했지만 차차 완성시켜 나갈 것이고 기능도 더 추가할 것입니다.
```

## 9일
- 생애 처음으로 requirements.txt를 생성해 봄
```
# requirements 생성
pip freeze > requirements.txt
# 패키지 설치
pip install -r requirements.txt
```
- HTML/CSS 코드 수정하신거 Template에 적용 및 업데이트
- 이실직고하자면 거의 놀았음

## 10일
- 정보처리기능사 필기 시험이 얼마 남지 않아서 각 진수별 변환법, 논리 회로, 논리식을 공부했음
  > 인터넷에 정리된 글로는 완전히 이해하지 못해서 책을 주문함
- 전에 공부하던 영어책 복습 및 진도를 조금 나갔음
```
a different story: 다른 상황/이야기
in a twinkling: 순식간에
be starved to death: 굶어죽다

책에 나와있는 소설, 동화 일부 내용을 베껴쓰며 단어 뜻을 찾아보며 공부를 했음
```

## 11일
- Django 예제를 찾아서 여러가지 따라하고 내용을 이해하려고 공부 함

## 12~13일
- 여기에 정리할 만한 좋은 공부를 하진 못했고, 친구들과 만나서 많이 놀았다..

## 14일
- `on_delete=models.CASADE`란 모델 A 와 모델 B가 N:1 관계일 때, 모델A에 on_delete=models.CASADE 구문이 설정되어있으면, 모델 B의 어떤 레코드가 삭제되면 삭제될 모델 B의 레코드와 관련있는 모델 A의 레코드들도 연차적으로 삭제됩니다. 
- 추상 모델(Abstract Model): Django model을 작성할 때 여러 테이블에 같은 형식의 필드(컬럼)이 있는 경우가 있다. 이럴 때, Abstract Model을 만들어 상속받으면 된다. 내가 생성한 추상 모델의 코드를 적어보겠다!!!
```
from django.db import models


class BaseModel(models.Model):
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    class Meta:
        abstract = True
```

## 15일
- Django를 이용해 데일리 미팅 글 작성 기능을 구현해냈다. 코드를 자랑해보겠다!
```
# views.py
from django.shortcuts import render
from django.http import JsonResponse
from .models import Meeting, MeetingType
from django.contrib.auth import get_user_model, get_user


# /meetings/please/
def please(request):
    if request.method == 'POST':
        done = request.POST.get('done', '')
        in_progress = request.POST.get('in_progress', '')
        obstacle = request.POST.get('obstacle', '')

        error_message = ''

        if done == '':
            error_message = '지금까지 무엇을 하셨는지 입력해주세요!'
        if in_progress == '':
            error_message = '무엇을 하실건지 입력해주세요!'
        if obstacle == '':
            error_message = '예상되는 어려움을 적어주세요!'
        
        user = get_user(request)

        if not error_message and user:
            meeting = Meeting.objects.create(meeting_type=MeetingType.DAILY, done=done, in_progress=in_progress, obstacle=obstacle, user=user, team=user.team)
            meeting.save()
    
        return JsonResponse({
            'success': error_message == '',
            'error_message': error_message,
        }, json_dumps_params = {'ensure_ascii': True})
```
- view를 어떻게 작성해야 할 지 며칠동안 감이 안잡혔는데 그래도 완성해서 기분이 매우 좋다.

## 16일
- 데일리 미팅 기능 구현한 걸 PR을 올리고 코드 리뷰를 받아서 알게된 점들을 코드로 공유해보겠다.
```
from django.db import models

class BaseModel(models.Model):
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    class Meta:
        abstract = True
```
- 코드 리뷰에서 개행을 넣어달라는 리뷰가 있었다.
  - 위 코드에서 `from django.db import models` 아래에 개행이 한 칸인걸 두 칸으로 바꾸고, 문서의 끝에는 항상 개행 한 칸을 넣어야 한다는걸 알게 되었다.
- iTerm2 Customiz를 했다. font, color를 변경하고 new line, highlighting 기능을 넣었다.

## 17일
곧 
