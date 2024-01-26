```javascript
<script setup>
// 자바스크립트 영역
import { ref } from 'vue'
const greeting = ref('Hello World!')
</script>

<template>
<!-- html (뷰 컴포넌트의 표현단, 템플릿 문법) -->
  <p class="greeting">{{ greeting }}</p>
</template>

<style>
/* CSS (뷰 템플릿의 스타일링) */
.greeting {
  color: red;
  font-weight: bold;
}
</style>
```
* Vue 싱글 파일 컴포넌트(Single-File Components: 
* Vue SFC는 HTML, CSS 및 JavaScript 이 3개를 하나로 자연스럽게 합친 것이다.
* <template>
* 화면의 특정 영역에 대한 HTML, CSS, JS 코드를 한 파일에서 관리하는 방법이다.
* SFC의 목적 중 하나는 “관심사항 분리”가 있다.

# 참고자료
* https://ko.vuejs.org/guide/scaling-up/sfc
* https://joshua1988.github.io/vue-camp/vue/sfc.html

