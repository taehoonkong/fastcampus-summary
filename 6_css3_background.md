# 6. CSS3 Background

## 6.1 background-image property

### 요소에 배경 이미지를 지정

```css
body {
  background-image: url("http://taehoon.com/img/some_img.png");
}
```

## 6.2 background-repeat property

### 배경 이미지의 반복을 지정

```css
body {
  background-image: url("http://taehoon.com/img/some_img1.png"), url("http://taehoon.com/img/some_img2.png");
  /* 가로, 세로 모두 반복 */
  background-repeat: repeat;
  /* 가로 반복 */
  background-repeat: repeat-x;
  /* 세로 반복 */
  background-repeat: repeat-y;
  /* 반복 안함 */
  background-repeat: no-repeat;
  /* 두 개의 이미지 적용 시에 */
  background-repeat: repeat, repeat-x; /* 첫번째: 반복, 두번째: 가로반복 */
}
```

## 6.3 background-size property

### 배경 이미지의 크기를 지정

### 6.3.1 px값 지정

```css
.bg {
  /* 첫 번째 값은 width, 두 번째 값은 height */
  background-size: 700px 500px;
}
```

### 6.3.2 %값 지정

```css
.bg {
  /* 첫 번째 값은 width, 두 번째 값은 height */
  background-size: 100% 100%;
}
```

### 6.3.3 cover 지정

```css
.bg {
  /* 배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 width, height 중 큰값에 배경이미지를 맞춘다 */
  background-size: cover;
}
```

### 6.3.4 contain 지정

```css
.bg {
  /* 배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 영역에 배경이미지가 보이지 않는 부분없이 전체가 들어갈 수 있도록 이미지 스케일을 조정한다. */
  background-size: contain;
}
```

## 6.4 background-attachment property

### 화면이 스크롤 되더라도 배경화면을 고정시키고 싶을때 fixed 키워드 지정

```css
.parallax {
      background-image: url("http://taehoon.com/img/some_img.png");
      /* parallax scrolling effect */
      background-attachment: fixed;
    }
```

## 6.5 background-position property

### background-image의 위치를 지정

```css
.bg {
  /* 중앙 상단 */
  background-position: top;
  /* 중앙 하단 */
  background-position: bottom;
  /* 정중앙 */
  background-position: center;
  /* 중앙 좌측 */
  background-position: left;
  /* 중앙 우측 */
  background-position: right;
  /* 상단 중앙 */
  background-position: top;
  /* % */
  background-position: 20% 75%;
  /* px */
  background-position: 30px 20px;
}
```

## 6.6 background-color property

### background-color를 지정

```css
.bg {
  background-color: tomato;
}
```