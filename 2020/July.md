## 2일
오늘은 `Statement`라는 이름으로 앱 개발을 시작했다(Django). 시간이 없기도 했는데 간단히 모델링만 진행했다. 모레 토요일부터 월요알까지 <b>showmethatcode</b>분들과 제주도를 가기로 했다.

## 3일
항상 동네 미용실만 다니다가 헤어 스튜디오? 같은 느낌의 미용실을 다녀왔다. 투블럭만 고집해왔다가 이제 질려서 매직 + 다운펌을 해봤는데 만족스럽다.

## 4~6일
showmethatcode in Jeju

## 7일
지원할 회사들을 알아보고 <b>드림 코딩</b>에서 JavaScript 공부를 했다.

## 8일

### REST란
REST는 HTTP기반으로 필요한 자원에 접근하는 방식을 정해놓은 아키텍쳐이다.<br>
REST는 자원(resource), method, message 세 가지로 구성되어 있다.

### Resourece
REST에서 자원에 접근할 때 URI로 하게 된다.

#### '/'의 쓰임새
슬래시(/) 구분자는 계층 관계를 나타내는 데 사용

ex: `http://www.showmethatcode.team/doggy/bulldog`<br><br>
'doggy'부터 하위 소속들을 거쳐서 'bulldog'까지 도달하는 구조임을 알 수 있다.<br> 
그렇기 때문에 URI 마지막 문자로 슬래시(/)를 포함하지 않는다.

- URI를 이루는 자원들은 동사보다는 명사로 이루어져야 한다.

- URI에서는 '_'(언더바)보다는 '-'(하이픈)을 권장한다.
    > 가독성이 중요한 '_'은 자원 해석에 혼란을 줄 수 있기 때문이다.

- URI 경로에는 소문자가 적합하다.
    > 대소문자에 따라 다른 자원로 인식하게 되기 때문이다.

### HTTP Method
- POST: POST를 통해 해당 URI를 요청하면 리소스를 생성한다.
- GET: GET를 통해 해당 리소스를 조회한다. 리소스를 조회하고 해당 도큐먼트에 대한 자세한 정보를 가져온다.
- PUT: PUT를 통해 해당 리소스를 수정한다.
- DELETE: DELETE를 통해 리소스를 삭제한다.

### REST의 장/단점

#### 장점
1. 언어와 플랫폼이 독립적이다.
2. SOAP(다른 통신방식)보다 개발이 쉽고 단순하다.
3. REST가 지원하는 프레임워크나 언어등 도구들이 없어도 구현이 가능하다.
4. 기존 웹 인프라가 사용 가능하다. HTTP를 그대로 사용하기 때문에

#### 단점
1. HTTP 프로토콜만 사용이 가능하다.
2. p2p 통신 모델을 가정했기 때문에 둘 이상을 대상으로 하는 분산환경엔 유용하지 않다.
3. 보안, 정책등에 대한 표준이 없기 때문에 관리가 어렵고 이러한 부분까지 고려해서 구현 할 경우 설계나 구현에서 좀 더 어려움을 갖는다.

- - -

회사 자격요건에 <b>REST API에 대한 이해</b>를 요구해서 뭔가 하고 찾아봤다. 내가 이해한게 맞다면 단순히 슬랙봇 만들때 사용한..? 혹은 HTTP 통신 흐름에 대한 이해를 요구하는 것..?

### JavaScript ES5+

#### Ternary operator 

```js
const name = 'ellie2';
console.log(name === 'ellie' ? 'yes': 'no');
```

#### Switch statement

```js
const browser = 'Chrome';
switch (browser) {
    case 'IE':
        console.log('go away!');
        break;
    case 'Chrome':
    case 'Firefox':
        console.log('love you!');
        break;
    default:
        console.log('same all!');
        break;
}
```
비슷한 형식으로 반복되는 조건문이라면 if보다 switch를 사용하는게 타이핑하기 더 수월할 것 같다.

#### Quiz
Q1. iterate from 0 to 10 and print only even numbers (use continue)

```js
for (let i = 0; i < 11; i++) {
    if (i % 2 !== 0) {
        continue;
    }
    console.log(`${i}`);
}
```

Q2. iterate from 0 to 10 and print numbers until reaching 8 (use break)

```js
for (let i = 0; i < 11; i++) {
    if (i > 8) {
        break;
    }
    console.log(`${i}`);
}
```

#### TypeScript 맛보기

```ts
function log(message: string): number {
    console.log(message);
    return 0;
}
```

```js
function log(message) {
    console.log(message);
    return 0;
}
```

TypeScript를 사용하면 개발 속도가 느려질 수는 있겠지만 분명 Code refactoring, Type을 통한 버그 수정이 편해질 것 같다.