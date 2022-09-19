### TL;DR

#### CSR(Client Side Rendering)

1. 유저가 웹사이트에 요청을 보낸다.
2. 서버에서 JavaScript 링크가 들어있는 HTML 파일을 받아와서 다운로드 받는다. (_**Not Viewable** & **Not Interactive**_)
3. 링크 되어 있는 JavaScript 파일을 다운로드 받는다. (_**Not Viewable** & **Not Interactive**_)
4. 브라우저가 프레임 워크를 실행하고 페이지 렌더링을 완료한다. (_**Viewable** & **Interactive**_)

#### SSR(Server Side Rendering)

1. 유저가 웹사이트에 요청을 보낸다.
2. 서버가 즉시 렌더링 가능한 HTML 파일을 만들어서 클라이언트에 보낸다.
3. 클라이언트가 서버로부터 받은 HTML 파일을 렌더링한다. (_**Viewable** & **Not Interactive**_)
4. 브라우저가 JavaScript 파일을 다운로드 받는다. (_**Viewable** & **Not Interactive**_)
5. 브라우저가 프레임 워크를 실행한다. (_**Interactive**_)

---

### Detail

아래 코드는 CSR의 대표적인 예시 코드이다.
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <meta name="description"
              content="Amazing web site" />
        <title>App</title>
    </head>
    <body>
        <div id="root"></div>
        <script src="app.js"></script>
    </body>
</html>
```
**CSR**은 브라우저가 동작하기 위한 파일이 모두 준비되어야만 화면에 보여진다.
CSR에서 받아오는 HTML 파일은 `body` 태그 안에 JavaScript 파일 링크만 들어 있어서 처음에는 빈 화면이 보이게 된다.
HTML 파일에 있는 JavaScript 파일을 다운로드 받는다. JavaScript 파일에는 우리 어플리케이션에 필요한 로직들 뿐만 아니라 어플리케이션을 구동하는 프레임
워크와 라이브러리(ex. React, Vue, Angular)의 소스코드들도 다 포함이 되어 있기 때문에 사이즈가 굉장히 커서 다운로드 받는데 시간이 소요된다.
추가로 필요한 데이터가 있을 경우 서버로 요청해서 JSON 데이터를 받아온 다음 JavaScript 파일과 함께 동적으로 HTML을 생성해서 사용자에게 화면을 보여준다.

#### CSR의 장점
- 최초 요청에 JavaScript 파일을 다운로드 받고, 이후에는 화면에서 변화가 일어나야 하는 만큼의 데이터만 요청하기에 **후속 페이지 로드 시간이 빠르다**.
- 서버를 호출할 때 마다 전체 UI를 다시 로드할 필요가 없다.

#### CSR의 단점
- 최초 페이지 로드 시간이 SSR에 비해 느리다.
- SEO(Search Engine Optimization)는 HTML 파일을 기반으로 분석하기 때문에 비어있는 HTML을 내려주는 CSR을 사용하면 불리하다.

---

**SSR**은 서버로부터 즉시 렌더링 가능한 HTML 파일을 만들어서 클라이언트에 넘기고, 클라이언트가 HTML 파일을 받아 렌더링한다. 
하지만 JavaScript 파일이 로드되지 않아 상호작용은 불가능하다. 브라우저가 JavaScript 파일을 다운로드한다. 파일이 받아지는 동안 유저는 컨텐츠를 볼 수는 있지만 상호작용은 할 수 없다. 그래도 다운 받는 동안 일어난 상호작용는 모두 기록해놓는다. 파일 로드가 완료되면 FrameWork를 실행하고 기록되었던 상호작용이 가능해진다.

#### SSR의 장점
- 초기 로딩이 빠르다.
- CSR 처럼 비어있는 HTML 파일을 받아오는 것이 아니기 때문에 SEO에 유리하다.

#### SSR의 단점
- 새로운 요청이 생길때마다 바뀌지 않아도 되는 부분도 렌더링된다.
- TTV(Time To View)와 TTI(Time To Interact) 간의 공백이 길다.