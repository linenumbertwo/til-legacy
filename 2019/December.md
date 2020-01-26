## 12.01
- Function()과 친해지는 시간을 보냈습니다.
- 프로그래머스 문제를 풀어보았는데 알고리즘식으로 돼있어서 푸는데 즐거움(?)이 있었습니다.

## 12.02
- 산업기능요원에 대한 정보를 찾아봤습니다. (제가 해야하기 때문에)
  - (내가)할 수 있는 방법 
    - 1순위. 자신-학교-기업과 3자협약을 맺는 것
    - 2순위. 특성화고졸업(예정)자

## 12.03
- Greeny코드를 완벽히 이해하며, Webhook으로 단방향 메세지를 보냈었지만 Botkit으로 바꾸려고 공부중입니다.

## 12.04
- node.js에서 크롤링 하는 것을 공부 중입니다.

## 12.05
- 크롤링과 botkit을 이용하여 슬랙 봇을 만드는 중

## 12.06
- Reviewed synchronous and asynchronous in JavaScript


  - Synchronous: Execute(Run) sequentially from top to bottom 
  ```
  console.log("1st");
  console.log("2nd");
  console.log("3rd");
  
  OUTPUT 
  > 1st, 2nd, 3rd
  ```
  - Asynchronous: If complete for synchronous code, return by value
  ```
  console.log("1st");
  
  setTimeout(()=>{
  console.log("2nd");
  }, 0)
  // 지연시간을 0초로 설정  
  
  console.log("3rd");
  
  OUPUT
  > 1st, 3rd, 2nd
  ```
  
## 12.07
- Watched "생활코딩" from youtube and studied English

## 12.08
- Studied the concept of callback and closure in "생활코딩"
- Studied [here](https://www.codingfactory.net/10401), local and global variable
- Studied [here](https://emflant.tistory.com/66), inner and outer function

## 12.09
- JavaScript console method
```
console.debug('log와 동일한 로그 메시지를 출력합니다.');
console.error('에러 메시지를 출력합니다.');
console.info('정보성 메시지를 출력합니다.');
console.warn('경고성 메시지를 출력합니다.');
```
- Difference between break and continue
```
for (i = 0; i < 10; i++){
    if (i==3)
    continue;
    if (i==5)
    break;
    console.log(i)
}
OUPUT >> 0, 1, 2, 4
```
## 12.10
- Watched channel "생활코딩"
- Get to know url basic port value is 80
- Node.js CRUD
  - Create, Read, Update, Delete

## 12.11
- Read "JavaScript 200" and solved problems
- Vscode command: alt+cmd+up/down, alt+shift+I, shift+alt+up/down
- Memorized English terms
- Watched nodejs on youtube channel "생활코딩"
- Get to know the nodejs package pm2
- pm2 console method
```
npm install pm2 -g // 설치
pm2 start <name> // 서버 열기
pm2 monit // 모니터 열기
pm2 list // pm2로 실행중인 서버 리스트 열기
pm2 start <name> --watch // 서버 실행 중 코드 수정을 해도 재시동 없이 적용됨
pm2 stop <name> // 서버 종료
```

## 12.12
- Watched all nodejs videos on "생활코딩"
- Studied and Memorized English terms and English writing
- Write few TILs in English

## 12.16
- Watched MySQL on "생활코딩"
- Tried Errors in MySQL
- Errors and solutions
  - `ERROR 2002 (HY000): Can’t connect to local MySQL server through socket ‘/tmp/mysql.sock’ (2)`
    - Deleted and reinstalled MySQL
  - `ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)`
    - Reset password in MySQL

## 12.17
- Watched all MySQL videos on "생활코딩"
  - Learned useful MySQL knowledge
    - Change database command `use dbname`
- [Node.js](https://github.com/indante/Node.js) uploading on github repository

## 12.18
- Refactoring [Node.js-MySQL](https://github.com/indante/Node.js-MySQL) code and uploading on github repository

## 12.19
- Watched Node.js-express on "생활코딩"
- Searched and learned jQuery code examples.
  - [This site](https://www.w3schools.com/jquery/default.asp) good for learning jQuery

## 12.20
- Tried various functions of jQuery
  - jQuery's animate method was funny and amazing
  
## 12.24
- Watched all Node.js-express videos on "생활코딩"
  - Security best practices for Express applications in production include
    - Don’t use deprecated or vulnerable versions of Express    // 최신버전 사용하기
    - Use TLS   // https 사용하기
    - Use Helmet    // 보안이슈들을 자동으로 해결
    `npm install --save helmet`
    ```
    var helmet = require('helmet');
    app.use(helmet());
    ```
    - Use cookies securely    // 쿠키를 안전하게 사용해라
    - Ensure your dependencies are secure   // 종속성 검사(?)
    `npm i nsp -g`, `nsp check`

## 12.25
- [Node.js-Express](https://github.com/indante/Node.js-Express) uploading on github repository
- Starting React from "생활코딩"

## 12.27
- Watched React on "생활코딩"
