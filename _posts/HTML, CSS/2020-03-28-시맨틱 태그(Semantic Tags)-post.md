---
title: “시맨틱 태그(Semantic Tags)”
date: 2020-03-38
categories: html/css
---

# 시맨틱 태그(Semantic Tags)
시맨틱 요소는 자신의 의미를 브라우저와 개발자 모두에게 명확하게 설명한다.
기존의 non-semantic 요소들(&#60;div&#62;, &#60;span&#62;..)이 자신의 컨텐츠에 대해 아무것도 설명해주지 않았다면, semantic 요소들(&#60;form&#62;, &#60;table&#62;, &#60;article&#62;..)은 자신의 컨텐츠를 명확하게 정의한다.

- &#60;article&#62;
관심사에 따라서 글을 작성하기 위해 작성되는 독립적인 요소입니다. 또한, &#60;h1&#62; ~ &#60;h6&#62;의 제목 요소를 가지는 것을 권고한다.

- &#60;aside&#62;
주요한 주제가 아닌 부차적인 내용을 담는 태그입니다. &#60;article&#62;태그안에 들어갈 수도있고 외부에 존재할 수도 있습니다. 외부에 존재하는 경우 기존의 &#60;div class=sidebar&#62;과 같은 역할을 한다.

- &#60;footer&#62;
footer라는 이름에서 알 수 있듯, 웹페이지의 발 부분, 즉 하단을 나타내는데 사용되는 태그이다. 웹페이지의 저작권, 상표, 연락처, 회사 주소와같은 웹 페이지의 메인 컨텐츠는 아니지만 게시되어야 하는 부가적인 정보를 가지는 태그이다.

- &#60;header&#62;
&#60;header&#62;태그는 &#60;body&#62;태그 이전에 쓰이는 HTML태그이지만 &#60;header&#62;태그는 &#60;body&#62;태그 안에서 제목 혹은 머리말을 표현하기 위해 사용되는 태그이다.

- &#60;main&#62;
페이지의 메인 컨텐츠를 담는 태그이다. 한 페이지에 한번 쓰일 수 있다.

- &#60;nav&#62;
‘네비게이션 바’라고 불리는 메뉴바와 같은 것들을 포함하는 태그이다.

- &#60;section&#62;
관심사에 따라서 구획을 구분하기 위한 태그이다. 이 또한 &#60;article&#62;태그와 같이 &#60;h1&#62; ~ &#60;h6&#62;의 제목태그를 담는것을 권고한다. 이를 통해 해당 섹션의 관심사가 무엇인지 검색 로봇에 알려줄 수 있다.

## 시맨틱 태그를 사용하면 좋은 점
1. 개발자로 하여금 문서의 의미론적인 구조를 쉽게 파악할 수 있게 해준다(가독성)
2. 검색엔진에게도 의미적으로 중요한 부분과 덜 중요한 부분을 파악할 수 있게 해주어 효율적인 검색을 하도록 만든다. 시멘틱 태그를 사용해서 문서를 만들수록 검색엔진에 쉽게 노출된다.