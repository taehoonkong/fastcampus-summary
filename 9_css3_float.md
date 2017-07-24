# 9. CSS3 Float

> * float 프로퍼티는 주로 layout을 구성하기 위해 사용되는 핵심 기술이다. layout의 가장 큰 목적은 1개 이상의 요소를 원하는 위치에 정렬시키는 것이다.
> * float 프로퍼티를 사용할 때 요소의 위치를 고정시키는 absolute를 사용하면 안된다.

## 9.1 요소 정렬

### float 프로퍼티를 사용하지 않은 block요소들은 수직으로 정렬됨

> **정렬순서**
> * float-right: 상위 요소가 오른쪽부터 쌓임
> * float-left: 상위요소가 왼쪽부터 쌓임

```css
.d1 {
  /*float: left;*/
  float: right;
  background: red;
}
.d2 {
  /*float: left;*/
  float: right;
  background: orange;
}
```

```html
<body>
  <div class="d1"> 1 </div>
  <div class="d2"> 2 </div>
</body>
```

> float 프로퍼티는 좌측, 우측만 가능하므로 중앙정렬은 **margin** 프로퍼티를 사용해야 한다.
> ```css
> div {
>   width: 960px;
>   margin: 0 auto;
> }
> ```

```css
div {
  color: white;
  font-weight: bold;
  font-size: 30px;
  line-height: 50px;
  height: 50px;
  margin: 0 10px;
  padding: 10px;
}
.d1 {
  background: red;
  float: left;
  /* float가 선언되면 width가 inline 요소와 같이 content에 맞게 최소화 됨 */
}
.d2 {
  background: orange;
}
```

## 9.2 float 프로퍼티 관련 문제 해결 방법

### 9.2.1 float 프로퍼티가 선언된 요소와 float 프로퍼티가 선언되지 않은 요소간 margin이 사라지는 문제

> ```css
> .d2 {
>   background: orange;
>   /* solution */
>   overflow: hidden;
> }
> ```

### 9.2.2 float 프로퍼티를 가진 자식 요소를 포함하는 부모 요소의 높이가 정상적으로 반영되지 않는 문제

```css
.wrap {
  color: white;
  text-align: center;
  padding: 10px;
  background-color: #def0c2;
  /*overflow: hidden;*/
}

/* **이 방법을 사용한다.** */
.clearfix:after {
  content: "";
  display: block;
  clear: both;
}

.d1 {
  float: left;
  width: 49%;
  margin-right: 2%;
  padding: 20px 0;
  background-color: #59b1f6;
}
.d2 {
  float: left;
  width: 49%;
  padding: 20px 0;
  background-color: #ffb5b4;
}
```

```html
<body>
  <div class="wrap clearfix">
    <div class="d1">dv1</div>
    <div class="d2">dv2</div>
  </div>
  <div style="background:red;padding:10px;color:white;">dv3</div>
</body>
```