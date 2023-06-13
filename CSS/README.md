## CSS

css가 하는 일은 HTML 태그를 가리키는 일이다.

###기본구조

```
    selector {
        property: value;
    }
```

## 브라우저와 CSS

브라우저가 CSS를 읽는 방식은 cascading이다. \(위에서부터 아래로 차례대로 읽는다.\)
만약 같은 selector를 가리키는 CSS가 여러 개이면 가장 마지막 스타일이 적용된다.

<br/>

## CSS를 HTML에 추가하는 방법

inline CSS, 태그를 열어서 그 안에 css를 작성
external CSS, css를 가지는 파일명을 만들어 css파일과 html 도큐먼트의 관계를 stylesheet으로 명시
