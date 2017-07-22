# 2. CSS3 Selector

Style을 적용하고자 하는 요소들을 특정하기 위한 목적으로 사용된다.

## 2.1 Universal Selector

| Pattern | Description |
| :-----: | :-----------|
| * |  HTML 문서 내의 모든 요소 선택 |

```css
* {
  color: red;
  font-size: 15px;
  border: 4px solid orange;
}
```

---

## 2.2 Type Selector

| Pattern | Description |
| :------ | :-----------|
| div, h1, p ... | 지정된 태그명을 가진 요소 선택 |

```css
/* p 태그 선택 */
p {
  color: orange;
  border: 1px double red;
}

/* h1 태그 선택 */
h1 {
  color: brown;
  font-size: 30px;
}
```

---

## 2.3 ID Selector

| Pattern | Description |
| :------ | :-----------|
| #some_id | id 어트리뷰트 값을 지정하여 일치하는 요소 선택(id는 unique한 값이다.) |

```css
/* id = some_id */
#some_id {
  background-color: yellowgreen;
  padding: 10px 20px;
}
```

---

## 2.4 Class Selector

| Pattern | Description |
| :------ | :-----------|
| .some_class | class 어트리뷰트 값을 지정하여 일치하는 요소 선택(class는 중복가능하다.) |

```css
.some_class {
  background-color: blue;
  margin: 10px 20px;
}

.some_class_2 {
  color: orange;
  padding: 10px 20px;
}
```

> class attribute 값은 공백으로 구분하여 여러개를 지정 할 수 있다.

```html
<body>
  <h1 class="some_class some_class_2">Hell World</h1>
</body>
```

---

## 2.5 Attribute Selector

### 2.5.1 Select All

| Pattern | Description |
| :------ | :-----------|
| a[href] | 지정된 어트리뷰트를 갖는 모든 요소 선택 |

```css
a[href] {
  color: tomato;
}
```

### 2.5.2 Select by Value

> #### 2.5.2.1 Equal

| Pattern | Description |
| :------ | :-----------|
| a[target="_blank"] | 지정된 어트리뷰트를 가지면서 동시에 어트리뷰트 값도 일치하는 모든 요소를 선택 |

```css
a[target="_blank"] {
  color: orange;
}
```

> #### 2.5.2.2 Split by Space

| Pattern | Description |
| :------ | :-----------|
| h1[title~="first"] | 지정된 어트리뷰트를 가지면서 동시에 공백으로 분리된 어트리뷰트 값을 포함하는 모든 요소를 선택 |

```html
<html>
<head>
  <style>
    h1[title~="first"] {
      color: yellow;
      font-size: 40px;
    }
  </style>
</head>
<body>
  <h1 title="head first">Head</h1>
</body>
</html>
```

> #### 2.5.2.3 Start with Hyphen

| Pattern | Description |
| :------ | :-----------|
| p[lang\|="en"] | 지정된 어트리뷰트의 값과 일치하거나 지정 어트리뷰트 값 뒤 연이은 하이픈으로 시작하는 요소를 선택 |

```html
<html>
<head>
  <style>
    p[lang|="en"] {
      color: blue;
    }
  </style>
</head>
<body>
  <p lang="en">en!</p>
  <p lang="en-us">en-us!</p>
</body>
</html>
```

> #### 2.5.2.4 Start with Value &
> #### 2.5.2.5 End with Value

| Pattern | Description |
| :------ | :-----------|
| a[href^="https://"] | 지정된 어트리뷰트의 값으로 시작하는 요소를 선택|
| a[href$=".com"] | 지정된 어트리뷰트의 값으로 끝나는 요소를 선택|

```html
<html>
<head>
  <style>
    a[href^="https://"] {
      color: yellow;
      font-style: italic;
    }

    a[href$=".com"] {
      color: orange;
    }
  </style>
</head>
<body>
  <a href="https://www.google.com">Google</a>
  <a href="http://www.naver.com">Naver</a>
</body>
</html>
```

> #### 2.5.2.6 Include Value

| Pattern | Description |
| :------ | :-----------|
| div[class*="test"] | 지정된 어트리뷰트 값을 포함하는 요소를 선택|

```html
<html>
<head>
  <style>
    div[class*="test"] {
      font-size: 30px;
      margin: 30px 40px;
    }
  </style>
</head>
<body>
  <div class="first_test">The first div element.</div>
</body>
</html>
```

---

## 2.6 Combinator

![](./img/descendant-child.png)

### 2.6.1 Descendant Combinator

| Pattern | Description |
| :------: | :----------- |
| SelectorA SelectorB|
| div p | SelectorA(div)의 모든 후손 요소 중 SelectorB(p)와 일치하는 요소를 선택 |

```html
<html>
<head>
  <style>
    div p {
      color: orange;
    }
  </style>
</head>
<body>
  <div>
    <h1>This is h1</h1>
    <!-- color: orange -->
    <p>This is p</p>
  </div>
</body>
</html>
```

### 2.6.2 Child Combinator

| Pattern | Description |
| :------: | :----------- |
| SelectorA > SelectorB|
| div > p | SelectorA(div)의 자식 요소 중 SelectorB(p)와 일치하는 요소를 선택 |

