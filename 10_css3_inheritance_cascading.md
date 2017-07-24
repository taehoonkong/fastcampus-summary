# 10. CSS3 Inheritance & Cascading

## 10.1 상속(Inheritance)

> * 상속이란 상위요소의 속성을 하위요소가 물려 받는 것을 의미한다.
> * 모든 프로퍼티가 상속되지는 않는다.

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <style>
    .text-red {
      color: red; /* h1, p에 상속 */
      border: 1px solid #bcbcbc; /* 상속 안됨 */
      padding: 10px; /* 상속 안됨 */
    }
    .text-red button {
      color: inherit; /* inherit 키워드를 통하여 명시적으로 상속 */
    }
    .text-red p {
      border: inherit;
      padding: inherit;
    }
  </style>
</head>
<body>
  <div class="text-red">
    <h1>Heading</h1>
    <p>Paragraph<strong>strong</strong></p>
    <button>Button</button>
  </div>
</body>
</html>
```

## 10.2 Cascading

* 요소는 하나 이상의 CSS선언에 영향을 받을 수 있다. 이때 충돌을 피하기 위하여 우선순위가 필요한데 이를 **Cascading Order**라고 한다.
  * 중요도: CSS가 어디에 선언 되었는가?
  * 명시도: 대상을 명확하게 특정할 수록 우선순위가 높아진다.
  * 선언순서: 나중에 선언된 스타일이 우선 적용된다.

### 10.2.1 중요도

우선순위

1. head 요소 내의 style 요소
1. head 요소 내의 style 요소내의 @import문
1. \<link>로 연결된 CSS 파일
1. \<link>로 연결된 CSS 파일 내의 @import문
1. Browser Default Stylesheet

### 10.2.2 명시도

우선순위

> !important > 인라인 스타일 > 아이디 선택자 > 클래스/속성/가상 선택자 > 태그 선택자 > 전체 선택자 > 상위 요소에 의해 상속된 속성

### 10.2.3 선언순서

```css
p { color: blue; }

/* 우선적용 */
p { color: red; }

.red { color: red; }

/* 우선적용 */
.blue { color: blue; }
```