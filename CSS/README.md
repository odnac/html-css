## 참고 문서

:bookmark_tabs: [MDN-CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)

<br/>

## CSS

css가 하는 일은 HTML 태그를 가리키는 일이다.

#### 기본구조

```css
selector {
    property: value;
}
```

<br/>

## 브라우저와 CSS

> 브라우저가 CSS를 읽는 방식은 cascading이다. \(위에서부터 아래로 차례대로 읽는다.\)<br/>
> 만약 같은 selector를 가리키는 CSS가 여러 개이면 가장 마지막 스타일이 적용된다.

<br/>

## CSS를 HTML에 추가하는 방법

1. inline CSS, 태그를 열어서 그 안에 css를 작성<br/>
2. external CSS, css를 가지는 파일명을 만들어 css파일과 html 도큐먼트의 관계를 stylesheet으로 명시

<br/>

## block & inline

\<div\>와 같이 하나의 요소 옆에 다른 요소가 올 수 없는 것을 **_block_** <br/>
\<span\>과 같이 하나의 요소 옆에 다른 요소가 올 수 있는 것을 **_inlin_**

```html
<span> hi </span>
<!--inline-->
<span> my </span>
<span> name </span>
<span> is </span>
<div>
    <!--block-->
    <span> odnac </span>
</div>
<span> !! </span>
<!--inline-->
```

### 실행 결과

<span> hi </span>
<span> my </span>
<span> name </span>
<span> is </span>

<div>
    <span> odnac </span>
</div>
<span> !! </span>

### block inline 차이점

> inline은 css에서 display 속성을 block으로 바꾸면 block으로 바뀐다.</br>
> but, 아무 내용이 없는 block을 inline으로 바꾸면 사라진다. \(내용을 넣으면 보임\) <br/>
> because, **_block_**은 높이와 너비가 있고 **_inline_**은 높이와 너비가 없기 때문이다.

### block의 특징

#### <ul><li>margin : 경계의 바깥에 있는 공간</ul></li>

```css
* {
    margin: 20px; /* 상하좌우 20px */
    margin: 20px 15px; /* 상하20px, 좌우15px */
    margin: 20px 5px 12px 9px; /* 상20px 우5px 하12px 좌9px */
}
```

##### Collapsing margins, 마진 붕괴 현상 :bookmark_tabs: [참고자료](https://velog.io/@raram2/CSS-%EB%A7%88%EC%A7%84-%EC%83%81%EC%87%84Margin-collapsing-%EC%9B%90%EB%A6%AC-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4)

#### <ul><li>padding : 경계의 안쪽에 있는 공간</ul></li>

```css
* {
    padding: 20px; /* 상하좌우 20px */
    padding: 20px 15px; /* 상하20px, 좌우15px */
    padding: 20px 5px 12px 9px; /* 상20px 우5px 하12px 좌9px */
}
```

#### <ul><li>border : 경계</ul></li>

```css
* {
    border: 2px solid black;
}
```

> \* 모든 태그를 의미한다. <br/>  
> **Tip**  
> inline은 높이와 너비를 가질 수 없기 때문에 margin 좌우만 가질 수 있다.  
> padding은 상하좌우 가질 수 있다.

<br/>

## id class

```html
<!-- 
        id : 겹치면 안 됨
        class : 겹쳐도 됨
        
        #abc == id="abc"
        .abc == class="abc" 
    -->

<head>
    <style>
        .fruit {
            background-color: green;
        }
        #apple {
            color: red;
        }
        #banana {
            color: yellow;
        }
    </style>
</head>
<body>
    <span id="apple" class="fruit">hello</span>
    <span id="banana" class="fruit">hello</span>
</body>
```

<br/>

## display: flex

box들을 옆으로 둘 때

##### flexbox froggy :bookmark_tabs: [공부 사이트](https://flexboxfroggy.com/#ko)

```html
<head>
    <style>
        body {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100vh;
            flex-direction: column; /* row */
            flex-wrap: wrap; /* nowrap */
        }
        div {
            width: 300px;
            height: 300px;
        }
    </style>
</head>
<body>
    <div></div>
    <div></div>
    <div></div>
</body>
```

1. 자식 엘리먼트에는 어떤 것도 적지 말아햐 한다. 부모 엘리먼트에만 명시해야 한다. 원하는 것을 움직이려면 부모 엘리먼트를 flex로 바꿔야한다.
2. justify-content : 주축, align-items 교차축, vh = viewport height 화면 100% 말함
3. height을 지정해주지 않으면 align-items를 설정해도 바뀌지 않음. 이미 중심에 있을테니까
4. flex-direction: column을 하면 주축과 교차축이 바뀜
5. flex-wrap: 창을 줄였을 때 wrap이면 div의 크기가 압축되고 nowrap이면 div의 크기를 유지하기 위해 다음 줄로 내려간다.

