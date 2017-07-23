# 5. CSS3 Display

## 5.1 display Property

| Keyword | Description |
| :------ | :---------- |
| block | block 특성을 가지는 요소(block 레벨 요소)로 지정 |
| inline | inline 특성을 가지는 요소(inline 레벨 요소)로 지정 |
| inline-block | inline-block 특성을 가지는 요소(inline-block)로 지정 |
| none | 해당 요소를 화면에 표시하지 않는다(차지하는 공간도 없음). |

> display property는 상속되지 않는다.

### 5.1.1 block level keyword

### **block level keyword의 특징**

* 항상 새로운 라인에서 시작한다(자동개행).
* 화면 크기 전체의 가로폭을 차지한다(width: 100%).
* width, height, margin, padding property 지정이 가능하다.
* block level 요소 내에 inline 레벨 요소를 포함 할 수 있다.
* div, h1 ~ h6, p, ol, ul, li, hr, table, form

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    div:nth-of-type(1) {
      background-color: #FFA07A;
      padding: 20px;
    }
    div:nth-of-type(2) {
      background-color: #FF7F50;
      padding: 20px;
      width: 300px;
    }
  </style>
</head>
<body>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width, height 미지정 → width: 100%; height: auto;</p>
  </div>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width: 300px → width: 300px; height: auto;</p>
  </div>
</body>
</html>
```

### 5.1.2 inline level keyword

### **inline level keyword의 특징**

* 새로운 라인에서 시작하지 않으며 문장의 중간에 들어갈 수 있다.
* content의 너비만큼 가로폭을 차지한다(width: 100%).
* width, height, margin, padding property 지정이 불가능하다.
* 상,하 여백은 line-height로 지정한다.
* inline level 요소 뒤에 공백(엔터, 스페이스)이 있는 경우 정의하지 않은 space(4px)가 자동 지정된다.
* inline level 요소 내에 block level 요소를 포함할 수 없다.
* span, a, strong, img, br, input, select, textarea, button

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    span {
      background-color: red;
      color: white;
      padding: 10px;
      /* 상, 하 여백은 line-height로 지정한다. */
      /* line-height: 50px; */
    }
  </style>
</head>
<body>
  <h1>My <span>Important</span> Heading</h1>
  <span>Inline</span>
  <span>Inline</span><span>Inline</span>
</body>
</html>
```

### 5.1.3 inline-block level keyword

### **inline-block level keyword의 특징**

* inline level 요소와 마찬가지로 줄을 바꾸지 않고 다른 요소들과 한 행에 위치 시킬 수 있다.
* width, height, padding, margin, line-height를 모두 사용할 수 있다.
* inline level 요소 뒤에 공백(엔터, 스페이스)이 있는 경우 정의하지 않은 space(4px)가 자동 지정된다.

### [**Fighting the Space Between Inline Block Elements**](https://css-tricks.com/fighting-the-space-between-inline-block-elements/)

> #### 1. Remove the spaces
> ```html
> <ul>
>  <li>
>   one</li><li>
>   two</li><li>
>   three</li>
> </ul>
> ```
> #### 2. Navigate margin
> ```css
> nav a {
>   display: inline-block;
>   margin-right: -4px;
> }
> ```
> #### 3. Skip the closing tag
> ```html
> <ul>
>   <li>one
>   <li>two
>   <li>three
> </ul>
> ```
> #### 4. Set the font size to zero
> ```css
> nav {
>   font-size: 0;
> }
> nav a {
>   font-size: 16px;
> }

## 5.2 visibility Property

| Keyword | Description |
| :------ | :---------- |
| visible | 해당 요소를 보이게 한다(default). |
| hidden | 해당 요소를 보이지 않게 한다. 요소의 공간은 남아있다. |
| collapse | table 요소에서 사용하며 행이나 열을 보이지 않게 한다. |
| none | FF, IE : table 요소에서 행이나 열을 보이지 않게 한다. CR : hidden |

## 5.3 opacity Property

### 프로퍼티 요소의 투명도를 지정한다. 0.0(투명) >>> 1.0(불투명)