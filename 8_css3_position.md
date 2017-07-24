# 8. CSS3 Position

## 8.1 position property

### position property는 top, bottom, left, right property와 함께 사용하여 위치를 지정

### 8.1.1 static(기본위치)

* static은 position property의 기본값이다.
* 기본적인 요소의 배치 순서에 따라 위에서 아래로, 왼쪽에서 오른쪽 순서에 따라 배치되며 부모 요소 내에 자식요소로서 존재할 때는 **부모 요소**의 위치를 기준으로 배치된다.
* top, bottom, left, right property를 사용할 수 없다. 사용할 경우에 무시된다.

```css
body {
  margin: 0;
}

.parent {
  width: 150px;
  height: 150px;
  background: #bcbcbc;
  border: 1px solid #bcbcbc;
}

.static-box {
  position: static;
  background: #2E303D;
  color: #e55c3c;
  font-weight: bold;
  text-align: center;
  line-height: 150px;
}
```

```html
<body>
  <div class="parent">
    <div class="static-box">static-box</div>
  </div>
</body>
```

### 8.1.2 relative(상대위치)

* static 위치를 기준으로 좌표 프로퍼티(top, bottom. left, right)를 사용하여 위치를 이동시킨다.

```css
body {
  margin: 0;
}

.parent {
  width: 150px;
  height: 150px;
  background: #bcbcbc;
  border: 1px solid #bcbcbc;
  margin: 50px;
}

.relative-box {
  position: relative;
  top: 50px;
  left: 50px;
  background: #2E303D;
  color: #e55c3c;
  font-weight: bold;
  text-align: center;
  line-height: 150px;
}
```

```html
<body>
  <div class="parent">
    <div class="relative-box">relative-box</div>
  </div>
</body>
```

### 8.1.3 absolute(절대위치)

* 부모요소 또는 부모가 static 이라면 가장 가까이 있는 조상 요소(static 제외)를 기준으로 좌표 프로퍼티(top, bottom, left, right)만큼 이동한다.
* absolute 선언 시, block 레벨 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.
* 기준이 되는 부모에 relative를 걸고 absolute로 움직일것

```css
.parent {
  width: 200px;
  height: 200px;
  background: #bcbcbc;
  border: 1px solid #bcbcbc;
  margin: 50px 0 0 300px;
  position: relative;
}

.absolute-box {
  position: absolute;
  height: 200px; width: 200px;
  top: 50px; left: 50px;
  color: #e55c3c;
  font-weight: bold;
  text-align: center;
  background: #2E303D;
  line-height: 200px;
}
```

```html
<body>
  <div class="parent">
    <div class="absolute-box">absolute box (in parent)</div>
  </div>
  <div class="absolute-box">absolute box (no parent)</div>
</body>
```

### 8.1.4 fixed(고정위치)

* 부모요소와 관계없이 browser의 viewport를 기준으로 좌표 property(top, bottom, left, right)를 이용하여 위치를 이동시킨다.
* 스크롤이 되더라도 사라지지 않고 항상 같은 곳에 위치한다.
* fixed 프로퍼티 선언 시, block 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.

```css
body {
  margin: 0;
}

.fixed-box {
  position: fixed;
  color: #e55c3c;
  font-weight: bold;
  text-align: center;
  background: #2E303D;
}

.sidebar {
  width: 50px;
  height: 100%;
  top: 0;
  right: 0;
  padding-top: 100px;
}

.footer {
  width: 100%;
  height: 50px;
  bottom: 0;
  left: 0;
  line-height: 50px;
}
```

```html
<body>
  <div class="fixed-box sidebar">fixed box(side-bar)</div>
  <div class="fixed-box footer">fixed box(footer)</div>
</body>
```

## 8.2 z-index property

### z-index 프로퍼티에 큰 숫자값을 지정할수록 화면 전면에 출력

```css
.box {
  width: 100px; height: 100px;
  position: absolute;
}
.red {
  background-color: red;
  left: 10px; top: 10px;
  z-index: 100;
}
.green {
  background-color: green;
  left: 50px; top: 50px;
  z-index: 10;
}
.blue {
  background-color: blue;
  left: 90px; top: 90px;
  z-index: 1;
}
```

```html
<body>
  <div class="box red"></div>
  <div class="box green"></div>
  <div class="box blue"></div>
</body>
```

## 8.3 overflow property

### 자식 요소가 부모 요소의 영역을 벗어났을때의 처리방법을 정의

| Property value | Description |
| :------------- | :---------- |
| visible | 영역을 벗어난 부분을 그대로 표시한다. |
| hidden | 영역을 벗어난 부분을 잘라내어 보이지 않게 한다. |
| scroll | 영역을 벗어난 부분과 관계 없이 스크롤을 표시한다. |
| auto | 영역을 벗어난 부분이 있으면 스크롤을 표시한다. |

> #### 특정방향으로만 스크롤을 표시하고 싶을 때
> ```css
> div {
>   overflow-x: auto;
>   overflow-y: auto;
> }