<br/>

## position: fixed

화면 고정하기

```html
<head>
    <style>
        body {
            height: 1000vh;
            margin: 20px;
        }
        div {
            width: 300px;
            height: 300px;
            color: white;
            background-color: teal;
        }
        #fixed {
            position: fixed;
            background-color: wheat;
            width: 350px;

            /* top, left, right, bottom 중 하나만 수정해도 서로 다른 레이어에 위치하게 되어 원래 위치가 무시된다. */
            /* 
            top: 5px;
            left: 10px;
            right: 15px;
            bottom: 20px; 
            */
        }
    </style>
</head>
<body>
    <div></div>
    <div id="fixed"></div>
</body>
```

> position: fixed;를 이용하면 스크롤해도 항상 화면 제자리에 머문다. 광고 생각하면 된다.  
> 하지만 top, left, right, bottom 중 하나만 수정해도 서로 다른 레이어에 위치하게 되어 원래 위치가 무시된다.  
> position fixed를 이용하면 가장 위에 위치하게 된다.(맨 앞)

<br/>

## position: static \( default \)

레이아웃이 박스를 처음 위치하는 곳에 두는 것

```html
<head>
    <style>
        body {
            height: 1000vh;
            margin: 20px;
        }
        div {
            width: 300px;
            height: 300px;
            color: white;
            background-color: teal;
            position: static;
        }
    </style>
</head>
<body>
    <div></div>
</body>
```

<br/>

## position: relative

element가 '처음 생성된 위치'를 기준점으로, top bottom left right로 위치를 조금씩 수정할 수 있다.

```html
<head>
    <style>
        body {
            height: 1000vh;
            margin: 20px;
        }
        div {
            width: 300px;
            height: 300px;
            color: white;
            background-color: teal;
        }
        #relative {
            position: relative;
            background-color: wheat;
            width: 50px;
            height: 50px;
            top: -10px;
            left: -10px;
        }
    </style>
</head>
<body>
    <div>
        <div id="relative"></div>
    </div>
</body>
```

<br/>

## position: absolute

가장 가까운 relative 부모를 기준으로 이동. relative 부모가 없으면 body가 기준이 됨

```html
<head>
    <style>
        body {
            height: 1000vh;
            margin: 20px;
        }
        div {
            width: 300px;
            height: 300px;
            color: white;
            background-color: teal;
            position: relative; /* relative가 없으면 가장 가까운 relative가 기준이 된다. 만약 이 코드가 없다면 body가 기준이 됨 */
        }
        #absolute {
            position: absolute;
            background-color: wheat;
            width: 50px;
            height: 50px;
            bottom: 0px;
        }
    </style>
</head>
<body>
    <div>
        <div id="absolute"></div>
    </div>
</body>
```

<br/>

## Combinators

```html
<head>
    <style>
        body {
            height: 1000vh;
            margin: 20px;
        }
        span {
            color: tomato;
            background-color: yellow;
        }

        /* 부모 자식에 접근하기 */
        p span {
            color: teal;
        }

        /* div 아래 있는 자식, 손자 노드 등 까지 모든 <span>에 적용. outside과 inside <span>에 모두 적용 됨 */
        div span {
            text-decoration: underline;
        }

        /* div 바로 아래 자식 노드 <span>만 적용. outside <span>만 적용 됨 */
        div > span {
            border: solid;
        }

        /* span의 형제노드지만 가장 가깝지 않을 때 적용 */
        span ~ p {
            text-decoration: overline;
        }

        /* span의 가장 가까운 형제노드 p에만 적용 */
        span + p {
            text-decoration: line-through;
        }
    </style>
</head>
<body>
    <div>
        <span>outside</span>
        <p>
            daslkfjsdlkfjasldkjflaskdjflaskdjflaskdjflasdjflaskdjflaksjflaksdjfaklsdjflaksdjflk.
            <span>inside</span>
        </p>
        <p>여긴 span ~ p 적용 되네?</p>
    </div>
</body>
```

<br/>

## Pseudo Selectors

```html
<head>
    <style>
        /* 방식 1 */
        input:optional {
            border: 1px solid wheat;
        }
        input:required {
            border: 1px solid tomato;
        }

        /* 방식 2 */
        input {
            border: 1px solid wheat;
        }
        input:required {
            border-color: tomato;
        }

        /* ~= 포함하는 */
        input[placeholder~="name"] {
            background-color: pink;
        }

        input[type="password"] {
            background-color: thistle;
        }
    </style>
</head>
<body>
    <div>
        <form>
            <input type="text" placeholder="first name" />
            <input type="text" placeholder="last name" />
            <input type="password" required placeholder="password" />
        </form>
    </div>
</body>
```

<br/>

## States

