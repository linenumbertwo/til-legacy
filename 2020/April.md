## 1일

오늘은 친구와 볼링을 쳤는데 192점으로 최고 기록을 갱신했습니다. 그래서 취업하고 자신에게 마이볼을 선물해야겠습니다.<br>
그리고 서점에 가서 <b>ELON MUSK</b> 책을 샀습니다. 주변에서 정말 좋은 책이고 동기부여도 된다 소리를 들어서 읽어보고 있습니다.<br>
조금 읽었는데도 일론 머스크님에게 존경을 표할 정도로 대단함을 느끼고 있습니다.<br>
아 그리고 이번 주 <b>showmethatcode</b> 분들과 만나서 1분기 회고를 하기로 했기에 미팅 후 회고 내용 정리해서 작성하겠습니다.

## 2일

오늘은 <b>ELON MUSK</b> 책을 읽었다. 책을 안좋아하는 사람임에도 불구하고 집중하고 몰입하게 되었다. 그만큼 유익했다는 소리이다.<br>
일론 머스크는 엄청 뛰어난(똑똑한) 사람임에도 누구보다 성실했으며 모두가 불가능하다고 생각하는걸 가능으로 실현해낸다.<br>
내가 일론 머스크처럼 똑똑했더라도 <b>인류</b>를 위하지 않고 오직 <b>나</b>를 위해 살았을 거라고 어느정도 확신한다.<br>
단순히 글로만 쓰여진 일론 머스크의 연설을 읽는데도 가슴이 두근거렸다. 나름 요즘 열심히 살고 있다고 생각했는데 아닌거같다.<br>
나도 <b>"불가능을 가능으로"</b> 라는 생각을 갖고 남들보다 뛰어난 사람이 되고 싶다는 욕심이 생겼다. 

## 3일

요즘 코로나 바이러스 때문에 재택을 하는 사람들이 많아져서 내가 가는 스타벅스에 자리가 없다. 그래서 친구랑 만화카페를 갔다.<br>
생각보다 넓고 쾌적했으며, 개인 공간도 있고 자유로워서 엄청 만족스러웠다. 카페에 비하면 가격이 더 비싸지만 큰 차이는 없다.<br>
약 한시간 동안 <b>ELON MUSK</b> 책을 읽다가 친구가 과제를 할 때 나도 정보처리기능사 공부랑 코딩을 했다.<br>
웹 퍼블리싱 내용을 공부했다. `relative`, `fixed`, `absolute` 포지셔닝 및 `margin & padding`, `width & height` 등 기본적인 내용을 공부했습니다. 전에 만들었던 Diary CSS 코드가 너무 지저분해서 refactoring 해보려고 합니다.

## 4일

매 주 토요일은 정기휴일이다. 근데 제대로 놀지도 않고 의미없는 하루였다.<br>
<b>ELON MUSK</b> 책 조금 읽고 정보처리기능사 공부를 했다.

## 5일

오늘은 <b>showmethatcode</b> 사람들과 1분기 회고를 했다. 내가 회고했던 내용의 핵심을 짚어보자면<br>
1. 코딩과 많이 친해져서 웬만한 언어를 습득할 때 비교적 빨리 익힐 줄 알았는데 전혀 아니라서 실망스러웠다.
2. 영어 공부를 꾸준히 하기로 마음 먹었었는데 전혀 하고 있지 않다.
3. 공부를 할 때 날 위해서 하는게 아니라 보여주기식 공부를 하는 것 같다(미팅에서 TIL 공유하는걸 말함).
4. 요즘 카페 갈 때 친구와 함께 가는데 그로 인해 공부 집중이 더욱 안되는 것 같다.

1분기는 10점 만점에 6점을 줬다. 가장 큰 요소였던 게임에 흥미를 잃었고 코딩에 더 집중할 수 있는 발판이 될 수 있다고 생각한다.<br>

### 계획
1. 친구한테 양해 구하고 보다 집중적으로 공부하기
2. 아침에 일어나서 휴대폰 사용하지 않기(유튜브에 쓰는 시간이 많기에 일어나서 바로 씻고 카페가기)
3. 데일리 목표 공유하기(오후 1시이전, 최소한의 목표)
    - ex) VSCode 열기, 슬랙에 아침 인사 하기 등 (시작이 어렵기 때문)

### showmethatcode 공동의 목표
- earlybirds 필수 기록하기(일어난 시간)
    - 규칙적인 생활을 지키는게 목표

