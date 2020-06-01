## 13일 전까지 했던걸 요약해보자면

### showmethatcode Hackathon
하나밖에 생각이 안난다.. <b>showmethatcode</b> 사람들과 해커톤을 진행했다. 이번에는 실제 유저들을 대상으로 서비스를 만들었다. [내게 맞는 댕댕이 찾기](https://showmethatcode.team/doggy/)인데 10개의 간단한 질문을 통해 귀여운 강아지를 추천해준다. 이 페이지를 만드는데 걸린 시간은 약 12시간, 처음엔 막막했다. 왜냐하면 jQuery를 맛보기 식으로밖에 공부를 안해서 아무것도 모르는 상태였기 때문이다. 그렇기에 이 해커톤을 통해 jQuery에 감동받았다. 확실한 정보는 아니지만 귀에 들려오는 소리에 의하면 현업에서는 jQuery를 잘 사용하지 않는다고 한다(왜일까?).. 모든 작업을 마치고 서버에 배포한 후 지인들에게 홍보를 해서 GA(Google Analytics)를 통해 사용자 수를 실시간으로 지켜봤다. 결과는 약 1200명 정도의 사람들이 이용했는데 엄청 뿌듯했다..!

### 정보처리기능사 실기 접수
11일부터 접수 시작인데 다음 날로 미뤘다가 큰일이 발생했다. 서울, 경기 지역 시험장에 자리가 다 마감된 것이다. 그래서 어쩔 수 없이 강원도 원주로 시험을 보러 떠난다 ;ㅁ; (매우 화남)<br>

## 13일
전에 Node로 만들었던 일기장 웹페이지를 Django로 다시 만들어보는 중이며 정보처리기능사 실기 공부도 함께 하고 있다.<br>
요즘 너무 바빠서(?) TIL을 못썼는데 오늘부터 다시 열심히 작성해야겠다.

## 14일
정보처리기능사 실기 책이 도착해서 가벼운 마음으로 공부해봤는데 엄청나게 어렵다. 그래도 코딩에 대한 얘기도 나오고 충분히 흥미로웠지만 알고리즘 순서도에 막막함을 느끼고 있다. 그래서 이기적 책에 나와있는 무료 강의로 들으면서 병행하고 있다.

## 15일
오늘도 역시나 정보처리기능사 순서도 공부를 했지만 아직도 감이 잘 안잡힌다.

### JavaScript 
> [벨로퍼트](https://learnjs.vlpt.us/)에서 공부했다.

#### null, undifined
> null과 undefined 는 둘 다 값이 없음을 의미하는건 맞는데, null 은 우리가 없다고, 고의적으로 설정하는 값을 의미하고, undefined 는 우리가 설정을 하지 않았기 때문에 없는 값을 의미합니다.

#### var, const, let
> 가급적 const, let 을 사용하자.

#### && , ||
> && = AND, || = OR

#### 논리 연산자

```js
const value = !((true && false) || (true && false) || !false);

# 논리 연산자 순서 = NOT > AND > OR
# 위 value의 결과값은 !true
```

#### 객체 비구조화 할당

```js
function print(hero) {
  const { alias, name, actor } = hero;
  const text = `${alias}(${name}) 역할을 맡은 배우는 ${actor} 입니다.`;
  console.log(text);
}
```

#### 배열

Object.entries: [[키, 값], [키, 값]] 형태의 배열로 변환<br>
Object.keys: [키, 키, 키] 형태의 배열로 변환<br>
Object.values: [값, 값, 값] 형태의 배열로 변환

---

알고 있던 내용을 더 자세하게 알 수 있어서 유익했고 즐거웠다.

## 17일

내가 Diary를 만들 때는 User 모델을 따로 만들었는데 알고 보니 Django에는 User모델이 기본적으로 있었다.

```py
from django.shortcuts import render
from django.conf import settings
from django.contrib.auth import get_user_model
from django.contrib.auth.models import User # 선언해주고

def sign_up(request):
  if request.method == 'POST':
    user_id = request.POST.get('sign_up_id', '')
    user_pw = request.POST.get('sign_up_pw', '')
    user = User.objects.create_user(user_id, '', user_pw) # .create_user()를 통해 회원가입이 이루어진다. 패스워드 암호화도 자동으로 된다.
    user.save()
    return render(request, 'sign_up.html', {
    });
```

Django.. 알면 좋지만 모르면 호구가 되는 느낌..이 든다!

## 18일

계속 회원가입 페이지가 잘 나타나다가 오류가 발생하고가 반복됐다.<br>
`The view accounts.views.sign_up didn't return an HttpResponse object. It returned None instead.` 이 에러가 발생하는데 왜 발생하는지 모르겠다.. 그래서 현재 카페에 있고 새벽까지 조금 더 해볼 예정이다..

## 19일

### `settings.AUTH_USER_MODEL` VS. `get_user_model()`

```py
class Diary(models.Model):
    #1. user = models.ForeignKey(settings.AUTH_USER_MODEL , on_delete=models.CASCADE)
    #2. user = models.ForeignKey(get_user_model(), on_delete=models.CASCADE)
    ...
```
기존에는 1번 코드를 사용했으나 [Stack Overflow](https://stackoverflow.com/questions/24629705/django-using-get-user-model-vs-settings-auth-user-model)에서 2번의 코드가 더 좋다고 해서 수정했다.(영어라 잘 해석한건지는 모르겠다..)<br>

### 로그인 인증

```py
from django.shortcuts import render, redirect
from django.conf import settings
from django.contrib.auth.models import User
from django.contrib.auth import get_user, authenticate, login # 이것이 핵심
from diary.models import Diary

def sign_in(request):
    if request.method == 'GET':
        user = get_user(request)
        return render(request, 'sign_in.html', {
        
        });
    if request.method == 'POST':
        user_id = request.POST['user_id']
        user_pw = request.POST['user_pw']
        error_message = '아이디 혹은 비밀번호를 확인해주세요'
        user = authenticate(request, username=user_id, password=user_pw)

        if user_id or user_pw == '': # 아이디 혹은 비밀번호가 입력되지 않았을 시
            error_message = error_message # 위의 error_message를 저장

        if user is not None: # 유저 데이터가 있다면
            login(request, user) # 조금 검색해봐야 할 것 같다(코드 흐름을 보면 대충 역할인지 느껴지는?)
            return redirect('/diary')

        else: # 오류처리
            error_message = error_message
            return render(request, 'sign_in.html', {
                'error_message': error_message
            })
```
혼자 코드를 짜서 해보려고 했으나 계속 `AnonymousUser`가 떠서 힘들었는데 검색해보니 authenticate, login 을 이용한 방법이 있었다.<br>

### Slang
창모의 노래를 듣다가 One hunnit 이 들려 궁금해서 검색해봤는데 100을 의미한다고 한다. I keep it 100 = I keep it real = I keep it hunnit (?) 이런 느낌이려나..

## 24일

요즘은 정보처리기능사 실기 공부를 열심히 하고 있다. 그리고 오늘은 코딩을 했다!<br>
오늘 알게된 점은 코드로 설명해보겠다.

```py
# urls.py
urlpatterns = [
    ...,
    path('<int:diary_id>/', detail, name='detail'),
]

# views.py
def detail(request, diary_id):
    user = get_user(request).id
    diary = Diary.objects.filter(user_id=user, id=diary_id).get()
    print(diary_id) # http://127.0.0.1:8000/diary/12/ 이면 console에 12가 찍힌다.
    return render(request, 'detail.html', {
        'diary': diary
    })
```
detail 함수에 두번째 인자에 diary_id를 주면 url로부터 id값을 받아올 수 있었다.

## 25일

오늘은 Diary HTML/CSS 작업을 했다. 오랜만에 하는거라 다 까먹었고, 사실 전에는 내가 원하는 위치에 요소들을 넣기 위해서 코드가 어떤 역할을 하는지도 잘 모른 상태에서 때려 박았다. 그래서 같이 미팅하는 분에게 <b>Codeit</b> 계정을 빌려서 자세하게 공부하고 복습하는 시간을 가졌다.
### 학습한 내용
`overflow`, `border-radius`, `background-color: transparent`, `box-shadow`, `box-sizing: border-box`

## 26일

정보처리기능사실기에서 순서도 함수에 대해 공부했다.<br>
`ABS(X)`, `INT(X)`, `SQRT(X)`, `MOD(X,Y)`, `LEFT(X,Y)`, `RIGHT(X,Y)`, `MID(X,Y,Z)`, `VAL(X)`<br>
디버깅 표랑 피보나치 수열에 대한 내용도 읽었는데 디버깅 표의 흐름은 알겠으나, 문제에 맞는 값을 어떻게 넣어줘야 할 지 잘 모르겠다. 피보나치 수열은 단순했다. 1,1,2,3,5,8,... 처럼 연속된 2개 항을 합하여 새로운 항을 생성하는게 피보나치 수열이다!

## 27일

웹 퍼블리싱 공부하다가 가운데 수직 정렬을 보다 효율적으로 하는 방법에 대해 찾아봤다.
### 구글링을 통해 학습한 내용
1. `position: relative;` > `top:50px` 이렇게 top에 값을 줘서 위치 조정하기
2. `display: table-cell;` > `vertical-align: middle;` div 태그를 테이블처럼 만들기

### 미팅하는 분에게 배운 방법
1. `top: calc(50% - 50px);` 인데 CSS에도 함수가 있다는걸 처음 알게된 순간
2. `left: 50%` > `top: 50%` > `transform: translate(-50%, -50%)`, `transform`이 생소하지만 유용해보인다. 리서치가 필요함

## 28일

정보처리기능사 공부를 했고, 코딩 할 때 <b>VSCode</b>를 사용하는데 <b>Pycharm</b>으로 해보고 있다. 장고를 할 때는 적어도 Pycharm을 사용해야 효율적인 작업을 할 수 있을 것 같다(미미하게나마).

## 29-30일

군대에서 휴가 나온 친구들이 두 명이나 돼서 이 날은 하루종일 놀았다!!

## 31일

이 날은 TypeScript에 대해 검색해보고 공부도 조금 해봤다.

### TypeScript

- 컴파일 언어, 정적 타입 언어이다. JS는 인터프리터 언어지만, TypeScript는 컴파일 언어로 코드 수준에서 미리 타입을 체크하여 오류를 체크해낸다. 단 전통적인 컴파일 언어와는 다르게, 링킹 과정이 생략되어 있다.
- 타입 스크립트 = 자바스크립트 + 타입
    * 컴파일 단계에서 타입 오류를 잡아낼 수 있고, 코드 어시스트 기능도 지원받을 수 있다.
    * 이것을 통해 암묵적 형변환, 호이스팅, 복잡성 문제를 해결할 수 있다.

### Destructuring
> TypeScript 검색해보다가 신기해서 적어 봄!
```ts
var param = ['점수는..?!', 100];
let [name, num] = param;

console.log(`
message: ${name}
score: ${num}
`);
```
