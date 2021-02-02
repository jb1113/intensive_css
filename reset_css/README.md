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