## 6일

오늘 새벽에 가슴이 답답해서 잠을 잘 못잤다. 코로나일까 의심도 하고 저녁을 급하게 먹어서 체했을 수도 있어서 새벽 3시에 동네를 뛰어다녔다.<br>
다행히 자고 일어나니 답답함은 사라졌지만 약 1시에 일어났고, 어제 회고에서 세운 계획 2번 3번을 지키지 못했다 ;ㅁ;<br>
Node Slack SDK를 이용해 Slack Bot을 간단하게 만들어봤다.

```
require('dotenv').config();
const { RTMClient } = require('@slack/client');
const token = process.env.SLACK_TOKEN
const rtm = new RTMClient(token);

rtm.start();

rtm.on('message', (message) => {
    var text = message.text
    if(text==="구글"){
        rtm.sendMessage("google.com", message.channel)
    }
});
```

이렇게 쉬운걸 괜히 botkit에 집착해서 시간만 낭비했다.. Google URL Parameter 추출하려고 이것저것 공부하다가 시간을 보냈다.

## 7일

이제 구글링 대신해주는 봇을 만들기 위해 `axios`, `cheerio`를 이용하려고 했다. 왜 이렇게 생각했는지 모르겠지만 크롤링을 해야 한다고 생각했다.
여러 웹 사이트를 크롤링 해보면서 공부했다. `axios`로 HTTP 파일을 가져오고, `cheerio`로 값을 빼내온다 라고 이해하고 있다.

```
// axios로 HTTP 가져오기
const getHtml = async () => {
  try {
    return await axios.get("https://www.yna.co.kr/sports/all");
  } catch (error) {
    console.error(error);
  }
};

// cheerio로 원하는 값 가져오기
getHtml()
  .then(html => {
    let ulList = [];
    const $ = cheerio.load(html.data);
    const $bodyList = $("div.headline-list ul").children("li.section02");

    $bodyList.each(function(i, elem) {
      ulList[i] = {
          title: $(this).find('strong.news-tl a').text(),
          url: $(this).find('strong.news-tl a').attr('href'),
      };
    });

    const data = ulList.filter(n => n.title);
    return data;
  })
  .then(res => log(res));
```

## 8일

오늘은 야매로 구글봇을 완..성했다?

```
rtm.on('message', (message) => {
    var text = message.text
    var google_text = text.slice(4);
    if(google_text){
        rtm.sendMessage(`google.com/search?q=${google_text}`, message.channel)
    }
    console.log(text)
});
```

슬랙 채널에서 메세지를 받아온 후, slice로 `!구글` 명령을 잘라내고 키워드만 빼내와서 링크에 넣어주는 방식이다.<br>
동작은 되는데 조건에 `!구글` 명령어에만 반응할 수 있게, 공백 처리도 해줘야한다. 머리 회전이 안되므로 내일로 미룬다.

## 9일

### 오늘의 TMI

