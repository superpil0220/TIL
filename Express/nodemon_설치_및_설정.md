```shell
npm install nodemon
```
* 파일 수정시 서버를 내리고 다시 올려야 수정된 내용이 반영된다. 너무 귀찮다.
* nodemon을 사용해서 수정 시 서버 재기동없이 반영해보자.
* 위 명령어로 설치한다.

```javascript
"scripts": {
  "start": "nodemon main.js"
},
```
* package.json 파일에서 서버 실행 명령어를 수정하자.

# 참고자료
* https://velog.io/@nomadhash/Node.JS-Express와-Nodemon
