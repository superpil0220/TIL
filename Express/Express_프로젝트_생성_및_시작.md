```shell
mkdir demo
cd demo
```
* demo 디렉토리를 만들고 demo 디렉토리로 이동한다.
* 앞으로 프로젝트의 코드가 담길 디렉토리다.

```shell
npm init
```
* 위 명령어로 package.json 파일을 생성한다.
* 명령어를 실행하면 애플리케이션의 이름 및 버전과 같은 몇 가지 정보에 대한 설정을한다.


```shell
npm install express
```
* express 패키지 설치

```javascript
const express = require('express');
const app = express();

app.get("/", (req, res) => {
  res.send("Hello Superpil!");
})

app.listen(8080, () => {
  console.log("Server Start!!");
})
```
* 최상위 디렉토리 하위에 main.js파일을 생성하고 위 코드를 넣자.
* 8080포트로 서버를 열고 / 로 접속하면 문자열을 응답한다.

```json
"scripts": {
	"test": "echo \"Error: no test specified\" && exit 1",
	"start": "node main.js"
},
```
* "start": "node main.js"를 작성하고 터미널에서 “npm start” 명령어를 입력하면 실행된다.

# 참고자료
* https://expressjs.com/ko/starter/installing.html
