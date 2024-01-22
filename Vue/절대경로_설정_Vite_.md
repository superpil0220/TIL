# 개념
* 상대경로 : ../../assets/img/vue.png
* 절대경로 : @/assets/img/vue.png
* 상대경로는 현재 디렉토리에서 불러오고싶은 파일의 경로를 찾아가야한다.
* 절대경로는 현재 디렉토리와 상관없이 절대경로의 시작점으로 설정한 디렉토리를 시작점으로 잡고 불러오고싶은 파일을 찾는다.
* 상대경로보다 절대경로가 개발할때 파일을 찾을 수 없는 이슈를 방지할 수 있다.

# Vite에서 절대경로 설정
```javascript
import { fileURLToPath, URL } from 'node:url';

import { defineConfig } from 'vite';
import vue from '@vitejs/plugin-vue';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    }
  }
});
```
* 최상위 디렉토리 하위에 vite.config.js 파일을 생성 후 위 코드 중에서 
* 만약, vue cli로 프로젝트를 생성했다면 자동으로 설정되었을거다.

# 참고자료
* https://l4279625.tistory.com/110#vite.config.js-1
