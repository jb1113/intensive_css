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
    메뉴 제작시 메뉴 간 영역을 균등하게 하는 방법과 전체 메뉴의 최소/최대 값을 갖는 방법에 대해서 알아보겠습니다.

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

    2단 메뉴는 메인 메뉴와 서브 메뉴로 구성되어 있습니다.
    메인 메뉴 활성화 여부에 따라 서브 메뉴가 노출될 수 있는 방법과 메뉴가 화면 가로 중앙 정렬될 수 있게 하는 방법에 대해서 알아보겠습니다.

    ### 주요 기능

    - 메인, 서브 메뉴를 갖는 2단 가로 메뉴
    - 메인, 서브 메뉴는 가로 중앙 정렬 처리
    - 메인 선택 메뉴는 볼드, 컬러 변경 처리
    - 서브 선택 메뉴는 볼드, 컬러 변경, 하단 라인 추가 처리

    ### 스타일 정보

    - 메인, 서브 메뉴 높이 : 50px
    - 메인 메뉴 기본 폰트 : 20px/#333
    - 메인 메뉴 마우스 오버/활성화 시 폰트 : 20px/bold/SteelBlue
    - 서브 메뉴 기본 폰트 : 17px/#333
    - 서브 메뉴 마우스 오버/활성화 시 폰트 : 17px/bold/SteelBlue, 하단 라인 : 2px/SteelBlue

    ### 주요 태그 및 속성

    **HTML**

    - div
    - ul
    - li
    - a
    - span

    **CSS**

    - position
    - border
    - margin
    - padding
    - background
    - text-align
    - :after
    - :hover

    ---

    ### HTML 실습

    **1. 1단 메뉴와 동일한 메뉴 구성**

    ```html
    <div class="wrap">
    	<!-- 메인 메뉴 -->
    	<ul class="menu">
    		<li class="menu_item">
    			<a href="#" class="menu_link">블로그</a>
    		</li>
    		<li class="menu_item">
    			<a href="#" class="menu_link">카페</a>
    		</li>
    		<li class="menu_item">
    			<a href="#" class="menu_link">지식백과</a>
    		</li>
    		<!-- 메인 메뉴 활성화 클래스 active 추가 -->
    		<li class="menu_item active">
    			<a href="#" class="menu_link">웹툰</a>
    		</li>
    	</ul>
    </div>
    ```

    1단 메뉴와 동일하게 메인 메뉴 태그를 위와 같이 작성합니다.
    각 태그에 스타일 적용을 위한 클래스를 추가하고 메인 메뉴 활성화 처리를 위해 특정 `<li>` 태그 안에 active 클래스를 하나 더 추가합니다.

    **2. 2단 메뉴 구성을 위해 메인 메뉴 안의 서브 메뉴 구성**

    ```html
    <div class="wrap">
    	<!-- 메인 메뉴 -->
    	<ul class="menu">
    		<li class="menu_item">
    			<a href="#" class="menu_link">블로그</a>
    		</li>
    		<li class="menu_item">
    			<a href="#" class="menu_link">카페</a>
    		</li>
    		<li class="menu_item">
    			<a href="#" class="menu_link">지식백과</a>
    		</li>
    		<!-- 메인 메뉴 활성화 클래스 active 추가 -->
    		<li class="menu_item active">
    			<a href="#" class="menu_link">웹툰</a>
    			<!-- 서브 메뉴 -->
    			<ul class="submenu">
    				<li class="submenu_item">
    					<a href="#" class="submenu_link">연도별</a>
    				</li>
    				<!-- 서브 메뉴 활성화 클래스 active 추가 -->
    				<li class="submenu_item active">
    					<a href="#" class="submenu_link">요일별</a>
    				</li>
    				<li class="submenu_item">
    					<a href="#" class="submenu_link">장르별</a>
    				</li>
    				<li class="submenu_item">
    					<a href="#" class="submenu_link">작가별</a>
    				</li>
    				<li class="submenu_item">
    					<a href="#" class="submenu_link">작품별</a>
    				</li>
    			</ul>
    		</li>
    	</ul>
    </div>
    ```

    서브 메뉴는 메인 메뉴인 menu_item 클래스를 가지고 있는 `<li>` 태그 안에 `<ul>` 태그와 `<li>` 태그를 사용하여 서브 메뉴를 추가 합니다.

    서브 메뉴가 메인 메뉴와 구분될 수 있도록 submenu, submenu_item, submenu_link 클래스를 추가합니다.

    마지막으로 서브 메뉴 활성화 처리를 위해 특정 `<li>` 태그 안에 active 클래스를 하나 더 추가합니다.

    **3. 텍스트 너비와 동일한 하단 라인 스타일 적용을 위한 `<span>` 태그 추가**

    ```html
    <div class="wrap">
    	<!-- 메인 메뉴 -->
    	<ul class="menu">
    		<li class="menu_item">
    			<a href="#" class="menu_link">블로그</a>
    		</li>
    		<li class="menu_item">
    			<a href="#" class="menu_link">카페</a>
    		</li>
    		<li class="menu_item">
    			<a href="#" class="menu_link">지식백과</a>
    		</li>
    		<!-- 메인 메뉴 활성화 클래스 active 추가 -->
    		<li class="menu_item active">
    			<a href="#" class="menu_link">웹툰</a>
    			<!-- 서브 메뉴 -->
    			<ul class="submenu">
    				<li class="submenu_item">
    					<a href="#" class="submenu_link"><span>연도별</span></a>
    				</li>
    				<!-- 서브 메뉴 활성화 클래스 active 추가 -->
    				<li class="submenu_item active">
    					<a href="#" class="submenu_link"><span>요일별</span></a>
    				</li>
    				<li class="submenu_item">
    					<a href="#" class="submenu_link"><span>장르별</span></a>
    				</li>
    				<li class="submenu_item">
    					<a href="#" class="submenu_link"><span>작가별</span></a>
    				</li>
    				<li class="submenu_item">
    					<a href="#" class="submenu_link"><span>작품별</span></a>
    				</li>
    			</ul>
    		</li>
    	</ul>
    </div>
    ```

    텍스트를 감싸는 `<span>` 태그는 inline 속성으로 텍스트 너비와 동일하게 영역을 갖게 됩니다.

    **4. 각 메인 메뉴마다 서브 메뉴가 존재하는 경우 추가**

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<meta name="viewport" content="width=device-width">
    		<title>메뉴 - 2단 메뉴 제작</title>
    		<link rel="stylesheet" href="./2-column_menu.css">
    	</head>
    	<body>
    		<div class="wrap">
    			<ul class="menu">
    				<li class="menu_item">
    					<a href="#" class="menu_link">블로그</a>
    				</li>
    				<li class="menu_item">
    					<a href="#" class="menu_link">카페</a>
    				</li>
    				<li class="menu_item">
    					<a href="#" class="menu_link">지식백과</a>
    					<ul class="submenu">
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>건강백과</span></a>
    						</li>
    						<li class="submenu_item active">
    							<a href="#" class="submenu_link"><span>동물백과</span></a>
    						</li>
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>식물백과</span></a>
    						</li>
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>음식백과</span></a>
    						</li>
    					</ul>
    				</li>
    				<li class="menu_item active">
    					<a href="#" class="menu_link">웹툰</a>
    					<ul class="submenu">
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>연도별</span></a>
    						</li>
    						<li class="submenu_item active">
    							<a href="#" class="submenu_link"><span>요일별</span></a>
    						</li>
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>장르별</span></a>
    						</li>
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>작가별</span></a>
    						</li>
    						<li class="submenu_item">
    							<a href="#" class="submenu_link"><span>작품별</span></a>
    						</li>
    					</ul>
    				</li>
    			</ul>
    		</div>
    	</body>
    </html>
    ```

    최종적으로 제작하려는 2단 메뉴 구성은 위와 같습니다.

    ---

    ### CSS 실습

    메인 메뉴는 1단 메뉴와 동일하게 요구 사항에 맞게 CSS 속성을 추가합니다.
    메뉴 가로 중앙 정렬을 위해 margin: 0 auto; 속성을 추가합니다.
    inline-block 요소를 중앙 정렬 시키기 위해서 text-align: center; 속성을 추가하면 중앙 정렬 됩니다.

    ```css
    .menu {
    	width: 700px;
    	margin: 20px auto 0;
    	text-align: center;
    }

    .menu_item {
    	display: inline-block;
    }

    .menu_link {
    	display: block;
    	padding: 13px 20px;
    	line-height: 24px;
    	font-size: 20px;
    	color: #333;
    	font-weight: bold;
    }

    ```

    메인 메뉴의 마우스 오버시, 활성화 된 메뉴를 표시하기 위한 스타일을 추가합니다.

    ```css
    .menu_item:hover .menu_link,
    .menu_item.active .menu_link {
    	color: steelblue;
    }
    ```

    서브메뉴 스타일이 적용되어 있지 않은 상태에서 HTML만 추가할 경우 메인메뉴가 깨져 보입니다.
    때문에 서브메뉴 스타일을 추가합니다.

    ```css
    .submenu {
    	position: absolute;
    	left: 0;
    	width: 100%;
    	min-width: 700px;
    	border-top: 1px solid #eee;
    	border-bottom: 1px solid #eee;
    }
    ```

    이렇게 CSS 스타일을 주게되면 메인 메뉴 밑으로 서브메뉴가 세로로 정렬이 됩니다.
    주의해야 할 점은 submenu의 position: absolute; 속성을 주어 메인 메뉴와 동일하게 전체 영역에서 가로 중앙 정렬 되도록 잡아야 합니다

    만약 submenu에 position: absolute; 속성이 적용된 상태에서
    상위 부모인 menu_item에 position: relative; 속성을 주게 되면 부모의 너비와 높이, 위치 값들을 상속받기 때문에 브라우저 전체 가로 너비에 중앙 정렬되지 않고, 부모를 기준으로 정렬되기 때문에 원하는 형태가 되지 않습니다.

    ```css
    .submenu_item {
    	display: inline-block;
    }

    .submenu_link {
    	display: block;
    	padding: 10px 35px;
    	line-height: 20px;
    	font-size: 17px;
    	color: #333;
    }
    ```

    submenu_item에 display: inline-block; 속성을 주어 가로 배치가 되도록 합니다.

    ```css
    .submenu {
    	min-widht: 700px;
    }
    ```

    submenu에 min-widht: 700px; 값을 넣은 이유는 이 부분을 제거하게 될 경우 submenu가 갖는 고정 너비가 정해져 있지 않기 때문에, 브라우저 창이 줄어들었을 때 
    부모가 전체 100%인 너비를 가지므로 submenu_item 값들이 밑으로 떨어지는 현상이 발생합니다.

    ```css
    .submenu_item:hover .submenu_link,
    .submenu_item.active .submenu_link {
    	font-weight: bold;
    	color: steelblue;
    }
    ```

    메인 메뉴와 마찬가지로 서브 메뉴에도 마우스 오버시와 활성화 된 메뉴를 표시하기 위한 스타일을 추가합니다.

    ```css
    /* 유지 보수 측면에서 좋지 않은 방법 */
    /* 하단 라인의 너비가 submenu_link 너비와 동일하며, 텍스트 너비와 같지 않음 */
    .submenu_link {
    	position: relative;
    }

    .submenu_item:hover .submenu_link:after {
    	position: absolute;
    	content: '';
    	right: 0;
    	bottom: 0;
    	left: 0;
    	border-bottom: 2px solid steelblue;
    }
    ```

    마지막으로 서브 메뉴 마우스 오버, 활성화 시에 하단 라인을 넣어주기 위해 위와 같이 CSS 스타일을 추가합니다.

    하지만 이 경우 하단 라인이 텍스트 너비와 다르게 submenu_link 사이즈와 동일한 너비 값으로 라인이 그려집니다.

    이는 position: absolute; 속성과 right: 0; left: 0; 속성으로 잡혀있기 때문에 submenu_link 사이즈와 동일한 형태가 됩니다.

    텍스트 너비와 동일하게 적용하기 위해서는 width 속성을 이용하여 잡아줄 수 있으나, 이는 텍스트 길이가 길어지는 경우 메뉴도 따라서 너비가 넓어지므로, width 값을 항상 텍스트 사이즈에 맞게 조절해 주어야 하기 때문에, 유지 보수 측면에서 좋지 않습니다.

    또한 스타일 관리가 메뉴 별로 각각에 적용이 되어야 하는 부분도 있기 때문에 이 방법 대신 `<span>` 태그를 이용하여 텍스트 너비에 맞게 변경하도록 합니다.

    ```css
    /* 텍스트 너비에 맞는 라인을 넣기 위한 방법 */
    .submenu_link span {
    	position: relative;
    }

    .submenu_item:hover span:after, 
    .submenu_item.active span:after {
    	position: absolute;
    	content: '';
    	right: 0;
    	bottom: -10px;
    	left: 0;
    	border-bottom: 2px solid steelblue;
    }
    ```

    HTML에 `<span>` 태그를 추가하여 `<span>` 에 스타일을 적용하면, 텍스트 너비에 따라 보더의 길이가 변경되는 것을 확인할 수 있습니다.

    마지막으로 각 메인 메뉴마다 서브 메뉴가 존재할 경우 활성화 된 메인 메뉴의 서브 메뉴만 노출되도록 해야합니다.

    하지만 지금은 다른 메인 메뉴에 서브 메뉴를 추가할 경우 서브 메뉴가 겹쳐져 보이는 것을 확인할 수 있습니다.

    ```css
    .submenu {
    	display: none;
    	...
    }
    ```

    기본적으로 서브 메뉴 같은 경우에는 display: none; 속성을 사용하여 처음부터 보이지 않도록 설정을 해줍니다.

    ```css
    .menu_item.active .submenu {
    	display: block;
    }
    ```

    그런 다음 메인 메뉴의 menu_item에 active가 있을 경우에만 서브 메뉴를 노출하도록 스타일을 추가합니다.

    이렇게 되면 서브 메뉴가 없는 메인 메뉴의 경우에는 서브 메뉴가 노출되지 않는 것을 확인할 수 있습니다.

    최종적으로 제작하려고 하는 2단 메뉴 CSS 스타일은 아래와 같은 형태입니다.

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
    .menu {
    	width: 700px;
    	margin: 20px auto 0;
    	text-align: center;
    }

    .menu_item {
    	display: inline-block;
    }

    .menu_link {
    	display: block;
    	padding: 13px 20px;
    	line-height: 24px;
    	font-size: 20px;
    	color: #333;
    	font-weight: bold;
    }

    .menu_item:hover .menu_link,
    .menu_item.active .menu_link {
    	color: steelblue;
    }

    .menu_item.active .submenu {
    	display: block;
    }

    .submenu {
    	display: none;
    	position: absolute;
    	left: 0;
    	width: 100%;
    	min-width: 700px;
    	border-top: 1px solid #eee;
    	border-bottom: 1px solid #eee;
    }

    .submenu_item {
    	display: inline-block;
    }

    .submenu_link {
    	display: block;
    	padding: 10px 35px;
    	line-height: 20px;
    	font-size: 17px;
    	color: #333;
    }

    .submenu_item:hover .submenu_link,
    .submenu_item.active .submenu_link {
    	font-weight: bold;
    	color: steelblue;
    }

    .submenu_link span {
    	position: relative;
    }

    .submenu_item:hover span:after,
    .submenu_item.active span:after {
    	position: absolute;
    	content: '';
    	right: 0;
    	bottom: -10px;
    	left: 0;
    	border-bottom: 2px solid steelblue;
    }
    ```

    ---

    ### 요약 정리

    **메뉴 가로 중앙 정렬**

    가로 중앙 정렬을 위해서 고정 너비 값을 가지고 있는 block 요소에 margin: 0 auto; 속성을 주고, inline-block 요소의 경우에는 text-align: center; 속성을 사용하여 중앙 정렬이 가능합니다.

    ```css
    .menu {
    	width: 700px;
    	margin: 20px auto 0;
    	text-align: center;
    }

    .menu_item {
    	display: inline-block;
    }
    ```

    **서브 메뉴 보이기/감추기**

    메인 메뉴가 비활성화인 경우에 서브 메뉴는 노출되지 않아야 하므로, submenu는 display: none; 속성을 기본값으로 가지고 있어야 합니다.

    만약 메인 메뉴가 활성화될 경우에는 해당 메인 메뉴 menu_tem에 active 클래스를 추가하여 submenu가 display: block; 속성으로 변경될 수 있도록 처리합니다.

    ```css
    .menu_item.active .submenu {
    	display: block;
    }

    .submenu {
    	display: none;
    }
    ```

    **서브 메뉴 하단 라인**

    서브 메뉴 마우스 오버 또는 활성화 시 노출되는 하단 라인을 메뉴명 텍스트 너비와 동일한 라인을 생성하기 위해 메뉴명을 감싸는 inline 속성의 `<span>` 태그를 추가하고 :after 가상 요소를 사용하여 border-bottom 속성을 선언할 경우, 향후 메뉴명 텍스트가 늘어나더라도 동일한 너비의 하단 라인을 가질 수 있습니다.

    ```css
    .submenu_link span {
    	position: relative;
    }

    .submenu_item:hover span:after, 
    .submenu_item.active span:after {
    	position: absolute;
    	content: '';
    	right: 0;
    	bottom: -10px;
    	left: 0;
    	border-bottom: 2px solid steelblue;
    }
    ```