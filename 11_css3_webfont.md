# 11. CSS3 Web Font

## 11.1 Web Font

---

## 11.2 CDN(Content Delivery Network) 링크 방식

### [Google Font](https://fonts.google.com/)

### @import rule의 url 함수는 서버에서 혹은 지정된 url에서 파일을 찾은 후 다운로드

```css
@import url(http://fonts.googleapis.com/earlyaccess/nanumgothic.css);

* {
  font-family: 'Nanum Gothic', sans-serif;
}
```

---

## 11.3 Server Font Loading 방식

### @font-face 규칙으로 폰트를 등록하고 font-family 프로퍼티로 폰트를 선택하여 사용

```css
@font-face {
  font-family: myFontName; /* myFontName 은 임의지정 */
  src: url("myFont.woff"); /* woff는 Font 확장자이며 브라우저마다 지원하는 확장자가 다르다. */
}

* { font-family: myFontName, sans-serif; }
```

### 검증된 웹폰트 사용 방법

```css
@font-face {
  font-family:"Nanum Gothic";
  src:url("NanumGothic.eot"); /* IE 9 호환성 보기 모드 대응 */
  src:local("☺"),             /* local font 사용 방지. 생략 가능 */
      url("NanumGothic.eot?#iefix") format('embedded-opentype'), /* IE 6~8 */
      url("NanumGothic.woff") format('woff'); /* 표준 브라우저 */
}

* { font-family: "Nanum Gothic", sans-serif; }
```

### 영문과 한글을 혼용하는 경우 먼저 영문폰트, 그 다음 한글 폰트를 지정한다.

```css
font-family: 'Lora', 'KoPub Batang', 'Times New Roman', serif;
```