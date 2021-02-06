# IR 기법

- IR 기법 소개

    ### IR이란?

    - Image Replacement
    - 이미지를 볼 수 없는 사용자에게 적절한 대체 텍스트를 제공하는 것

    `<img>` 태그에는 반드시 alt 속성을 사용해서 대체 텍스트를 입력해 주어야 합니다.

    하지만, 만약 `<img>` 태그의 alt 속성 값으로 표현하기에 대체 텍스트가 너무 길거나, CSS background 속성을 사용하여 처리한 의미 있는 이미지일 경우, 마크업으로 대체 텍스트를 제공합니다.

- 요소 숨김 처리

    CSS로 대체 텍스트를 화면에서 숨기는 방법은 여러가지가 있습니다.
    대체 텍스트는 그 의미가 잘 전달이 되도록 시멘틱하게 마크업 해야 하고, 화면에서 보이지 않도록 CSS로 숨깁니다.
    이때 중요한 것은 스크린 리더기가 읽을 수 있도록 처리해야 한다는 점입니다.

    ### 요소를 화면에서 숨기는 방법

    ### BAD

    스크린 리더가 인식하지 못하기 때문에 다음 중 어느 속성이라도 사용하지 말아야 합니다.

    ```css
    /* opacity(투명도)를 0으로 주는 것과 동일하게 화면에서 사라지지만, 스크린 리더가 인식 안함 */
    visibility: hidden;

    /* 요소가 아예 없는 것으로 인식 */
    display: none;

    /* 요소의 사이즈를 0으로 만들면 스크린 리더 인식 안함 */
    width: 0;
    height: 0;
    font-size: 0;
    line-height: 0;
    ```

    ### SO SO

    스크린 리더가 인식하지만 레이아웃이나 성능 등에 이슈가 발생할 수 있기 때문에 상황에 맞게 사용하여야 합니다.

    ```css
    /* 투명해진것 뿐, 위치를 그대로 잡고있기 때문에 요소가 전체 레이아웃에 영향을 주지 말하야하는 곳에서 단독으로 사용하기 어려움 */
    opacity: 0;

    /* 요소 안의 텍스트만 옮기는 것이기 때문에 전체 레이어의 크기가 지나치게 크게 잡힘 (성능 이슈) */
    text-indent: -9999px;

    /* position값이 default인 static이 아닌 다른 속성값이 추가되어야 함 (성능 이슈) */
    z-index: -1;
    ```

    참고로 text-indent 값을 100%로 처리함으로서 요소의 크기만큼만 텍스트를 밀어내도록 하여 성능 이슈는 피할 수 있습니다.

    그러나 여러 줄로 된 경우에는 text-indent가 첫 줄, 첫 단락의 시작만 밀어주기 때문에 아래의 문장들은 그대로 보입니다.

    ### BEST

    스크린 리더가 인식하면서 레이아웃이나 성능 등에 영향을 미치지 않는 방법으로 아래 속성들을 조합해서 사용합니다.

    ```html
    <span class="blind">숨김 텍스트</span>
    ```

    ```css
    .blind {
    	/* 요소를 띄워서 주변 레이아웃에 영향을 끼치지 않도록 */
    	position: absolute;

    	/* 크기를 0이 아닌 1로 주어 스크린 리더가 읽을 수 있도록 */
    	width: 1px;
    	height: 1px;

    	/* 눈에 보이는 부분을 제거 */
    	margin: -1px;
    	clip: rect(0 0 0 0);
    	overflow: hidden;
    }
    ```

    HTML 전체적으로 많이 쓰이기 때문에 blind라는 하나의 공통된 클래스를 생성하여 숨김이 필요한 요소에 클래스를 추가하여 처리하는 것이 효율적입니다.

    ### clip 속성 (default=auto)

    좌표 (0, 0)을 기준으로해서 절대값 네개의 좌표로 지정한 직사각형 모양대로 요소를 잘라내는 속성입니다. (mask 효과)

    ```css
    clip: rect(top right bottom left);
    ```

    position 속성 값이 absolute 혹은 fixed인 요소여야 하고, 만약 overflow 속성 값이 visible일 경우에는 적용되지 않습니다.

    ---

    ### 참고자료

    [clip](https://developer.mozilla.org/en-US/docs/Web/CSS/clip)

    [CSS clip property](https://www.w3schools.com/cssref/pr_pos_clip.asp)

- 프로모션 페이지 제작

    일정 기간 노출되고 사라지는 프로모션 페이지는 전체 화면을 이미지로 처리한 경우가 많습니다.

    ### HTML 실습 코드

    모든 텍스트를 화면에서 숨겨야 하기 때문에 복잡하게 `<div>` 태그로 감싸거나 하지 않고, 우선 시멘틱하게 마크업을 하는데 집중합니다.

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>프로모션 페이지 제작</title>
    		<link rel="stylesheet" type="text/css" href="promotion.css">
    	</head>
    	<body>
    		<!-- <img src="./promotion.png" width="1020" height"650" alt=""> -->
    		<div class="wrap">
    			<h1 class="blind">알면 알수록 즐거운 네이버쇼핑 윈도시리즈</h1>
    			<p class="blind"> 쇼핑 즐기고 10%적립 혜택도 받으세요!</p>

    			<ol>
    				<li>
    					<strong class="blind">100 포인트만 있으면!</strong>
    					<p class="blind">포인트 100원 이상 보유 시 신청 가능(신청 확인용으로 차감되지 않습니다.)</p>
    					<a href="#" class="link_point"><span class="blind">포인트가 부족하다면?</span></a>
    				</li>
    				<li class="blind">
    					<strong class="blind">쇼핑윈도 시리즈 즐기고~</strong>
    					<p class="blind">11.15 ~ 11.30 누적 1만원 이상 구매</p>
    				</li>
    				<li class="blind">
    					<strong class="blind">구매금액 10%적립!</strong>
    					<p class="blind">최대 1만원 네이버페이 포인트 적립</p>
    				</li>
    			</ol>

    			<a href="#" class="link_join"><span class="blind">신청하기</span></a>

    			<h2 class="blind">유의사항</h2>
    			<ul class="blind">
    				<li>BIG3 쇼핑 이벤트와 중복으로 신청하실 수 없습니다.</li>
    				<li>내부 사정에 따라 공지 없이 신청 종료될 수 있습니다.</li>
    			</ul>
    		</div>
    	</body>
    </html>
    ```

    모든 요소를 감싸고 있는 `<div class="wrap">`을 추가하여 전체 컨텐츠 영역에 이미지를 적용합니다.

    텍스트를 한꺼번에 숨기기 위해서는 부모 요소에 blind 클래스를 추가하면 됩니다.
    하지만 이미지 안에서도 `<a>` 태그의 링크는 동작해야 하기 때문에 `<a>` 태그가 있는지 반드시 확인해야 합니다.

    `<a>` 태그에는 이미지 상의 버튼과 동일한 영역과 위치를 잡을 수 있도록 스타일을 적용하기 위해서 link_point와 link_join이라는 클래스를 각각 추가합니다.
    버튼의 텍스트는 다른 요소들과 마찬가지로 숨기기 위해서 `<span>` 태그로 한번 더 감싼 후 blind 클래스를 추가합니다.

    ### CSS 실습 코드

    ```css
    @charset "UTF-8";

    /* reset CSS */
    ol {
    	list-style: none;
    }

    body, ol {
    	margin: 0;
    	padding: 0;
    }

    .wrap {
    	position: relative;
    	background: url(./promotion.png) no-repeat 0 0;
    	width: 1020px;
    	height: 650px;
    	margin: 0 auto;
    }

    .blind {
    	position: absolute;
    	clip: rect(0 0 0 0);
    	width: 1px;
    	height: 1px;
    	margin: -1px;
    	overflow: hidden;
    }

    .link_point {
    	position: absolute;
    	left: 128px;
    	bottom: 195px;
    	width: 94px;
    	height: 14px;
    }

    .link_join {
    	position: absolute;
    	left: 312px;
    	bottom: 114px;
    	width: 270px;
    	height: 56px;
    }
    ```

    `<div class="wrap">`에 배경 이미지를 넣고, 컨텐츠 영역을 이미지 크기만큼 지정해 줍니다.
    margin: 0 auto;을 사용하여 화면 상 가운데에 위치하도록 정렬합니다.

    CSS 리셋에서 해보았던 대로 기본 스타일을 초기화하여 불필요한 여백이나 스타일이 노출되지 않도록 합니다.

    blind 클래스에 텍스트를 숨기기 위한 속성들도 모두 추가합니다.

    마지막으로 이미지와 동일한 영역과 위치에 `<a>` 태그 링크가 올 수 있도록 스타일을 추가합니다.

- IR 기법 요약 정리

    ### 언제 사용할까?

    - `<img>` 태그 사용 시, 대체 텍스트가 너무 긴 경우
    - background-image 속성으로 처리한 의미 있는 이미지

    ### 어떻게 사용할까?

    - 스크린 리더가 제대로 읽을 수 있도록 시멘틱 마크업 유지
    - 스크린 리더가 인식 가능하고, 레이아웃과 성능에 영향이 없는 CSS 속성 사용
    - CSS에서 모든 요소를 선택해서 속성을 하나하나 넣어주기 보다는 특정 속성의 클래스를 만들어 필요한 요소에 해당 클래스를 추가