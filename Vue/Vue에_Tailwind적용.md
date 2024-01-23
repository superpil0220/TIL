# 설치 및 설정
## 설치
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
* 위 명령어로 tailwinds를 설치한다.

## 설정
```javascript
// tailwind.config.js

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
* 프로젝트 최상위 디렉토리 하위에 tailwind.config.js 파일을 생성 후 위 코드를 넣는다.
* 나중에 해당 파일에서 tailwind의 설정을 커스텀 할 수 있다.

```css
/* style.css */

@tailwind base;
@tailwind components;
@tailwind utilities;
```
* 원하는 css 파일에 위 코드 넣기
* 여기까지 완료하면 tailwind가 적용된다.

# 참고자료
* https://tailwindcss.com/docs/guides/vite#vue