```html
<head>
    <style>
        /* 마우스로 클릭 중일 때 */
        button:active {
            background-color: blue;
        }
        /* 마우스를 위로 올릴 때 */
        button:hover {
            background-color: red;
        }
        /* 키보드로 선택 할 때 */
        input:focus {
            background-color: tomato;
        }
        /* 방문 했을 때 */
        a:visited {
            color: purple;
        }
        form {
            border: 1px solid salmon;
            display: flex;
            flex-direction: column;
            padding: 20px;
        }
        /* 자식이 선택 될 때 본인(부모)가 바뀜 */
        form:focus-within {
            border-color: seagreen;
        }
        /* 부모가 선택 될 때 자식이 바뀜 */
        form:hover input {
            background-color: black;
        }

        form:hover input:focus {
            background-color: aqua;
        }
    </style>
</head>
<body>
    <form>
        <button>Hello</button>
        <input type="text" />
        <input type="text" />
        <a href="https://apple.com">Apple</a>
    </form>
</body>
```

<br/>

## Pseudo Elements

```html
<head>
    <style>
        input {
            color: blue;
        }
        input::placeholder {
            color: yellowgreen;
        }
        /* 글짜 드래그 할 때 */
        p::selection {
            color: white;
            background-color: yellowgreen;
        }
        p::first-letter {
            font-size: 50px;
        }
        p::first-line {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <form>
        <input type="text" placeholder="Name" />
    </form>
    <p>
        sdfasdfjasldfalsdjfklasjdflkajsdlfkjasdlkfj
        sldfjlskjdflkasjdflkasjdlfkjaslkdjfalsjfalskj
        asldkjfaksldjflksajdlfkasjdlfkajsdlkjsajdlkjfslk
    </p>
</body>
```

<br/>

## Variable : 변수

:root 모든 documentd의 뿌리

```html
<style>
    :root {
        --variable: value;
        --main-color: #fcce00;
    }
    p {
        top: var(--variable);
        background-color: var(--main-color);
    }
</style>
```

<br/>

## Trasitions : 상태의 변화를 보내주는 애니메이션

```html
<head>
    <title>hihihih</title>
    <style>
        a {
            color: white;
            background-color: tomato;
            text-decoration: none;
            padding: 3px 5px;
            border-radius: 5px;
            font-size: 20px;

            /* 
                transition은 state가 없는 요소에 써야한다. (hover가 없는 쪽)
                state에서 사용하는 요소만 transition이 바꿀 수 있다. (transition의 background-color와 color는 a:hover에서 바꿨기 때문에 적용된다.)
            */
            /* 
                ease-in function : 브라우저에게 애니메이션이 어떻게 변할지 말해준다
                defualt : linear, ease-in, ease-in-out, ease-out, ease
                cubic-bezier : ease-in function 사용자화
            */
            transition: background-color 1s ease-in-out, color 2s ease-in-out;
            /* all 5s ease-in-out 한번에 바꾸고 싶으면 all 사용 */
        }
        a:hover {
            color: tomato;
            background-color: wheat;
        }
    </style>
</head>
<body>
    <a href="#">gogogo</a>
</body>
```

<br/>

## transformations : 요소를 변형시킨다

```html
<head>
    <title>hihihih</title>
    <style>
        img {
            border: 5px solid black;
            border-radius: 50%;

            /* 
                transformation은 box element를 변형시키지 않는다. 
                즉 sibling(이 코드에선 <p>태그)에게 영향을 끼치지 않는다.

                다른 요소의 box를 변형시키지 않고 원하는 요소를 이동시키기 위해서 사용하는 것
                transformation은 페이지 픽셀의 다른 부분에서 일어난다.
            */
            transform: rotateZ(80deg);
        }
    </style>
</head>
<body>
    <img src="minion.jpg" />
    <p>이 글자는 transformation에 의해 영향 받지 않고 가만히 자리에 있어요.</p>
</body>
```

<br/>

## Animations

#### 기본구조

```html
<style>
    @keyframes animationName {
        from {
            행동
        }
        to {
            행동
        }
    }
</style>
```

```html
<head>
    <title>Animation</title>
    <style>
        @keyframes coinflip {
            from {
                transform: rotateX(0deg);
            }
            to {
                transform: rotateX(360deg);
            }
        }
        img {
            border: 5px solid black;
            border-radius: 50%;
            animation: coinflip 5s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <img src="minion.jpg" />
</body>
```

<br />

## Media Queries : 오직 CSS만을 이용해서 스크린의 사이즈를 알 수 있는 방법

```css
<style>
@media screen {

}
@media print {

}
</style>
```

## box-sizing: border-box;

> 200px의 박스에 padding-left 50px를 주면 css는 200px의 박스 크기를 유지하려고 박스의 크기가 50 + 200 => 250 픽셀로 늘어난다.  
> 이를 막기 위해 box-sizing을 쓰면 200px 박스 크기를 유지하면서 패딩을 줄 수 있다.
