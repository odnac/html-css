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