```html
<html>
<head>
  <style>
    div > p {
      color: orange;
    }
  </style>
</head>
<body>
  <div>
    <h1>This is h1</h1>
    <!-- color: orange -->
    <p>This is p</p>
    <!-- only child -->
    <span>
      <p>This is another p</p>
      <p>This is another p</p>
    </span>
  </div>
</body>
</html>
```

### 2.6.3 Sibling Combinator

> #### 2.6.3.1 Adjacent Sibling Combinator

| Pattern | Description |
| :------: | :----------- |
| SelectorA + SelectorB|
| div + p | SelectorA(div)의 형제 요소 중 바로 뒤에 위치하는 SelectorB(p) 요소를 선택 |

```html
<html>
<head>
  <style>
    /* p 요소의 형제 요소 중에 p 요소 바로 뒤에 위치하는 ul 요소를 선택한다. */
    p + ul { color: red; }
  </style>
</head>
<body>
  <div>A div element.</div>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <p>The first paragraph.</p>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <h2>Another list</h2>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>
</body>
</html>
```

> #### 2.6.3.2 General Sibling Combinator

| Pattern | Description |
| :------: | :----------- |
| SelectorA ~ SelectorB|
| div ~ p | SelectorA(div)의 형제 요소 중 뒤에 위치하는 모든 SelectorB(p) 요소를 선택 |

```html
<html>
<head>
  <style>
    /* p 요소의 형제 요소 중에 p 요소 뒤에 위치하는 ul 요소를 모두 선택한다.*/
    p ~ ul { color: red; }
  </style>
</head>
<body>
  <div>A div element.</div>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <p>The first paragraph.</p>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <h2>Another list</h2>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>
</body>
</html>
```

---

## 2.7 Pseudo-Class Selector

```css
selector:pseudo-class {
  property: value;
}
```

| Pattern | Description |
| :------: | :----------- |
| a:hover | Selector(a)가 특정 상태(hover)일때의 style 선택 |

```html
<html>
<head>
  <style>
    /* a 요소가 hover 상태일 때 */
    a:hover { color: red; }
  </style>
</head>
<body>
  <a href="#">Hover me</a>
</body>
</html>
```

### 2.7.1 Link pseudo-classes, User action pseudo-classes

| pseudo-class | Description |
| :----------- | :---------- |
| :link | 방문하지 않은 링크 |
| :visited | 방문한 링크 |
| :hover | 마우스 올라와 있을 때 |
| :active | 클릭상태 |
| :focus | 포커스 들어와 있을 때 |

```css
/* a 요소가 방문하지 않은 링크일 때 */
a:link { color: orange; }

/* a 요소가 방문한 링크일 때 */
a:visited { color: green; }

/* a 요소에 마우스가 올라와 있을 때 */
a:hover { font-weight: bold; }

/* a 요소가 클릭된 상태일 때 */
a:active { color: blue; }

/* text input 요소와 password input 요소에 포커스가 들어와 있을 때 */
input[type=text]:focus,
input[type=password]:focus {
  color: red;
}
```

### 2.7.2 UI element states pseudo-classes

| pseudo-class | Description |
| :----------- | :---------- |
| :checked | 체크상태 |
| :enabled | 사용가능 |
| :disabled | 사용불가 |

### 2.7.3 Structural pseudo-classes

| pseudo-class | Description |
| :----------- | :---------- |
| :first-child | 셀렉터에 해당하는 모든 요소 중 첫번째 자식 요소 선택 |
| :last-child | 셀렉터에 해당하는 모든 요소 중 마지막 자식 요소 선택 |
|||
| :nth-child(n) | 셀렉터에 해당하는 모든 요소 중 앞에서 n번째 자식인 요소 선택 |
| :nth-last-child(n) | 셀렉터에 해당하는 모든 요소 중 뒤에서 n번째 자식인 요소 선택 |
|||
| :first-of-type | 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 첫번째 등장하는 요소를 선택 |
| :last-of-type | 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 마지막에 등장하는 요소를 선택 |
|||
| :nth-of-type(n) | 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 앞에서 n번째에 등장하는 요소를 선택 |
| :nth-last-of-type(n) | 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 뒤에서 n번째에 등장하는 요소를 선택. |
|||
| :not(selector) | 셀렉터에 해당하지 않는 모든 요소 선택 |

---

## 2.8 Pseudo-Element Selector

```css
selector::pseudo-element {
  property:value;
}
```

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소 콘텐츠의 첫글자를 선택 */
    p::first-letter { font-size: 3em; }
    /* p 요소 콘텐츠의 첫줄을 선택 */
    p::first-line   { color: red; }

    /* h1 요소 콘텐츠의 앞 공간에 content 어트리뷰트 값을 삽입한다 */
    h1::before {
      content: " HTML!!! ";
      color: blue;
    }
    /* h1 요소 콘텐츠의 뒷 공간에 content 어트리뷰트 값을 삽입한다 */
    h1::after {
      content: " CSS3!!!";
      color: red;
    }

    /* 드래그한 콘텐츠를 선택한다 */
    ::selection {
      color: red;
      background: yellow;
    }
  </style>
</head>
<body>
  <h1>This is a heading</h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Explicabo illum sunt distinctio sed, tempore, repellat rerum et ea laborum voluptatum! Quisquam error fugiat debitis maiores officiis, tenetur ullam amet in!</p>
</body>
</html>
```