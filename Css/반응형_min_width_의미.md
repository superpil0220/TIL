```css
@media screen and (min-width: 600px) {
  /* 이 스타일은 브라우저 창의 너비가 최소 600px 이상일 때 적용됩니다 */
}
```
* min-width
* 반응형 웹 디자인에서 
* 예를 들어, 

```css
body {
  background-color: blue;
}

@media screen and (min-width: 600px) {
  body {
    background-color: red;
  }
}
```
* 브라우저 창의 크기가 100px인 경우, 
* 브라우저 창의 너비가 600px 미만이면, 
* 브라우저 창의 너비가 600px 이상 조건이니깐 브라우저 크기가 700px, 800px 또는 그 이상이라도 body의 배경 빨간색으로 적용됨

# 참고자료
* https://apost.dev/823/
