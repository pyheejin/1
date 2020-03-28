---
title: "CSS의 정의와 역할"
date: 2020-03-28
categories: html/css
---

# CSS(Cascading Style Sheets)
Style sheet 언어로 HTML 문서에 있는 요소들에 선택적으로 스타일을 적용할 수 있다.

### HTML에 반영하는 방법
1. 인라인 스타일 : 태그 style 속성에 직접 작성

```css
<h1 style="color: red;">FRONTEND 101</h1>
```

2. style 태그 : html 파일의 style 태그 안에 작성

```html
<style>
    h2 {
        color: #408090;
    }
</style>
```

3. css 파일에 작성 : html 파일과 분리하여 css파일에 따로 작성
(대신 html파일에서 어느 css파일이 쓰였는지 브라우저에 알려야 하므로, &#60;head&#62;와 &#60;/head&#62; 안에 링크를 해주는 태그를 추가해야 한다.)
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width">
        <title>Page Title</title>
        <link href="index.css" rel="stylesheet" type="text/css" />
    </head>

    <body>
        <h1>My First Heading</h1>
        <p>My first paragraph.</p>
    </body>
</html>
```