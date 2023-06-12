## 참고 문서

:bookmark_tabs: [MDN-HTML](https://developer.mozilla.org/ko/docs/Web/HTML/Element/html)

<br/>

## 기본 구조

```
<!DOCTYPE html>
<html lang="kr">
    <head>
        <meta charset="utf-8"/>
        <title></title>
    </head>

    <body>

    </body>
</html>
```

</br>

## \<head\> 태그

```
<html lang="kr">    // 브라우저에게 어떤 언어를 사용하는지 알려줌
<link rel="shortcut icon" href="https://assets.nflxext.com/us/ffe/siteui/common/icons/nficon2016.ico">  // 탭 이미지
<title>넷플릭스 대한민국 - 인터넷으로 시리즈와 영화를 시청하세요</title>
<meta name="description" content="스마트 TV, 태블릿, 스마트폰, PC, 게임 콘솔 등 다양한 디바이스에서 영화와 시리즈를 마음껏 즐기세요.">
<meta charset="utf-8"/>
```

<br/>

## 태그 예시

```
<!-- unordered list, item list -->
<ul>
    <li>beer</li>
    <li>meat</li>
    <li>milk</li>
</ul>

<!-- orderdd list -->
<ol>
    <li>beer</li>
    <li>meat</li>
    <li>milk</li>
</ol>
```

### 실행 결과

<!-- unordered list, item list -->
<ul>
    <li>beer</li>
    <li>meat</li>
    <li>milk</li>
</ul>

<!-- orderdd list -->
<ol>
    <li>beer</li>
    <li>meat</li>
    <li>milk</li>
</ol>

<br/>

## \<form\> 태그

사용자로부터 입력을 받을 수 있는 HTLM 입력 폼(form)을 정의할 때 사용합니다.

```
<form>
    <input id="first-name" required placeholder="Name" type="text" />
    <input required placeholder="Last Name" type="text" />
    <input required placeholder="Username" type="text" />
</form>
```

<br/>

## 속성 예시

```
<a href="http://www.google.com" target="_blank">Go to google.com</a>

<img src="--url--" />

<link rel="shortcut icon" href="https://assets.nflxext.com/us/ffe/siteui/common/icons/nficon2016.ico" />
```

<br/>

## Semantic

```
<nav>
<div id="nav">

<header>
<div class="header">

<footer>
<div id="footer">

```