1. GitHub Repository에 License가 없으면 다른 사람들이 사용할 수 없다라는 사실을 알고 충격을 받았다.
2. PR을 받을 때 커밋이 2개 이상인 경우에는 `Squash Merge` 아니라면 `Rebase Merge`
3. Markdown 사용할 때 Backtic(```)옆에 js를 붙이면 하이라이팅이 된다.

### 오늘의 TIL

<b>객체지향 자바스크립트의 원리</b>라는 책을 읽었다. 원시 타입과 참조 타입에 대해 공부했고 여러모로 처음 알게된 사실들이 있었다.

```js
// 대표적인 녀석
var color1 = "red";
var color2 = color1;

console.log(color1); // red
console.log(color2); // red

color1 = "blue";

console.log(color1); // blue
console.log(color2); // red
```
Googling-Bot에서 어제는 `!구글` 말고도 `!검색`, `세글자` 이렇게 세글자만 입력해도 반응했는데 이제는 `!구글`에만 반응하게 만들었다.<br>
아직 여러가지 약점들이 많고 코드도 매우매우매우 허접해서 고칠게 많은 것 같다. 그래서 행복하다 ^^;

```js
rtm.on('message', (message) => {
    var text = message.text // 슬랙 전체 메세지 
    var googling_keyword = text.slice(4); // 검색할 내용 
    var call_sign = text.slice(0,3); // !구글 
    if(call_sign==="!구글"){
        rtm.sendMessage(`google.com/search?q=${googling_keyword}`, message.channel)
    }
});
```

## 10일

Googling-Bot을 완성했다. 좋은 코드로 만들지 못한게 아쉽지만 원하는 기능을 구현했다는거에 만족하고 있다. 어떻게 보면 내가 만든 슬랙 봇 중에서 그나마 실용성이 있는 것 같기 때문이다. 오늘은 공백을 `+`로 치환해주는 작업을 했다. 치환하는 이유는 구글 검색을 할 때 쿼리에서 공백을 `+`로 표현하기 때문이다. 최종적으로 `replace()`를 사용했고 이를 위해 <b>정규표현식</b>을 공부했다.

```js
require('dotenv').config();
const { RTMClient } = require('@slack/client');
const token = process.env.SLACK_TOKEN
const rtm = new RTMClient(token);

rtm.start();

rtm.on('message', (message) => {
    var text = message.text // 슬랙 전체 메세지
    var googling_keyword = text.slice(4); // 검색할 키워드
    var googling_detail_keyword = googling_keyword.replace(' ',"+") // 공백을 + 로 치환
    var call_sign = text.slice(0,3); // !구글
    console.log(googling_detail_keyword);
    if(call_sign==="!구글"){
        rtm.sendMessage(`https://www.google.com/search?q=${googling_detail_keyword}`, message.channel)
    }
});
```
최종적인 코드는 이러하고 [여기](https://github.com/indante/Googling-Bot)에 올렸슴다.<br>
### 시간복잡도
> 알고리즘이 문제를 해결하기 위한 연산(시간)의 횟수를 말한다.

시간복잡도를 공부하고 있는데 뭔지 감을 못잡았다. <b>피보나치 연산</b>, <b>Big O 표기법</b> 등 내일 더 공부해봐야겠다. 

## 12일

Googling-Bot을 조금 더 나은 방향으로 개선해보는 시간을 가졌다. `!구글` 말고도 `!google`, `!Google`에도 반응할 수 있게 코드를 추가해줬고 테스트 하던 중 공백이 두 개 이상 들어가면 + 로 치환해주지 않아서 코드를 수정했다. 기존에는 `.replace(' ', '+')` 코드였는데 `.replace(/ /gi, '+')`로 수정해줬다.

### 오늘 알게된 간략한 정규표현식
- g: 발생할 모든 패턴에 대한 전역 검색
- i: 대/소문자 구분 안함

[Googling-Bot](https://github.com/indante/Googling-Bot) 사용법을 정리했다.<br>

## 13일

이제 정보처리기능사 필기 시험 일주일 전이라 기출문제를 많이 풀어보고 있슴. <b>이기적</b>을 통해 모바일로도 시간 날 때마다 풀어보고 있는데 좀처럼 점수가 안나와서 문제임 100점 중 60점만 넘기면 되는데.. 오늘 정보처리기능사 공부 시간은 약 3시간 정도 했다. 그리고 Googling-Bot이 Slack Thread에서는 작동되지 않아서 Event가 있나 찾아보고 시도해봤지만 성공하지 못했다. 그 외에 <b>showmethatcode</b> Sprint 작업이 있어서 삽질만 했다. 오늘 총 공부시간? 카페에 있던 시간은 약 5시간 30분 정도 된다.

## 15일

Googling-Bot이 갑자기 오류가 나서 제대로 작동되지 않는다. 그래서 해결하려고 삽질좀 하는데 해결하지 못했다. 당장 다음 주에 정보처리기능사 시험이라 오늘 하루는 기출문제를 계속 풀었고 평균적으로 7~80점이 나와서 걱정은 조금 사라졌다.

## 16일

### Googling-Bot

종합적으로 여러가지 에러들이 발생하고 있다.

```js
// Error 1
https://www.google.com/search?q=+didn’t unfurl https://www.google.com/search?q= because it was already shared in this channel quite recently (within the last hour) and I didn’t want to clutter things up.

// Error 2
TypeError: Cannot read property ‘slice’ of undefined
var korean_googling_keyword = text.slice(4);
```
정확한 원인이 뭔지는 모르겠다. 에러가 단순히 한 줄만 뜨는게 아니라 코드가 실행되고 있는 동안 while문이 도는 것 처럼 계속 발생한다.
작동 전에 시도했던건 `npm update`를 해준 것 밖에 없는데 갑자기 작동이 된다. 여러 번 테스트해봐야 알 수 있을 것 같다.
그리고 `!구글 어디서?` 처럼 특수기호가 들어가면 특수기호는 검색해 주지 않는 버그를 발견해서 해결해야할 것 같다.

### 정보처리기능사

오늘은 정보처리기능사 기출문제만 약 10번 정도 푼 것 같다. 점수대는 평균 80점 정도로 올랐고 문제 정답을 아예 외워버리고 있다. 그래도 안정권으로 들어 와서 다행이다.

## 17일

### Googling-Bot

특수기호가 검색되지 않는 점을 수정했고 이로 인해 코드도 더욱 깔끔해졌다. `encodeURIComponent`를 통해 인코딩을 해줬다.
- `encodeURI`: A-Z a-z 0-9 - _ . ! ~ * ' ( ) 등을 제외하고 인코딩하는 함수
- `encodeURIComponent`: 모든 문자를 인코딩하는 함수
처음엔 두 함수가 헷갈렸지만 찾아보니 명확해졌다. 느낌표가 인코딩 되지 않는게 아쉬웠지만 그래도 코드가 간결해져서 좋다.

```js
// 기존엔 여섯 줄 이었음
var korean_call_sign = text.slice(0,3);
var korean_googling_keyword = encodeURIComponent(text.slice(4));
var english_call_sign = text.slice(0,7)
var english_googling_keyword = encodeURIComponent(text.slice(8));
```

### 정보처리기능사

오늘도 기출문제 여러 번 풀었는데 다 합격 받았다!

## 18일

<b>showmethatcode</b> 페이지에 추가 작업을 하려고 마음 먹은 날이다. 새로운 Branch를 생성 중 Branch Naming에 대해 찾아봤다.

### Branch Naming

#### Master Branch
배포(Release) 이력을 관리하기 위해 사용. 즉, 배포 가능한 상태만을 관리한다.

#### Develop Branch
기능 개발을 위한 브랜치들을 병합하기 위해 사용. 즉, 모든 기능이 추가되고 버그가 수정되어 배포 가능한 안정적인 상태라면 develop 브랜치를 ‘master’ 브랜치에 병합(merge)한다. 평소에는 이 브랜치를 기반으로 개발을 진행한다.

#### Feature Branch
feature 브랜치는 새로운 기능 개발 및 버그 수정이 필요할 때마다 ‘develop’ 브랜치로부터 분기한다. feature 브랜치에서의 작업은 기본적으로 공유할 필요가 없기 때문에, 자신의 로컬 저장소에서 관리한다. 개발이 완료되면 ‘develop’ 브랜치로 병합(merge)하여 다른 사람들과 공유한다.

#### Relase Branch
배포를 위한 전용 브랜치를 사용함으로써 한 팀이 해당 배포를 준비하는 동안 다른 팀은 다음 배포를 위한 기능 개발을 계속할 수 있다. 즉, 딱딱 끊어지는 개발 단계를 정의하기에 아주 좋다.

#### Hotfix Branch
출시 버전에서 발생한 버그를 수정 하는 브랜치

> 자세한 내용은 [여기](https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html)에서 볼 수 있다.<br>
----------------

오랜만에 장고를 다뤄서 낯설었다. 가상 환경 설정도 안하고, 환경 변수 세팅하는데도 오래 걸렸다. 세팅 다 끝내고 코드 실행해서 메인 페이지에 접속하는데 들어가지지 않는다.. 원인을 모르겠고 해결을 못한 상태이다.

## 19일

아무래도 내일 정보처리기능사 필기 시험 당일이라서 집중적으로 기출문제를 풀고 있다. 점수는 안정적인데 혹시 모를 일에 대비해서 하루 종일 기출문제를 풀 예정이다.

## 20일

정보처리기능사 필기 시험을 보고 왔는데 합격했다. 61점으로 간신히 턱걸이 했는데 오히려 기분이 더 좋았다. 그래서 오늘은 신나게 놀았다!(술, 당구)

## 21일

오늘 친구들과 아침 일찍 볼링을 치러 갔는데 치는 중간에 허리와 허벅지가 끊기는 듯한 통증이 있어서 병원에 가서 치료를 받았다. 가만히 앉아 있어도 허리 통증이 있어서 카페에 있다가 만화 카페로 넘어가서 누워서 책을 읽었다. <b>ELON MUSK</b>랑 <b>Two Scoops of Django</b>라는 책을 읽었다. 장고 책은 개념을 익히자는 생각으로 읽었는데 내용이 정말 어렵고 이해가 거의 안됐다. 내일은 코딩을 좀 열심히 하고 싶다.

## 22일

[showmethatcode](https://showmethatcode.team/) 페이지에서 비밀글로 작성 기능을 구현하려고 노력 했다. 지금은 권한이 없어도 접속 되지만 이 기능을 구현하고 나면 달라질 것 이다. 오늘 알게 된 내용은 여러가지로 삽질을 하다가 HTML checkbox를 추가하고, checkbox를 눌렀는지 안눌렀는지의 여부를 확인하고 그 데이터를 통해  비밀글로 작성될 지 판단된다. 그 데이터를 가져오기 위해서 view에서 `checkbox = request.POST.get('test')`로 가져오고 print 찍어보니 데이터가 가져와졌다. 이걸로 내일 완성지을 수 있을 것 같다.

## 23일

기대와 다르게 완성하지 못했음.. 또 다른 방안을 생각해냈는데 모델에 checkbox 관련 필드를 생성해서 해보려고 한다.

## 24일

우선 `is_secret`라는 필드를 생성하고 checkbox 여부를 데이터로 담으려고 했다. 첫번째로 모델 필드 타입을 `BooleanField`로 했는데 체크박스를 누르지 않을 시, Null 값이 나와서 제대로 값이 들어가지 않음.. 여러모로 시도해보다가 최종적으로 `NullBooleanField`로 변경하고 누르지 않을 시 Null값이 들어가는 방법으로 해보고 있다. 또 완성은 못했는데 내일..은 약속이 있으니 모레 완성할 수 있지 않을까 싶다!

## 26일

checkbox를 체크하면 on이 출력되고 체크하지 않으면 Null이 출력 된다. 그래서 `is_secret = request.POST.get('is_secret', '')  == 'on'`값을 줘서 True로 반환시킨다. 그리고

```py
if request.user.is_authenticated:
  is_team_member = request.user.is_team_member
else:
  is_team_member = False
# is_team_member = request.user.is_team_member if request.user.is_authenticated else False // 삼항연산자도 알게 됐다.
```
로 팀에 속해있는 유저인지 판별하는 변수를 생성하고 템플릿에 넘겨준다. 이 코드를 이용해서

```
{% if sharing.is_secret and not is_team_member %}
  비밀글임
{% else %}
  {{ sharing.til|linebreaksbr }}
{% endif %}
```

비밀글(is_secret)로 작성했는데 팀 멤버가 아닐 시 내용이 보여지지 않는 식의 코드를 구현했다. 도움을 받긴 했지만 그래도 내용을 들으면서 바로바로 이해가 됐다.

## 27일

이력서를 쓰고 있는데 내가 만들었던 일기장, 팀 페이지, 슬랙 봇 등 여러 가지 미흡한 코드들을 개선하고 있다. 아마 내일도 이렇게 할 예정이다!

## 28일

오늘도 어제처럼 진행했는데 잠을 잘 못자서인지 꾸벅꾸벅 졸고 집중을 제대로 하지 못했다.

## 29일

Googling-Bot의 변수들을 camelCase로 변경해줬다. 그리고 일기장 코드 개선 중, 인코딩 타입이 잘못되어있어서 한글로 글이 작성이 안됐다. 이걸 이제 알았다는 사실에 충격을 금치 못했다. 그래서 내일은 인코딩 먼저 해주고 작업해야겠다.

## 30일

계속 작업하다 보니까 전체적인 코드가 마음에 들지 않았다. 예를 들어서 로그인 실패 했을 때 오류 메세지를 `encodeURIComponent("로그인을 확인해주세요")` 같이 redirect 시키는 방법이다. 그래서 이번 주 내로 코드를 아예 갈아엎고 다시 해볼 생각이다. 이런 생각을 갖고 나서 엄청 마음이 무거워서 터미널을 꾸미면서 마음을 다스렸다. 원래는 엄청 지저분했는데 `powerlevel10k`로 변경했는데 엄청 깔끔해졌다. `vim ~/.zshrc`에 `ZSH_THEME=` 값을 `"powerlevel10k/powerlevel10k"`로 넣어주고 `source ~/.zshrc`해주니까 매우 간편하게 디자인 할 수 있었다(물론 이거 말고도 iTerm2, powerlevel10k, Oh My Zsh를 다운 받아야 한다). 그래서 기분이 매우 좋다.