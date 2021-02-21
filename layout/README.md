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

    ### CSS 실습

    이제 완성된 HTML을 이용하여 최종적으로 CSS를 이용해 가로 길이가 800px ~ 1200px로 유동적인 사이트 구성을 만듭니다.

    **1. 기본 태그에 스타일 부여**

    ```css
    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .content {
    	height: 300px;
    	background-color: yellowgreen;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
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
    	background-color: yellowgreen;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
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
    	background-color: yellowgreen;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
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
    				height: 300px;
    				margin: 0 auto;
    				background-color: yellowgreen;
    			}

    			.footer {
    				height: 100px;
    				background-color: dodgerblue;
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

- 다단 레이아웃 제작

    다단 레이아웃은 1단 레이아웃과 함께 매우 대표적인 레이아웃 형태 중 하나입니다.

    예시 이미지와 같이 콘텐츠의 영역이 2개 또는 그 이상의 열(column)로 나눠진 레이아웃을 행의 개수에 따라 2단 레이아웃, 3단 레이아웃으로 부르고 있으며 이런 열의 개수에 따른 레이아웃들을 통틀어서 다단 레이아웃(multi column layout)이라고 부릅니다.

    과거에는 다단 레이아웃의 짜임새가 테이블과 비슷하고 PC에서만 고정적인 사이즈로 표현을 했기 때문에 `<table>` 태그를 이용하여 레이아웃을 만드는 방법이 유행을 했습니다.
    하지만 웹표준이 발표되면서 현재는 `<table>` 태그로 레이아웃을 제작하는 사이트는 찾아보기 힘들어졌습니다.

    ### 다단 레이아웃 형태를 가진 사이트들

    - (네이버 뮤직 : 2단) [https://music.naver.com/home/index.nhn](https://music.naver.com/home/index.nhn)
    - (네이버 지식인 : 2단) [https://kin.naver.com/index.nhn](https://kin.naver.com/index.nhn)
    - (네이버 날씨 : 3단) [https://weather.naver.com](https://weather.naver.com)

    ### 주요 기능

    - 콘텐츠의 열(column)이 두개를 가짐
    - 콘텐츠와 사이드 영역의 구분선을 가짐
    - 구분선은 헤더와 푸터에 항상 맞닿음

    ### 스타일 정보

    - 콘텐츠 영역 가로 길이 : 500px
    - 사이드 영역 가로 길이 : 300px

    ### 주요 태그 및 속성

    **HTML**

    - div

    **CSS**

    - float
    - clear
    - display: table
    - display: table-cell

    ---

    ### HTML 실습

    ```html
    <!-- 2단 레이아웃 -->
    <div class="wrap">
    	<div class="header">header</div>
    	<div class="content">content</div>
    	<div class="aside">aside</div> <!-- 사이드 영역 추가 -->
    	<div class="footer">footer</div>
    </div>
    ```

    우선은 1단 레이아웃과 같이 각 항목을 생성해줍니다.
    2단 메뉴에서는 사이드 영역이 추가되므로, aside라는 클래스명을 가진 `<div>` 태그를 추가했습니다.

    물론 이렇게 만들고 적당한 CSS 코드를 추가하여 원하는 레이아웃의 형태를 구성할 수도 있겠지만 이번 실습에서 float과 display: table; 속성을 이용하여 실습을 진행할 것이기 때문에 각 영역만 나열된 형태로는 원하는 레이아웃의 형태를 잡을수 없습니다.

    행(column)을 나누게 될 영역들을 container라는 클래스명을 가진 `<div>` 태그로 묶어줍니다.

    ```html
    <div class="wrap">
    	<div class="header">header</div>
    	<div class="container"> <!-- content와 aside의 묶음 영역 추가 -->
    		<div class="content">content</div>
    		<div class="aside">aside</div>
    	</div>
    	<div class="footer">footer</div>
    </div>
    ```

    ---

    ### CSS 실습 (float)

    이제 완성된 HTML에 CSS를 추가하여 원하는 형태의 레이아웃을 만듭니다.

    **1. 사전 스타일 부여**

    ```css
    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	width: 800px;
    }

    .content {
    	width: 500px;
    	height: 300px;
    	background-color: yellowgreen;
    }

    .aside {
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    먼저 요구사항에 맞게 각 영역에 적당한 너비와 높이, 색상을 부여하여 확인하기 쉽도록 하고 1단 레이아웃과 같은 형태로 만들어 줍니다.

    aside가 block 요소이기 때문에 아래로 그냥 떨어지는 형태가 됩니다.
    aside 영역을 content 영역의 옆으로 붙이기 위해서 float을 추가합니다.

    **2. float을 이용하여 정렬**

    ```css
    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	width: 800px;
    }

    .content {
    	float: left; /* float 추가 */
    	width: 500px;
    	height: 300px;
    	background-color: yellowgreen;
    }

    .aside {
    	float: left; /* float 추가 */
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    float을 이용해 정렬하기 위해 content와 aside 클래스에 float: left; 속성을 추가하였습니다.

    하지만 이것만으로 float을 통해 정렬하는 과정이 끝난것은 아닙니다.
    이렇게 하면 footer 영역이 content 영역과 aside 영역의 뒤로가서 header 영역과 붙어버립니다.

    이를 위해서는 aside 영역 뒤에 오는 요소(footer)를 float에서 해제해야 합니다.

    **3. float 해제**

    ```css
    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	width: 800px;
    }

    .container:after { /* 가상요소 after를 이용하여 float 해제 */
    	clear: both; /* float 해제 */
    	display: block;
    	content: '';
    }

    .content {
    	float: left;
    	width: 500px;
    	height: 300px;
    	background-color: yellowgreen;
    }

    .aside {
    	float: left;
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    이제 footer 영역이 float의 영향에서 해제되었습니다.

    이렇게 해서 원하는 모습의 기본 모습이 완성되었습니다.
    float을 해제하는 방법은 여러 방법이 존재하며, 각 방법을 상황에 따라 적절하게 이용합니다.

    **4. 가운데 정렬 및 container 높이값 100% 설정**

    ```css
    html, body, .wrap { /* 최상단 부모 요소로부터 상속받는 container의 min-height 값을 100%로 하기 위해 */
    	height: 100%;
    }

    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	width: 800px;
    	min-height: 100%; /* 요구사항인 container 영역의 최소 높이 100%를 만족하기 위해 */
    	padding: 100px 0; /* header, footer의 값이 fixed로 정해진 것이 아니기에 포함되어 계산 */
    	margin: -100px auto; /* 때문에 padding을 주어 100px 만큼 떨어뜨린후, margin을 이용하여 당겨옵니다 (padding 영역에 포함되도록) */
    	box-sizing: border-box; /* padding에 min-height 값이 포함되므로, padding 값이 min-height 값에 영향을 주지 않게 하기 위하여 속성 추가 */
    }

    .container:after {
    	clear: both;
    	display: block;
    	content: '';
    }

    .content {
    	float: left;
    	width: 500px;
    	height: 300px;
    	background-color: yellowgreen;
    }

    .aside {
    	float: left;
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    content 영역과 aside 영역을 가운데 정렬시키기 위해 두 영역을 감싸고 있는 container 영역에 가운데 정렬을 위한 margin: 0 auto;를 추가합니다.

    요구사항인 container 영역의 최소 높이 100%를 가질수 있도록 min-height 속성을 추가합니다.

    그리고 이 min-height 값은 최상단의 부모 요소로부터 상속을 받아야 되기 때문에 html, body, .wrap에 height 값을 100%를 주어야 container의 min-height 값이 적용됩니다.

    이렇게 되면 footer 영역이 화면 아래로 내려가게 되므로 footer 영역을 다시 끌어올려야 합니다.

    상단 고정 레이아웃을 만들때와 다르게 header 영역이 fixed로 값이 떨어진 것이 아니기 때문에 header 영역의 height 값 100px도 포함되어 계산되어야 합니다.

    이를 위해 위 아래로 padding 값을 줘서 위, 아래로 100px 만큼 떨어뜨린 후, margin을 위, 아래 -100px 만큼 주어 다시 당겨줍니다.

    하지만 이 상태에서도 footer 영역은 container의 padding 영역에 포함되었지 끌어올려지지 않았습니다.
    이는 padding에 min-height 값이 포함되어서 그렇습니다.

    padding 값이 min-height 값에 영향을 주지 않게 하기 위하여 box-sizing: border-box; 속성을 주어 해결합니다.

    padding 값이 min-height값에 포함되지 않아, footer 영역이 정상적으로 맨 아래에 붙는 것을 확인할 수 있습니다.

    **5. 구분선 만들기**

    ```css
    html, body, .wrap {
    	height: 100%;
    }

    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	width: 800px;
    	min-height: 100%;
    	padding: 100px 0;
    	margin: -100px auto;
    	box-sizing: border-box;
    }

    .container:after {
    	clear: both;
    	display: block;
    	content: '';
    }

    .content {
    	float: left;
    	width: 500px;
    	height: 1000px;
    	border-right: 5px solid black; /* content 영역의 오른쪽에 border로 영역 구분 */
    	background-color: yellowgreen;
    	box-sizing: border-box; /* border 값도 전체 영역 크기의 포함되도록 */
    }

    .aside {
    	float: left;
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    그 다음 요구사항으로 content와 aside 영역 사이에 구분선을 넣는데, 구분선을 header 끝점에서 footer 끝점까지 맞닿아 이어지게 만들려고 합니다.

    예를 들어, 현재 content 영역의 height 값이 임의의 값 300px이 들어가 있는데 이것보다 더 길어지는 경우 height 값이 500px인 경우에는 content 영역의 오른쪽에 border-right 속성을 이용하여 border를 줍니다.

    하지만 확인해보면 aside 영역이 아래로 떨어집니다.
    이는 border의 5px이 content의 width 값 500px과 합해져 505px이 되므로, 가로 길이가 505px되어 버렸고, aside의 300px과 더해지면 container의 width 값인 800px을 넘어버리기 때문에 떨어지는 것입니다.

    그래서 이를 해결하기 위해서 content의 width값을 495px로 줄여도 되지만, 이전에  container에 사용했던 방법으로 box-sizing 속성을 이용하여 border의 값이 width 값에 영향을 끼치지 않도록 하여 문제를 해결합니다.

    다시 정상적으로 aside가 위로 올라온 것을 확인할 수 있습니다.

    하지만 지금 문제는 content가 항상 header의 끝점과 footer의 끝점이 맞닿는 최대값이 되어야만 합니다.

    그래서 이를 해결하기 위해서 다른 방법을 사용하여 구분선을 만들어 보겠습니다.

    ```css
    html, body, .wrap {
    	height: 100%;
    }

    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	position: relative; /* container를 기준점으로 잡아야 하므로 */
    	width: 800px;
    	min-height: 100%;
    	padding: 100px 0;
    	margin: -100px auto;
    	box-sizing: border-box;
    }

    .container:after {
    	clear: both;
    	display: block;
    	content: '';
    }

    .content {
    	float: left;
    	width: 500px;
    	height: 300px;
    	background-color: yellowgreen;
    }

    .aside {
    	float: left;
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .aside:after {
    	position: absolute; /* container를 기준으로 위치를 고정 */
    	/* content와 aside 영역이 나뉘는 부분의 header 끝점과 footer 끝점이 맞닿는 위치 값 */
    	top: 100px;
    	bottom: 100px;
    	right: 300px;
    	width: 5px;
    	background-color: black;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    기존에 추가했던 border-right와 box-sizing 속성을 지워줍니다.
    대신 aside 영역에 가상요소를 이용하여 임의의 도형을 만들어서 띄워줍니다.

    구분선을 header 끝점에서 footer 끝점까지 맞닿아 이어지게 만들고 싶은데, container의 영역은 현재 padding이 위, 아래로 100px씩 가지고 있고, container 영역의 좌측 상단 끝의 위치가 (0, 0)이 될 것입니다.

    그래서 content와 aisde영역이 나뉘는 부분의 header 끝점과 footer 끝점이 맞닿는 위치를 찾아서 도형을 이용하여 연결이되는 구분선을 만들어 줍니다.

    때문에 해당 위치는 top: 100px, right: 300px; bottom: 100px;이 되고, 기준점은 container가 됩니다.

    border 대신 after 가상요소를 이용하여 가상의 도형을 만들고 position 속성을 이용해서 구현한 이유는 content와 aside 영역 중 한 영역만 길어지는 경우 구분선이 어느 한 쪽 영역에 종속되어 있다면 header에서 footer까지 이어지는 구분선을 구현할 수 없기 때문입니다.

    하지만 가상요소를 이용하면 content의 양이 늘어나면서 container가 늘어나더라도 구분선이 제대로 동작합니다.

    ---

    ### 실습 코드 (float)

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>레이아웃 - float을 이용한 2단 레이아웃 제작</title>
    		<link rel="stylesheet" href="./reset.css">
    		<style>
    			html, body, .wrap {
    				height: 100%;
    			}

    			.wrap {
    				text-align: center;
    			}

    			.header {
    				height: 100px;
    				background-color: crimson;
    			}

    			.container {
    				position: relative;
    				width: 800px;
    				min-height: 100%;
    				padding: 100px 0;
    				margin: -100px auto;
    				box-sizing: border-box;
    			}

    			.container:after {
    				clear: both;
    				display: block;
    				content: '';
    			}

    			.content {
    				float: left;
    				width: 500px;
    				height: 300px;
    				background-color: yellowgreen;
    			}

    			.aside {
    				float: left;
    				width: 300px;
    				height: 300px;
    				background-color: orange;
    			}

    			.aside:after {
    				position: absolute;
    				top: 100px;
    				bottom: 100px;
    				right: 300px;
    				content: '';
    				width: 5px;
    				background-color: black;
    			}

    			.footer {
    				height: 100px;
    				background-color: dodgerblue;
    			}
    		</style>
    	</head>
    	<body>
    		<div class="wrap">
    			<div class="header">header</div>
    			<div class="container">
    				<div class="content">content</div>
    				<div class="aside">aside</div>
    			</div>
    			<div class="footer">footer</div>
    		</div>
    	</body>
    </html>
    ```

    ---

    ### CSS 실습 (display: table; display: table-cell;)

    이번에는 동일한 html을 가지고 display: table, display: table-cell 속성을 이용하여 레이아웃을 만들어 보겠습니다.

    **1. 사전 스타일 부여**

    ```css
    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	width: 800px;
    	margin: 0 auto; /* 가운데 정렬 */
    }

    .content {
    	width: 500px;
    	height: 300px;
    	background-color: yellowgreen;
    }

    .aside {
    	width: 300px;
    	height: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    각 영역에 스타일을 부여해 확인히 편한 상태로 다음 단계를 진행합니다.

    **2. display: table, display: table-cell 속성을 이용하여 정렬**

    ```css
    html, body, .wrap { /* 최상단 부모 요소로부터 상속받는 container의 min-height 값을 100%로 하기 위해 */
    	height: 100%;
    }

    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	display: table; /* 부모 요소에 display: table; 추가 */
    	table-layout: fixed; /* 창 크기가 줄어들더라도 자식 요소의 영역을 유지하기 위해 추가 */
    	width: 800px; /* 창 크기가 줄어들더라도 자식 요소의 영역을 유지하기 위해 추가 */
    	min-height: 100%; /* 최소 높이값 */
    	padding: 100px 0;
    	margin: -100px auto;
    	box-sizing: border-box;
    }

    .content {
    	display: table-cell; /* 자식 요소에 display: table-cell; 추가 */
    	width: 500px;
    	background-color: yellowgreen;
    }

    .aside {
    	display: table-cell; /* 자식 요소에 display: table-cell; 추가 */
    	width: 300px; /* 생략 가능 */
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    display: table과 display: table-cell 속성은 table과 동일한 효과를 주기 때문에 부모 요소인 container의 width 값을 부여한 상태에서 한쪽에 width 값을 안다면 나머지 한쪽의 width 값은 따로 지정해주지 않아도 됩니다.

    display: table과 display: table-cell 속성만으로도 정렬이 되었습니다.

    하지만 자식 요소인 content 영역 500px과 aside 영역 300px을 유지해야 하는데 창 크기가 줄어들면 임의적으로 줄어드는것을 확인할 수 있습니다.
    (container 클래스에 display: table; 속성만 존재 하였을 경우 확인 가능)

    때문에 부모 요소인 container에 table-layout: fixed; 속성을 주고, width 값을 800px로 고정하고, 요구 사항인 container 영역의 최소 높이 100%를 가질수 있도록 동일하게 min-height 속성을 추가합니다.

    그리고 이 min-height 값은 최상단의 부모 요소로부터 상속을 받아야 되기 때문에 html, body, .wrap에 height 값을 100%를 주어야 container의 min-height 값이 적용됩니다.

    content와 aside 영역이 container의 크기만큼 늘어난 것을 확인할 수 있습니다.

    하지만 header와 footer가 한 화면에 보여야 하기 때문에 container에 padding을 위, 아래로 100px을 주어 떨어뜨린 후, margin을 -100px을 주어 그 영역만큼 다시 당겨옵니다.

    그리고 padding이 min-height 속성에 영향을 주지 않게 하기 위해 box-sizing: border-box; 속성을 추가하겠습니다.

    이렇게 속성을 추가해주고 나면 우리가 원했던 대로 header와 footer가 한 화면에 보이는 것을 확인할 수 있습니다.

    container는 margin을 통해서 위 아래로 당겨옴으로 인해서 header와 footer 영역은 padding 으로 채워지게 됩니다.
    그래서 실제로 그 안에 들어가는 content와 aside 영역은 header와 footer를 제외한 영역을 오롯이 꽉 채워서 가질수 있게 됩니다.

    float을 이용했던 것과 table-cell로 만드는 것의 확연한 차이점은 container의 길이가 길어지거나 짧아지더라도 부모 table의 높이를 상속해서 자식 table-cell의 높이가 변경되는 것을 확인할 수 있습니다.

    때문에 초반에 넣었던 임의의 height 값은 필요가 없으므로 지우겠습니다.

    **3. 구분선 추가**

    ```css
    html, body, .wrap {
    	height: 100%;
    }

    .wrap {
    	text-align: center;
    }

    .header {
    	height: 100px;
    	background-color: crimson;
    }

    .container {
    	display: table;
    	table-layout: fixed;
    	width: 800px;
    	min-height: 100%;
    	padding: 100px 0;
    	margin: -100px auto;
    	box-sizing: border-box;
    }

    .content {
    	display: table-cell;
    	width: 495px; /* border 크기만큼 -5px */
    	border-right: 5px solid black; /* border를 이용하여 구분선 추가 */
    	background-color: yellowgreen;
    }

    .aside {
    	display: table-cell;
    	width: 300px;
    	background-color: orange;
    }

    .footer {
    	height: 100px;
    	background-color: dodgerblue;
    }
    ```

    구분선은 content의 높이를 그대로 가지기 때문에 content 오른편 또는 aside 왼편으로 구분선을 넣으면 원하는 구분선을 구현할 수 있습니다.

    구분선의 크기만큼 content의 width 값에서 빼주어 구분선을 포함한 가로 길이가 원래의 가로 길이를 넘지 않게 해주었습니다.
    또는 box-sizing: border-box; 속성을 이용하여 content의 가로 길이가 구분선의 크기까지 포함하도록 만들수도 있습니다.

    이 방법의 경우 구분선을 넣어주는 것이 높이 값을 상속받으므로, border 속성을 추가해주기만 하면 되기 때문에, float을 이용한 방법보다 훨씬 간단합니다.

    예를 들어, content의 내용이 길어지는 경우에도 자동으로 늘어나는 것을 확인할 수 있습니다.

    ---

    ### 요약 정리

    display: table; 속성을 이용한 방법은 float 속성을 이용하여 만든 방법과 비교했을때, 과정이나 코드가 조금 더 단순하게 느껴질 수 있습니다.
    하지만 content와 aside 영역에 임의의 높이값을 부여할 때, float 속성을 사용하여 구현한 것과는 달리 `<table>` 태그로 만든 표처럼 영역의 높이가 동일하게 부여되는 것을 확인할 수 있습니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>레이아웃 - display: table을 이용한 2단 레이아웃 제작</title>
    		<link rel="stylesheet" href="./reset.css">
    		<style>
    			html, body, .wrap {
    				height: 100%;
    			}

    			.wrap {
    				text-align: center;
    			}

    			.header {
    				height: 100px;
    				background-color: crimson;
    			}

    			.container {
    				display: table;
    				table-layout: fixed;
    				width: 800px;
    				min-height: 100%;
    				padding: 100px 0;
    				margin: -100px auto;
    				box-sizing: border-box;
    			}

    			.content {
    				display: table-cell;
    				width: 495px;
    				border-right: 5px solid black;
    				background-color: yellowgreen;
    			}

    			.aside {
    				display: table-cell;
    				width: 300px;
    				background-color: orange;
    			}

    			.box {
    				margin: 100px;
    				width: 200px;
    				height: 600px;
    				background-color: blueviolet;
    			}

    			.footer {
    				height: 100px;
    				background-color: dodgerblue;
    			}
    		</style>
    	</head>
    	<body>
    		<div class="wrap">
    			<div class="header">header</div>
    			<div class="container">
    				<div class="content">
    				content
    					<div class="box">box</div>
    				</div>
    				<div class="aside">aside</div>
    			</div>
    			<div class="footer">footer</div>
    		</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)

- 고정 레이아웃 제작