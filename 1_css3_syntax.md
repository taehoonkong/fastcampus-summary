# 1. CSS3 Syntax

## 1.1 Selector

Selector는 스타일을 적용하고자 하는 HTML요소를 선택하기 위해 css에서 제공하는 수단이다.

![](./img/css-syntax.png)

## 1.2 Property

표준스펙으로 지정되어 있는 property를 사용하여 style을 적용할 수 있다.

```css
p {
    color: ...;
    font-size: ...;
    border: ... ... ...;
};
```

## 1.3 Value

프로퍼티의 값을 변경함으로써 style을 변경한다.

```css
p {
    color: tomato;
    font-size: 16px;
    border: 4px solid black;
};
```

## 1.4 HTML과 CSS의 연동

### 1.4.1 Link style

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="css/style.css">
  </head>
</html>
```

### 1.4.2 Embedding style

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      p {
        color: red;
        background: yellow;
      }
    </style>
  </head>
</html>
```

### 1.4.3 Inline style

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 style="color: red;">Hell world</h1>
  </body>
</html>
```

## 1.5 Reset CSS
* [Eric Meyer’s reset](http://meyerweb.com/eric/tools/css/reset/)
* [normalize.css](https://necolas.github.io/normalize.css/)