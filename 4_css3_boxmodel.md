# 4. CSS3 Box Model

> 모든 HTML 요소는 Box 형태의 영역을 가지고 있다.
>
> ![](img/box-model.png)
> * **Content** : 요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역이다. width, height 프로퍼티를 갖는다.
> * **Padding** : 테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역이다. padding 프로퍼티 값은 패딩 영역의 두께를 의미하며 기본색은 투명(transparent)이다. 요소에 적용된 배경의 컬러, 이미지는 패딩 영역까지 적용된다.
> * **Border** : 테두리 영역으로 border 프로퍼티 값은 테두리의 두께를 의미한다.
> * **Margin** : 테두리(Border) 바깥에 위치하는 요소의 외부 여백 영역이다. margin 프로퍼티 값은 마진 영역의 두께를 의미한다. 기본적으로 투명(transparent)하며 배경색을 지정할 수 없다.

---

## 4.1 Width / Height Property

> ### **box-sizing**
>
> * Default : content-box
>
>   * 요소의 너비와 높이는 content 영역을 대상으로 한다.
>
> * Option : border-box
>
>   * content + padding + border가 포함된 영역을 Width / Height 프로퍼티의 대상으로 지정 가능하다.
>
> ### **Width**
> * Default
>   * auto(부모 요소의 100%)
> * Option
>   * 명시적으로 지정(px, em, % 등 크기단위 사용)
> ### **max-width & min-width**
> * max-width : 요소 너비의 최대값 지정
> * min-width : 요소 너비의 최소값 지정
> ### **Height**
> * Default
>   * auto(content의 높이 + 여분)
> * Option
>   * 명시적으로 지정(px, em, % 등 크기단위 사용)
> ### **Overflow**
> * width와 height를 명시적으로 지정하였을 때 content가 지정한 content영역의 크기를 넘어가면 넘치게 된다.
> * 해결방법 : overflow: hidden; 을 지정하면 넘친 content를 숨긴다.
> ### **상속**
> * Box Model 관련 프로퍼티는 상속되지 않는다.
> * width, height, padding, border, margin, box-sizing 등

```css
div {
  box-sizing: border-box; /* option */
  width: 300px;
  height: 80%;
  overflow: hidden;
}
```

---

## 4.2 Padding / Margin Property

### 4.2.1 padding / margin 프로퍼티는 네 방향으로 설정

> ```css
> /* 시계방향 순서대로 설정하면 된다. */
>
> div {
>   margin-top: ...px;
>   margin-right: ...px;
>   margin-bottom: ...px;
>   margin-left: ...px;
>
>   padding-top: ...px;
>   padding-right: ...px;
>   padding-bottom: ...px;
>   padding-left: ...px;
> }
> ```

### 4.2.2 간편법

> ```css
> div {
>   /* 4개의 값 지정 */
>   /* top right bottom left */
>   margin: 25px 50px 75px 100px;
>   padding: 25px 50px 75px 100px;
>
>   /* 3개의 값 지정 */
>   /* top right/left bottom */
>   margin: 25px 50px 75px;
>   padding: 25px 50px 75px;
>
>   /* 2개의 값 지정 */
>   /* top/bottom right/left */
>   margin: 20px 50px;
>   padding: 20px 50px;
>
>   /* 1개의 값 지정 */
>   /* top/right/bottom/left */
>   margin: 30px;
>   padding: 30px;
> }
>```

---

## 4.3 Border Property

### 4.3.1 border-style

```css
p.dotted { border-style: dotted; }
p.dashed { border-style: dashed; }
p.solid  { border-style: solid; }
p.double { border-style: double; }
p.groove { border-style: groove; }
p.ridge  { border-style: ridge; }
p.inset  { border-style: inset; }
p.outset { border-style: outset; }
p.none   { border-style: none; }
p.hidden { border-style: hidden; }
p.mix    { border-style: dotted dashed solid double; }

  /* border-style: top right bottom left; 각 방향에 다른 스타일 지정이 가능함 */
```

### 4.3.2 border-width

```css
p.one { border-width: thin; /* 1px */ }
p.two { border-width: medium; /* 3px */ }
p.three { border-width: thick; /* 5px */  }
p.four { border-width: 15px; }

/* 네 방향 동시 설정 */
p.five { border-width: 2px 10px 4px 20px; }
```

### 4.3.3 border-color

```css
p.one { border-color: red; }

/* 네 방향 동시 설정 */
p.two { border-color: red green blue yellow; }
```

### 4.3.4 border-radius

```css
.border-rounded {
  border-radius: 10px 40px 40px 10px;

  /* 위 코드는 아래의 shorthand이다.
  border-top-left-radius:     10px;
  border-top-right-radius:    40px;
  border-bottom-right-radius: 40px;
  border-bottom-left-radius:  10px;

  좌상단부터 시계방향 순으로 설정한다.
  */
}
```