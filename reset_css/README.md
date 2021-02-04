# CSS 리셋

- CSS 리셋 소개

    어떤 브라우저에서든 사용자들이 동일한 경험을 할 수 있도록 크로스브라우징 원칙을 지켜서 코딩해야 합니다.
    그 첫 단계가 바로 CSS 리셋입니다.
    아무 스타일을 적용하지 않은 HTML 문서가 화면에 어떻게 렌더링이 되는지 확인해 보고, CSS 리셋의 필요성을 직접 느껴봅니다.

    ### 크로스 브라우징이란?

    크로스 브라우징이란 어떤 웹 브라우저를 써도 화면이 똑같이 나오고 브라우저에 따라 입력과 사용에 문제가 생기지 않도록 하는 것을 말합니다.
    브라우저마다 같은 코드여도 해석하는 방식이 다르기 때문에 브라우저가 렌더링을 하는 기본 스타일에도 조금씩 차이가 있습니다.

    예를 들어, 네이버의 reset CSS들은 아래와 같습니다.

    ```css
    body,button,dd,dl,dt,fieldset,form,h1,h2,h3,h4,h5,h6,input,legend,li,ol,p,select,table,td,textarea,th,ul {
        margin: 0;
        padding: 0
    }

    body,button,input,select,table,textarea {
        font-size: 12px;
        line-height: 16px;
        color: #202020;
        font-family: -apple-system,BlinkMacSystemFont,"Malgun Gothic","맑은 고딕",helvetica,"Apple SD Gothic Neo",sans-serif
    }

    h1,h2,h3,h4,h5,h6 {
        font-size: inherit;
        line-height: inherit
    }

    textarea {
        -webkit-backface-visibility: hidden;
        backface-visibility: hidden;
        background-color: transparent;
        border: 0;
        word-break: keep-all;
        word-wrap: break-word
    }

    button,input {
        -webkit-border-radius: 0;
        border-radius: 0;
        border: 0
    }

    button {
        background-color: transparent
    }

    fieldset,img {
        border: 0
    }

    img {
        vertical-align: top
    }

    ol,ul {
        list-style: none
    }

    address,em {
        font-style: normal
    }

    a {
        color: inherit;
        text-decoration: none
    }

    a:hover {
        text-decoration: underline
    }

    iframe {
        overflow: hidden;
        margin: 0;
        border: 0;
        padding: 0;
        vertical-align: top
    }

    mark {
        background-color: transparent
    }

    i {
        font-style: normal
    }
    ```

    CSS 파일의 상단에 태그들에 대한 스타일을 적용한 부분까지가 reset CSS라고 볼 수 있습니다.
    모든 CSS 스타일을 삭제했을 때보다 모든 브라우저에서 reset CSS를 적용한 후의 화면이 비교적 유사하게, 동일하게 렌더링되고 있는 것을 확인할 수 있습니다.

    이렇게 모든 브라우저에서 동일한 화면을 볼 수 있도록 기본 값을 초기화하는 리셋 스타일이 모든 CSS 상단에 들어가야 합니다.

    그럼 어떤 reset CSS를 사용할까요?
    [https://cssreset.com](https://cssreset.com)이라는 페이지를 들어가보면 현재 가장 많이 사용되고 있는 reset CSS를 몇 가지 확인할 수 있습니다.

    ### reset CSS

    리셋 CSS는 정해진 형식이나 코드가 없습니다.
    사용하지도 않는 태그들을 초기화 할 필요도 없으며 프로젝트 성격에 맞추어 작성해주면 됩니다.
    모든 브라우저에서 동일한 뷰를 보여주기 위해 기본값을 초기화한다는 점만 기억하면 됩니다.

    ---

    ### 참고자료

    [CSS Reset - 2019's most common CSS Resets to copy/paste, with documentation / tutorials](https://cssreset.com/)

    [Eric Meyer's "Reset CSS" 2.0](https://cssdeck.com/blog/scripts/eric-meyer-reset-css/)

- reset.css 제작

    특정 UI를 만드는 것이 아니라 태그 별로 스타일을 확인하고 재정의 합니다.
    때문에 많이 사용하는 태그들 위주로 실습을 진행합니다.

    ### 주요 기능

    주요 태그들의 기본 스타일을 확인하고, 직접 reset CSS를 작성한다.

    ### 주요 태그 및 속성

    - HTML
    헤딩, 리스트, 폼, 테이블 등 주요 태그
    - CSS
    margin, padding, border, font-style, border-collapse, text-decoration, list-style

    ### body, h1, h2, h3, h4, h5, h6

    ```html
    <h1>h1</h1>
    <h2>h2</h2>
    <h3>h3</h3>
    <h4>h4</h4>
    <h5>h5</h5>
    <h6>h6</h6>
    ```

    ```css
    body,
    h1, h2, h3, h4, h5, h6 {
    	margin: 0;
    }
    ```

    헤딩 태그에 font-size와 font-weight도 기본 값을 가지고 있지만 초기화 하지 않고, margin만 제거 했습니다.
    프로젝트 성격에 따라서 초기화 해주어도 무관합니다.

    ### ul, ol, dl

    ```html
    <ul>
    	<li>ul 리스트의 li</li>
    	<li>ul 리스트의 li
    		<ul>
    			<li>ul 리스트의 li</li>
    			<li>ul 리스트의 li</li>
    		</ul>
    	</li>
    	<li>ul 리스트의 li</li>
    </ul>

    <ol>
    	<li>ol 리스트의 li</li>
    	<li>ol 리스트의 li</li>
    	<li>ol 리스트의 li</li>
    </ol>

    <dl>
    	<dt>dl 리스트의 dt</dt>
    	<dd>dl 리스트의 dd</dd>
    	<dd>dl 리스트의 dd</dd>
    </dl>
    ```

    ```css
    ul, ol, dl, dd {
    	margin: 0;
    	padding: 0;
    }

    ul, ol {
    	list-style: none;
    }
    ```

    ### list-style

    display 속성 값이 list-item인 요소의 기본 스타일이며 부모의 값을 상속받기 때문에 모든 `<li>` 태그에 적용 되도록 `<ol>` 태그 혹은 `<ul>` 태그에 값을 주는게 일반적인 방법입니다.
    브라우저에 기본값으로는 list-style-type 속성이 적용되어 있으며, 축약형으로 초기화 해줍니다.

    ### table

    ```html
    <table>
    	<caption>caption</caption>
    	<thead>
    		<tr>
    			<th>th</th>
    			<th>th</th>
    			<th>th</th>
    			<th>th</th>
    		</tr>
    	</htead>
    	<tbody>
    		<tr>
    			<th>th</th>
    			<th>th</th>
    			<td>td</td>
    			<td>td</td>
    		</tr>
    		<tr>
    			<th>th</th>
    			<th>th</th>
    			<td>td</td>
    			<td>td</td>
    		</tr>
    	</tbody>
    </table>
    ```

    ```css
    table {
    	border-collapse: collapse;
    }
    ```

    table에 임의로 border 속성값을 넣어서 렌더링 되는 모습을 보면, border-collapse가 seperate로 되어있기 때문에 셀 사이가 떨어진 채로 렌더링 됩니다.
    이런 식으로 테이블이 디자인 되는 경우가 거의 없기 때문에 border-collapse 속성의 값을 collapse로 변경해 줍니다.

    `<th>` 태그의 font-weight와 vertical-align: middle 기본 정렬 속성은 테이블의 제목에 해당하기 때문에 그대로 유지하였습니다.

    ### p, em, strong

    ```html
    <p>모든 브라우저에서 <em>동일한</em> 화면을 볼 수 있도록 기본값을 <strong>초기화</strong>합니다.</p>
    ```

    ```css
    p {
    	margin: 0;
    	padding: 0;
    }

    em {
    	font-style: normal;
    }
    ```

    `<p>` 태그는 여백을 제거하고, 텍스트가 기울어져 있는 `<em>` 태그의 font-style: italic;을 normal로 초기화합니다.
    `<strong>` 태그는 헤딩태그와 테이블의 `<th>` 태그와 같이 font-weight는 그대로 유지합니다.

    ### a

    ```html
    <a href="#">자세히 보기</a>
    ```

    ```css
    a {
    	text-decoration: none;
    }

    a:hover {
    	font-weight: bold;
    	text-decoration: underline;
    }
    ```

    `<a>` 태그는 상태값을 확인해 보아야 합니다.
    `<a>` 태그에 대한 스타일은 보다 다양하게 초기화할 수 있습니다.
    컬러, 마우스 커서 모양 등 프로젝트에 맞추어 변경해 줍니다.

    ### img

    ```html
    <img src="http://placehold.it/500x250" alt="dummy">

    <div style="border: 1px solid #ccc">
    	<img src="http://placehold.it/500x250" alt="dummy">
    </div>
    ```

    ```css
    img {
    	vertical-align: top;
    }
    ```

    `<img>` 태그를 `<div>`로 감싸주면 아무런 margin, padding 속성이 없는데도 이미지와 `<div>`태그 사이에 공간이 생기는 것을 border 속성을 통해서 확인할 수 있습니다.

    이유는 이미지가 텍스트와 같은 인라인 요소이기 때문에 나타나는 현상으로 margin, padding을 0 값으로 변경하여도 공간이 메꾸어 지지 않습니다.

    이를 없애는 방법으로는 vertical-align: top; 을 속성으로 주어 처리하거나
    display: block; 속성을 추가하여 block 요소로 변경을 해주는 방법밖엔 없습니다.

    그러나 원래 인라인 요소이기 때문에 원래 성격을 유지하면서 여백만 제거하기 위해 vertical-align: top; 속성을 이용해 여백을 제거해 주겠습니다.

    ### form

    ```html
    <form>
    	<fieldset>
    		<legend>form요소</legend>
    		<input type="text" title="검색어 입력" value="input text">
    		<button type="submit">submit</button>
    		<textarea>textarea</textarea>
    		<label for="checkbox">checkbox</label><input type="checkbox" id="checkbox">
    		<select>
    			<option>option 1</option>
    			<option>option 2</option>
    			<option>option 3</option>
    		</select>
    	</fieldset>
    <form>
    ```

    ```css
    fieldset, legend {
    	margin: 0;
    	padding: 0;
    	border: 0;
    }

    body, input, button, textarea, select {
    	font-size: 14px;
    	font-family: Dotum, '돋움', Helvetica, "Apple SD Gothic Neo", sans-serif;
    }
    ```

    form 관련 태그들은 브라우저 기본 스타일이 가장 많이 적용되어 있는 요소이고 브라우저마다 모양이 모두 다릅니다.
    그렇기 때문에 모두 동일하게 보이도록 커스텀 하는 일 자체가 매우 까다로운 작업이라서 실무에서는 디자인 요소로 처리하거나 기본 스타일대로 노출하는 경우가 많습니다.

    따라서 폰트 관련 속성만 초기화 하였으며 전체적으로 통일해주기 위해서 헤딩 태그, `<body>` 태그에도 적용하였습니다.

    ### 요약

    대부분의 프로젝트에서 margin과 padding 즉, 여백은 0으로 초기화 해주는 것이 디자인대로 CSS를 적용하기 편합니다.
    그 외 속성들은 프로젝트에서 공통으로 초기화할 필요가 있는 부분만 추가해주면 됩니다.

    스타일이 태그별로 모두 들어가 있기 때문에, 부모 요소가 아니라 태그 자체에 직접 스타일을 입력해주어야 합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>reset CSS</title>
    		<link rel="stylesheet" type="text/css" href="reset.css">
    	</head>
    	<body>
    		<h1>h1</h1>
    		<h2>h2</h2> <h3>h3</h3>
    		<h4>h4</h4>
    		<h5>h5</h5>
    		<h6>h6</h6>

    		<hr>

    		<ul>
    			<li>ul 리스트의 li</li>
    			<li>ul 리스트의 li
    				<ul>
    					<li>ul 리스트의 li</li>
    					<li>ul 리스트의 li</li>
    				</ul>
    			</li>
    			<li>ul 리스트의 li</li>
    		</ul>

    		<ol>
    			<li>ol 리스트의 li</li>
    			<li>ol 리스트의 li</li>
    			<li>ol 리스트의 li</li>
    		</ol>

    		<dl>
    			<dt>dl 리스트의 dt</dt>
    			<dd>dl 리스트의 dd</dd>
    			<dd>dl 리스트의 dd</dd>
    		</dl>

    		<hr>

    		<table>
    			<caption>caption</caption>
    			<thead>
    				<tr>
    					<th>th</th>
    					<th>th</th>
    					<th>th</th>
    					<th>th</th>
    				</tr>
    			</htead>
    			<tbody>
    				<tr>
    					<th>th</th>
    					<th>th</th>
    					<td>td</td>
    					<td>td</td>
    				</tr>
    				<tr>
    					<th>th</th>
    					<th>th</th>
    					<td>td</td>
    					<td>td</td>
    				</tr>
    			</tbody>
    		</table>

    		<hr>

    		<p>모든 브라우저에서 <em>동일한</em> 화면을 볼 수 있도록 기본값을 <strong>초기화</strong>합니다.</p>

    		<hr>

    		<a href="#">자세히 보기</a>

    		<hr>

    		<img src="http://placehold.it/200x100" alt="dummy">

    		<div style="border: 1px solid #ccc">
    			<img src="http://placehold.it/200x100" alt="dummy">
    		</div>

    		<hr>

    		<form>
    			<fieldset>
    				<legend>form요소</legend>
    				<input type="text" title="검색어 입력" value="input text">
    				<button type="submit">submit</button>
    				<textarea>textarea</textarea>
    				<label for="checkbox">checkbox</label><input type="checkbox" id="checkbox">
    				<select>
    					<option>option 1</option>
    					<option>option 2</option>
    					<option>option 3</option>
    				</select>
    			</fieldset>
    		<form>
    	</body>
    </html>
    ```

    ```css
    @charset "UTf-8";

    /* reset */
    body,
    h1, h2, h3, h4, h5, h6,
    ul, ol, dl, dd,
    p,
    fieldset, legend {
    	margin: 0;
    	padding: 0;
    }

    body, input, textarea, select, button {
    	font-size: 14px;
    	font-family: Dotum, '돋움', Helvetica, "Apple SD Gothic Neo", sans-serif;
    }

    ul, ol {
    	line-style: none;
    }

    table {
    	border-collapse: collapse;
    }

    em {
    	font-style: normal;
    }

    a {
    	text-decoration: none;
    }

    a:hover {
    	font-weight: bold;
    	text-decoration: underline;
    }

    img {
    	vertical-align: top;
    }

    fieldset {
    	border: 0;
    }
    ```

    ---

    ### 참고자료

    [list-style](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)

    [border-collapse](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)

- CSS 리셋 요약 정리
    - 브라우저마다 태그를 렌더링하는 기본 스타일이 다르다.
    - 모든 브라우저에서 동일한 화면을 볼 수 있도록 기본값을 초기화한다.
    - reset CSS는 각 프로젝트에 맞춰서 사용한다.