# layout 제작

- 레이아웃 소개

    레이아웃 제작은 모든 웹사이트를 만드는 과정에서 가장 먼저 선행되어야 하는 작업입니다.
    우리는 웹사이트의 사용성, 특성, 분위기 등에 따라서 다양한 레이아웃 중에 하나를 채택하여 디자인하고 제작할 수 있습니다.
    그러기 위해서는 웹페이지 제작에서의 레이아웃에 대해서 알아보고 그 종류는 무엇인지 이해하고 있어야 합니다.

    ### 웹 페이지의 레이아웃이란?

    레이아웃은 책이나 신문, 잡지 등의 출판물에서 글이나 그림을 효과적으로 정리하고 배치하는 일을 뜻하는 출판 용어입니다.
    이와 같이 웹사이트를 제작할때 메뉴, 컨텐츠, 부가정보 등과 같은 구성요소들을 필요한 곳에 위치하여 사용자가 효과적으로 웹사이트를 이용할 수 있게 배치하는 작업을 일컫습니다.

    ### 레이아웃(그리드 레이아웃)의 종류

    - 1단 레이아웃
    - 다단(2단, 3단, ...) 레이아웃
    - 고정(상, 하단 고정) 레이아웃
    - 그 외의 다양한 레이아웃

    ---

    ### 참고자료

    [CSS layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)

    [CSS Website Layout](https://www.w3schools.com/css/css_website_layout.asp)

    [Introduction to CSS layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)

- 1단 레이아웃 제작

    1단 레이아웃은 레이아웃의 종류 중에 가장 기본이 되는 레이아웃입니다.
    때문에 레이아웃 제작 과정중에 가장 단순하고 쉽습니다.

    1단 레이아웃은 하나의 행(column)으로 이루어진 레이아웃의 형태를 일컫습니다.

    이런 형태의 레이아웃은 웹에서 가장 기본이 되는 레이아웃이며 위의 이미지처럼 상단(header), 중단(contents), 하단(footer)의 구성으로 이루어져있는 것이 가장 일반적입니다.

    ### 1단 레이아웃 형태를 가진 사이트들

    - (네이버 쇼핑) [shopping.naver.com/home/p/index.nhn](http://shopping.naver.com/home/p/index.nhn)
    - (네이버 사전) [dict.naver.com](http://dict.naver.com)
    - (네이버 포스트) [post.naver.com/navigator.nhn](http://post.naver.com/navigator.nhn)

    ### 주요 기능

    - 1개의 행(column)을 갖는 레이아웃
    - 요소로 header, content, footer를 가짐

    ### 스타일 정보

    - 컨텐츠 최대 가로 길이 : 1200px
    - 컨텐츠 최소 가로 길이 : 800px
    - 컨텐츠 가운데 정렬

    ### 주요 태그 및 속성

    **HTML**

    - div
    - header
    - section
    - footer

    **CSS**

    - max-width
    - min-width
    - margin

    ---

    ### HTML 실습

    ```html
    <!-- 1단 레이아웃 -->
    <div class="header">header</div>
    <div class="content">content</div>
    <div class="footer">footer</div>
    ```

    레이아웃을 제작하기 위해서 각 div의 class나 id에 해당영역에 대한 이름을 부여합니다.
    이것은 HTML5가 나오기 전까지 div를 이용하여 레이아웃을 제작하는 가장 일반적인 방법입니다.

    ```html
    <!-- HTML5의 태그를 이용한 1단 레이아웃 -->
    <header>header</header>
    <section>content</section>
    <footer>footer</footer>
    ```

    하지만 HTML5의 발표로 레이아웃 각 요소의 의미를 태그명 자체에 내포하고 있는 새로운 태그가 등장했고, 이 새로운 태그들을 이용한다면 위의 코드처럼 제작할 수 있습니다.
    이 HTML5의 새로운 태그들은 각 요소의 명칭을 class나 id에 부여한 div와 동일한 의미를 갖습니다.

    마지막으로 이렇게 레이아웃에 필요한 요소들(header, section, footer 등)을 `<body>` 태그 안에 바로 작성하는 것 보다는 레이아웃과 관련된 아이템들을 감쌀 수 있는 wrap(또는 wrapper) 클래스를 가진 div를 만들어 레이아웃 컨테이너의 역할을 할 수 있도록 합니다.

    ```html
    <!-- div를 이용한 1단 레이아웃 -->
    <div class="wrap">
    	<div class="header">header</div>
    	<div class="content">content</div>
    	<div class="footer">footer</div>
    </div>

    <!-- HTML5를 이용한 1단 레이아웃 -->
    <div class="wrap">
    	<header>header</header>
    	<section>content</section>
    	<footer>footer</footer>
    </div>
    ```

    ---

    CSS 실습

    이제 완성된 HTML을 이용하여 최종적으로 CSS를 이용해 가로 길이가 800px ~ 1200px로 유동적인 사이트 구성을 만듭니다.

    **1. 기본 태그에 스타일 부여**

    ```css
    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .content {
    	height: 300px;
    	background-color: dodgerblue;
    }

    .footer {
    	height: 100px;
    	background-color: yellowgreen;
    }
    ```

    **2. 콘텐츠 영역 최대값 (1200px) 및 가운데 정렬**

    ```css
    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .content {
    	max-width: 1200px; /* 최대 가로 길이 1200px */
    	margin: 0 auto; /* 블럭 요소 가운데 정렬 */
    	height: 300px;
    	background-color: dodgerblue;
    }

    .footer {
    	height: 100px;
    	background-color: yellowgreen;
    }
    ```

    **3. 전체 영역 최소값 (800px)**

    ```css
    .wrap {
    	min-width: 800px; /* 최소 가로 길이 800px */
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .content {
    	max-width: 1200px;
    	margin: 0 auto;
    	height: 300px;
    	background-color: dodgerblue;
    }

    .footer {
    	height: 100px;
    	background-color: yellowgreen;
    }
    ```

    위의 순서대로 따라 했다면 브라우저에서 확인했을때 아래와 같은 스타일 변화를 볼 수 있습니다.

    ---

    ### 요약 정리

    **margin을 이용한 블럭요소 좌우 가운데 정렬**

    ```html
    <div>
    	<p></p>
    </div>
    ```

    위와 같은 HTML 구조는 `<p>` 태그가 블럭요소이기 때문에 text-align으로는 `<p>` 태그 자체를 가운데 정렬할 수는 없습니다.
    임의의 블럭 요소 `<div>` 안에 블럭요소 `<p>` 의 가운데 정렬을 가장 쉽게 하는 방법 중에 하나가 margin을 이용한 방법입니다.

    ```css
    div {
    	width: 300px;
    	height: 300px;
    }

    p {
    	width: 100px;
    	height: 100px;
    	margin: 0 auto;
    }
    ```

    부모 요소인 `<div>` 가 임의의 사이즈를 갖고 있고 자식 요소인 `<p>` 태그는 그보다 작은 사이즈를 갖고 있다고 가정하는 경우, 위의 조건을 만족할때 그 자식 블럭요소의 margin을 좌, 우로 auto 값을 부여한다면 margin은 좌, 우 수치를 균등하게 나눠가지게 됩니다.
    그렇게 해서 이번 예제에서 최대 가로 길이(1200px)를 넘어서는 레이아웃일때 content를 가운데 정렬할 수 있습니다.

    하지만 `<p>` 태그의 margin 값을 상, 하에 auto로 넣었을 때는 위, 아래의 가운데를 찾지는 못합니다.
    그 이유는 블럭요소는 기본적으로 좌우가 꽉차면서 부모의 좌측 끝과 우측 끝의 사이즈를 인식할 수 있지만, 무조건 위에서 아래로 쌓이는 블럭 요소의 특성상 부모의 위쪽 끝과 아래쪽 끝의 사이즈를 인식할 수는 없기 때문입니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>레이아웃 - 1단 레이아웃 제작</title>
    		<link rel="stylesheet" href="./reset.css">
    		<style>
    			.wrap {
    				min-width: 800px;
    				text-align: center;
    			}

    			.header {
    				height: 100px;
    				background-color: crimson;
    			}

    			.content {
    				max-width: 1200px;
    				margin: 0 auto;
    				height: 300px;
    				background-color: dodgerblue;
    			}

    			.footer {
    				height: 100px;
    				background-color: yellowgreen;
    			}
    		</style>
    	</head>
    	<body>
    		<div class="wrap">
    			<div class="header">header</div>
    			<div class="content">content</div>
    			<div class="footer">footer</div>
    		</div>
    	</body>
    </html>
    ```