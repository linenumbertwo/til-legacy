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
곧 군대가는 친구를 기념하여 친구들과 만나서 술을 먹었다. 원래 술을 못먹는 나지만 어제는 생각보다 잘 먹었다. 원래 내 주량은 한 병인데 어제는 두병 반 정도를 먹은 것 같다.
3차를 마무리 짓고 집을 가려던 찰나에 역시나 토를 했다 ;ㅁ; 오늘 공부를 못한 만큼 내일 더 열심히 해야 겠다.

## 18일
장고 튜토리얼 말고 오늘은 장고걸스를 보며 공부를 하는데 기분이 이상했다. `reverse()`, `len()`, `pop()`, `append()` 등 프로그래밍을 처음 접할 때 많이 사용했었고
신기해 하던 자신이 떠올랐다. 마침 피아노 연주 들으면서 공부 하는데 기분이 묘하다.
- 전에는 리스트와 딕셔너리 각각 언제 써야할 지 몰랐는데 장고걸스에 간단하게 정리가 되어 있다.
  - 리스트: 아이템 정렬이 필요할 때
  - 딕셔너리: 키(key)과 값(value)이 서로 연관되어 있거나, 효과적으로 (키를 사용해서) 어떤 값을 찾을 때
    > 딕셔너리는 리스트와 유사하지만, 변경(mutable)할 수 있습니다. 딕셔너리가 만들어진 후에도, 그 값을 마음대로 변경할 수 있다는 뜻입니다. 키/값을 나중에 추가할 수 있습니다.
- `range()`: 한창 for문을 사용할 때 난 이게 함수인지 몰랐고 지금까지도 몰랐다. 지금이라도 알게 되서 다행이다;;
```
# 인수 1개 - 시작 숫자를 지정해 주지 않으면 range 함수는 0부터 시작한다.
>>> list(range(5))
[0, 1, 2, 3, 4]

 # 인수 2개 - 입력으로 주어지는 2개의 인수는 시작 숫자와 끝을 나타낸다. 단, 끝 숫자는 해당 범위에 포함되지 않는다.
>>> list(range(5,10))
[5, 6, 7, 8, 9]

 # 인수 3개 - 세 번째 인수는 숫자 사이의 거리를 말한다.
>>> range(1,10,3)
[1, 4, 7]
```

