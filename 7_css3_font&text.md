# 7. CSS3 Font & Text

## 7.1 font-size property

### Text의 크기를 지정

```css
.font-size-40 { font-size: 40px; }
.font-size-2x { font-size: 2.0em; }
.font-size-150ps { font-size: 150%; }
.font-size-large { font-size: large; }
```

## 7.2 font-family property

### Font를 지정

> font는 여러개 지정이 가능하며 클라이언트의 컴퓨터가 해당 폰트를 가지고 있지 않은 경우에 후순위의 폰트를 사용하게 된다.

```css
.serif {
  font-family: "Times New Roman", Times, serif;
}

.sans-serif {
  font-family: Arial, Helvetica, sans-serif;
}

.monospace {
  font-family: "Courier New", Courier, monospace;
}
```

## 7.3 font-style, font-weight property

### font-style: 이탤릭체 지정, font-weight: 굵기 지정

```css
.italic {
  font-style: italic;
}
.light {
  font-weight: bold;
}
```

## 7.4 line-height property

### Text의 높이를 지정, 텍스트 수직 정렬

```css
.small {
  line-height: 70%; /* 16px * 70% */
}

.big {
  line-height: 1.2; /* 16px * 1.2 */
}
```

> ### **텍스트 수직정렬**
> a 요소의 line-height와 a 를 감싸고 있는 button 요소의 height 값을 일치시킨다.
> ```css
> .button {
>   height: 70px;
> }
>
> .button > a {
>   line-height: 70px;
> }

## 7.5 letter-spacing property

### 글자 사이의 간격을 지정

```css
.loose {
  letter-spacing: 2px;
}
```

## 7.6 text-align property

### text의 수평정렬을 지정

```css
h1 { text-align: center; }
h3 { text-align: right; }
p.left  { text-align: left; }
p.justify  { text-align: justify; }
/* a 태그의 경우 inline요소이기 때문에 text-align을 적용하려면 display를 block으로 지정하여야 한다. */
a  { text-align: center; }
```

## 7.7 text-decoration property

### text를 꾸며줌

```css
/* link underline 제거 */
a { text-decoration: none; }
/* 윗줄 */
p:nth-of-type(1) { text-decoration: overline; }
/* 취소선 */
p:nth-of-type(2) { text-decoration: line-through; }
/* 밑줄 */
p:nth-of-type(3) { text-decoration: underline; }
```