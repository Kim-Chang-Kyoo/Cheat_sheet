# CSS

선택자 속성 값

css minify

style sheet - 브라우저기본 / 사용자정의(인라인 내부 외부)

`<link rel='stylesheet' href=''>`



선택자-태그 요소에 적용하는스타일

태그 vs 요소

클래스선택자 - 같은 태그라도 일부는 다른 스타일을 사용하고 싶어

아이디선택자-단한번만적용

그룹선택자

우선순위중요 - 사용자지정스타일 -> 제작자지정스타일 -> 브라우저기본스타일 / !important->인라인->id->클래스->타입스타일

스타일상속 - 배경색과 배경이미지는 상속x



텍스트표현 = 글꼴스타일(font) + 텍스트스타일(글자 단어 문단)

`body {font-family: 'a a', a, b}`

font-family font-size font-style font-weight

<style>
    @font-face {
        font-family: '',
        src: url() format()
    }
</style>



p {color: green;}

.center {text-align: center;}

p {line-height: 24px;}

text-decoration

text-shadow

text-transform

letter-spacing

word-spacing



list-style-type

list-style-image

list-style-postion



caption-side

border

border-spacing

border-collapse

------------------------------

박스모델 - 블럭 인라인 / 컨텐츠 패딩 보더 마진

컨텐츠 - width height / box-sizing: border-box / box-sizing: content-box / box-shadow:

border-style border-width border-color border-radius

마진중첩



레이아웃

display: block inline inline-block none

float: left right none / clear: left right both

position: static relative absolute fixed / left right top bottom
