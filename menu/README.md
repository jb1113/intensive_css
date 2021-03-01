# 메뉴 제작

- 메뉴 소개

    메뉴는 웹페이지 이동을 도와주는 내비게이션의 역할을 합니다.
    웹사이트에서 메뉴는 필수적으로 제공되어야 하는 중요한 UI 요소 중 하나입니다.

    ### 메뉴란?

    메뉴는 다른 말로 내비게이션이라고도 불립니다.
    사용자가 웹사이트 내에 있는 다양한 페이지를 이동할 수 있도록 지원하며 웹사이트에서 제공되는 정보를 쉽게 찾을 수 있도록 도와주는 역할을 합니다.

    ### 메뉴의 종류

    - 1단 메뉴
    - 2단 메뉴
    - 좌/우측 메뉴

    ### 메뉴를 가진 사이트들

    - (네이버 쇼핑) [shopping.naver.com/help/service_guide/index.nhn](http://shopping.naver.com/help/service_guide/index.nhn)
    메인 화면을 살펴보면 본문 상단에서 1단 메뉴를 사용하고 있습니다.
    메뉴는 외곽선을 갖는 4개의 셀을 가지고 있습니다.
    - (네이버 영화) [movie.naver.com](https://movie.naver.com/)
    좌측을 보면 2단으로 구성된 세로 메뉴를 제공하고 있습니다.
    메뉴를 클릭하여 해당 페이지로 이동했을 경우 메뉴가 활성화되는 부분도 확인이 가능합니다.

    ---

    ### 참고자료

    [CSS Navigation Bar](https://www.w3schools.com/css/css_navbar.asp)

- 1단 메뉴 제작

    메뉴 UI는 웹사이트에서 주요 섹션으로 바로 이동할 수 있도록 하는 내비게이션 역할을 하므로 많이 사용되고 있는 UI입니다.
    그 중 가장 간단한 형태인 1단 메뉴를 제작해 보도록 하겠습니다.

    ### 주요 기능

    - 5개의 항목을 갖는 가로 메뉴
    - 메뉴의 간격은 모두 동일
    - 선택 메뉴는 볼드 처리
    - 메뉴 활성화 시 배경색과 폰트 컬러 변경

    ### 스타일 정보

    - 메뉴 전체 너비 (min/max) : 500px/700px
    - 메뉴 높이 : 36px
    - 메뉴 기본 폰트 : 12px/#333, 외곽선 : 1px/#ddd
    - 메뉴 활성화 시 배경색 : gray, 폰트 : 12px/bold/#fff, 외곽선 : 1px/#555

    ### 주요 태그 및 속성

    **HTML**

    - div
    - ul
    - li
    - a

    **CSS**

    - min-width
    - max-width
    - display: table;
    - table-layout: fixed;
    - display: table-cell;
    - position: relative;
    - border
    - margin-left
    - :hover

    ---

    ### HTML 실습

    ```html
    <div class="wrap">
    	<ul class="menu">
    		<li class="menu_item"><a href="#" class="menu_link">메일</a></li>
    		<li class="menu_item active"><a href="#" class="menu_link">카페</a></li>
    		<li class="menu_item"><a href="#" class="menu_link">소프트웨어</a></li>
    		<li class="menu_item"><a href="#" class="menu_link">지식백과</a></li>
    		<li class="menu_item"><a href="#" class="menu_link">영화</a></li>
    	</ul>
    </div>
    ```

    메뉴는 여러개의 메뉴 아이템을 가지고 있으므로 리스트 태그인 `<ul>` 태그와 `<li>` 태그를 이용하여 만드는 것이 일반적입니다.
    스타일 적용을 위해 각각 클래스를 추가하고, 메뉴 아이템 클릭 시 페이지 이동이 되어야 하므로 `<li>` 태그 안에 메뉴명을 감싸는 `<a>` 태그를 추가합니다.

    메뉴 활성화 처리를 위해 특정 `<li>` 태그에 active 클래스를 추가합니다.

    최종적으로 제작하려고 하는 1단 메뉴 HTML은 아래와 같은 형태입니다.

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<meta name="viewport" content="width=device-width">
    		<title>메뉴 - 1단 메뉴 제작</title>
    		<link rel="stylesheet" href="./menu.css">
    	</head>
    	<body>
    		<div class="wrap">
    			<ul class="menu">
    				<li class="menu_item"><a href="#" class="menu_link">메일</a></li>
    				<li class="menu_item active"><a href="#" class="menu_link">카페</a></li>
    				<li class="menu_item"><a href="#" class="menu_link">소프트웨어</a></li>
    				<li class="menu_item"><a href="#" class="menu_link">지식백과</a></li>
    				<li class="menu_item"><a href="#" class="menu_link">영화</a></li>
    			</ul>
    		</div>
    	</body>
    </html>
    ```

    ---

    ### CSS 실습

    동일한 스타일 적용을 위하여 reset CSS와 각 스타일을 추가합니다.

    ```css
    .menu_link {
    	display: block;
    	height: 36px;
    	line-height: 36px;
    	font-size: 12px;
    	color: #333;
    	text-align: center;
    	border: 1px solid #ddd;
    }
    ```

    menu_item에 있는 텍스트를 감싸기 위해 menu_link, 즉 `<a>` 태그를 display: block; 속성을 적용하여 table-cell이 가지고 있는 최대 너비에 맞게 변경합니다.

    각 table-cell의 너비를 균등하게 맞춰주기 위하여 menu에 table-layout:fixed; 속성을 반드시 적용합니다.

    최종적으로 제작하려고 하는 1단 메뉴 CSS 스타일은 아래와 같은 형태입니다.

    ```css
    @charset "UTF-8";

    /* 기본 스타일 */
    body {
    	font-family: '나눔고딕', NanumGothic, Dotum, '돋움', sans-serif;
    }

    body, ul, ol, li, div, a {
    	padding: 0;
    	margin: 0;
    }

    ul, ol {
    	list-style: none;
    }

    a {
    	color: inherit;
    	text-decoration: none;
    }

    /* 스타일 적용 */
    .wrap {
    	min-width: 500px;
    	max-width: 700px;
    	margin: 5px;
    }

    .menu {
    	display: table;
    	table-layout: fixed;
    	width: 100%;
    }

    .menu_item {
    	display: table-cell;
    }

    .menu_link {
    	display: block;
    	height: 36px;
    	font-size: 12px;
    	color: #333;
    	line-height: 36px;
    	text-align: center;
    	border: 1px solid #ddd;
    }

    .menu_item + .menu_item .menu_link {
    	margin-left: -1px;
    }

    .menu_item:hover .menu_link {
    	color: crimson;
    	font-weight: bold;
    }

    .menu_item.active .menu_link {
    	position: relative;
    	color: #fff;
    	font-weight: bold;
    	background-color: gray;
    	border-color: #555;
    }
    ```

    ---

    ### 요약 정리

    **메뉴 최소/최대 너비**

    min-width, max-width를 사용하여 브라우저 너비에 따른 메뉴 너비를 가변적으로 처리할 수 있습니다.

    ```css
    .wrap {
    	max-width: 700px;
    	min-width: 500px;
    }
    ```

    **메뉴 너비 균등**

    display: table; 속성을 사용하여 각 메뉴 셀을 테이블 그리드 UI로 배치할 수 있으며, 각 메뉴 너비를 균등하게 하기 위해 table-layout: fixed; 속성을 사용합니다.

    ```css
    .menu {
    	display: table;
    	table-layout: fixed;
    	width: 100%;
    }

    .menu_item {
    	display: table-cell;
    }
    ```

    **외곽선 겹침 현상 해결**

    각 셀이 가지고 있는 외곽선 겹침 문제는 우측 셀을 좌측으로 1px씩 이동하기 위하여 형제 선택자를 이용해 우측 셀에 margin-left: -1px; 속성을 적용하면 외곽선을 겹치게 만들어 두껍게 나오는 현상을 해결할 수 있습니다.

    ```css
    .menu_item + .menu_item .menu_link {
    	margin-left: -1px;
    }
    ```

    **활성화 메뉴 우측 외곽선 사라짐 현상 해결**

    메뉴 사이에 있는 외곽선들이 좌측, 우측의 외곽선이 모두 노출이 됨으로 외곽선 겹침 현상 해결을 위해 margin-left: -1px; 속성을 적용하였는데, 이렇게 하면 구조상으로 뒤에 나오는 메뉴의 외곽선이 위로 올라옵니다.

    겹쳐졌을 경우에 z-index의 기본값으로는 구조상 뒤에 있는 구조가 z-index 값이 높아 위로 올라오기 때문에, 메뉴가 활성화 됐을때에 구조상 앞에 있는 메뉴는 우측 외곽선이 노출되지 않는 부분이 발생하므로, position: relative; 속성을 사용하여 z-index 값을 새로 생성하게 하여 메뉴 구조의 제일 상단으로 올라오도록 합니다.

    ```css
    .menu_item.active .menu_link {
    	position: relative;
    	color: #fff;
    	font-weight: bold;
    	background-color: gray;
    	border-color: #555;
    }
    ```

- 2단 메뉴 제작