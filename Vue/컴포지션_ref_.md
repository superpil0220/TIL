* 반응형이란, 데이터가 변경되었을 때 이를 감지하고 이에 반응하여 DOM이 자동으로 업데이트 된다.

```javascript
<script>
import { ref } from 'vue';

export default {
  // `setup`은 Composition API 전용 특수 후크입니다.
  setup() {
    const count = ref(0);

    // ref를 템플릿에 노출
    return {
      count
    };
  }
};
</script>

<template>
  <div>
    {{ count }}
  </div>
</template>
```
* ref를 import해서 count에 ref(0)을 할당한다. count에 값0이 할당된다.
* ref()가 composition api 전용 특수 후크이다.
* 템플릿에 count를 노출시키기 위해 setup()에서 count를 return 해준다. 화면에 0이 출력된다.
* 이후, 스크립트에서 count값을 변경하면 바로 템플릿에 적용된다.

```javascript
<script>
import { ref } from 'vue';
export default {
  // `setup`은 Composition API 전용 특수 후크입니다.
  setup() {
    const count = ref(0);

    const up = () => {
			// JavaScript 에서 .value 는 필요합니다.
      count.value++;
    };

    // ref를 템플릿에 노출
		// 함수를 노출하는 것도 잊지 마세요.
    return {
      count,
      up
    };
  }
};
</script>

<template>
  <div>
    {{ count }}

    <button @click="up">+</button>
  </div>
</template>
```
* count와 같이 up함수를 setup에서 선언하고 return해준다.
* up함수는 실행될때마다 count값을 1씩 증가시킨다.
* count가 1씩 증가될때마다 화면에서 값이 변경되어 출력된다.

#  
```javascript
<script setup>
import { ref } from 'vue';

const count = ref(0);

const up = () => {
  count.value++;
};
</script>

<template>
  <div>
    {{ count }}

    <button @click="up">+</button>
  </div>
</template>
```
* setup()
* <script setup>을 사용하면 위 코드처럼 간결하게 작성할 수 있다.

# 참고자료
* https://ko.vuejs.org/guide/essentials/reactivity-fundamentals.html