- 장고(Django)란<br>
여태껏 공부하면서 장고는 뭐지? 왜 만들었지? 이런 호기심을 품어본적이 없다. 그냥 당연하듯이 어떤 특성이 있는지도 모른채 공부만 했다. 앞으로는 Python, JavaScript, Django 등 공부를 하더라도 그 언어에 대한 호기심을 품고 공부해야겠다. [djangogirls](https://tutorial.djangogirls.org/ko/django/) 엄청 좋은 것 같다.
- Model<br>
`class Post(models.Model)`는 모델을 정의하는 코드이다.
`class`는 특별한 키워드로, 객체를 정의한다는 것을 알려준다. `Post`는 모델의 이름이고 항상 클래스 이름의 첫글자는 대문자로 써야 한다. `models`는 Post가 장고 모델임을 의미한다. 이 코드 때문에 장고는 Post가 데이터베이스에 저장되어야 한다고 알게 된다.
- Django template extending(장고 템플릿 확장)<br>
템플릿 확장이란 웹사이트 안의 서로 다른 페이지에서 HTML의 일부를 동일하게 재사용할 수 있다는 뜻이다. 이 방법을 사용하면 동일한 정보/레이아웃을 사용하고자 할 때, 모든 파일마다 같은 내용을 반복해서 입력할 필요가 없게 된다.

```
# base.html
{% load static %}
<html>
    <head>
        <title>Django Girls blog</title>
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
        <link href='//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext' rel='stylesheet' type='text/css'>
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    </head>
    <body>
    <div class="page-header">
        <h1><a href="/">Django Girls Blog</a></h1>
    </div>
    <div class="content container">
        <div class="row">
            <div class="col-md-8">
            {% block content %}
            {% endblock %}
            </div>
        </div>
    </div>
</body>
</html>
```

```
# post_list.html
{% extends 'blog/base.html' %}

{% block content %}
    {% for post in posts %}
    <div class="post">
        <div class="date">
            <p>{{ post.published_date }}</p>
        </div>
    <h1><a href="">{{ post.title }}</a></h1>
    <p>{{ post.text|linebreaksbr }}</p>
    </div>
    {% endfor %}
{% endblock %}
```

위처럼 `base.html`에 반복되는 내용을 입력한다. 다른 HTML 파일에서 제일 위에 `{% extends <base 경로> %}`를 넣고 제일 마지막에 `{% endblock %}`을 선언해주면 `base.html`을 불러올 수 있다.

## 19일

- `|linebreaksbr`: 블로그 글 텍스트에서 행이 바뀌면 문단으로 변환하도록 하라는 의미입니다.
  > 행바뀜을 문단으로 변환하는 필터를 적용한다는 표현을 쓰기도 함
- PythonAnywhere<br>
전에는 Heroku, AWS를 사용했었는데 이번에 장고걸스를 따라하면서 PythonAnywhere로 배포해봤습니다.
  > 개인적으로 Heroku, AWS보다 배포 과정이 매우 쉬워서 학습하는데 편리함이 있었음

## 20일

이제 데일리 미팅에서 유저가 글 작성을 하면 그 유저에 맞는 이미지를 띄워주려고 시도했습니다.
`{% static 'images/hoseon.png' %}`를 for문으로 돌리고 있는데 코드를 어떻게 짜야 동적으로 작동할지 모르겠습니다.
`{% static 'iamges/{{ sharing.user }}.png' %}`로 그냥 해봤지만 역시나 안되고 하루종일 삽질해도 해결을 못했습니다.

## 21일

쉬려고 했던 날인데 할 게 없어서 코딩을 조금 했슴다. 이미지 띄우는건 나중으로 미루고(중요하지 않기에) 우선 유저가 글을 여러번 작성하지 못하게 
하는 코드를 짜는데 이거는 생각보다 쉬울 것 같다고 생각을 했지만 코드로 나타내지 못했습니다. 그래서 내일은 집중해서 완성해서 코드를 올려보겠습니다.

## 22일

결과를 먼저 말씀 드리자면 기능은 구현 해냈지만 허비한 시간이 너무 많았습니다. 이 기능은 당일 날 글을 작성하면 글 작성하는 박스가 사라지게끔(if문을 통해) 구현하는건데 
전혀 상관없는 `def write(request):`에서 몇시간동안 삽질을 했고, 나중에서야 `def home(request):`에서 작업을 했습니다.

```
# views.py

def home(request):
    if request.method =='GET':
        sharing_groups = SharingGroup.objects.all().order_by('-date')[:7]
        sharing_today = Sharing.objects.filter(user=request.user, created_at__date=datetime.date.today()) 
        can_check_in = len(sharing_today) == 0

        return render(request, 'sharings.html', {
            'groups': sharing_groups,
            'can_check_in': can_check_in,
        })
```

템플릿은 form을 `{% if can_check_in %} {% endif %}`로 감싸주고 데이터가 없으면 write가 나타나고 없으면 사라지는 식으로 기능을 구현했습니다.

## 23일

오늘 미팅 때 저희가 개발한 웹페이지로 진행을 하고 싶어서 AWS 계정 생성하고 배포를 진행했습니다.<br>
EC2와 RDS로 구축을 진행 중인데 인스턴스에서 코드 clone 받고 세팅 하는데 에러가 발생했습니다.<br>
`ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.`
이 에러 말고도 Python Version Error, Django Version Error 가 있었습니다.<br>
해결하려고 구글링 해서 시도를 해보기도 하고, 인스턴스 삭제해서 ubuntu version을 바꿔서 해보기도 했지만 해결하지 못했습니다.

## 24일

제 목표는 3~4월쯤에 취업하는 것이기에 이력서를 준비하고 있습니다. 공부한 시간에 비해 쓸 내용도 없고 아는 것도 없어서 걱정이 됩니다.<br>
이미지 파일을 동적으로 나타내는 코드를 구현하고 있습니다. 전부터 미루던 기능인데 이제서야 마무리 단계에 들어서서 시도해볼 예정입니다.

## 25일

중학교 동창 친구들과 모여서 놀기로 했기에 공부를 하지 못했지만 매우 즐거웠습니다👍

## 26일

정보처리기능사 필기 접수를 신청했고 공부 하고 있습니다. 아무래도 이번 해에 산업기능요원으로 취업해야 하기 때문에 자격증을 꼭 따야 합니다.<br>
이미지 파일을 동적으로 나타내는 기능을 구현했고 이제 AWS에 배포만 끝낸다면 저희 미팅 때 사용할 수 있을 것 같습니다.

```
def user_profile_images(self):
    get_user_profile_images = {
        'user1@gmail.com': static('images/woosik.png'),
        'user2@gmail.com': static('images/hyeonsu.png'),
        'user3@gmail.com': static('images/hoseon.png'),
        'user4@gmail.com': static('images/sangmin.png'),
    }
    return get_user_profile_images[self.email]
```
이렇게 메소드를 생성해서 템플릿에 넘겨주는 방법으로 구현했습니다.