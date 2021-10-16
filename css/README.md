# CSS [작성중]

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



background 관련, 그라데이션



css선택자

-연결선택자: 하위선택자 자식선택자 인접형제 형제

-속성선택자

-가상클래스

-가상요소



transform

transition-애니메이션효과

@keyframes



뷰포트

미디어쿼리

플렉스박스 레이아웃 vs CSS그리드 레이아웃

--------------------------------------------------------

많이하는실수

부모의 높이가 있어야 세로 가운데 정렬할 수 있다

크기가 있어야 정렬할 수 있따



css선택자

display: block;
display: inline-block;
display: inline;

inline vs block
텍스트
너비x
높이x

-------------------------------------------

flexbox 부모에적용

.father {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center; // 부모가차지하는높이에서가운데정렬
			// stretch는 높이가 없어야 적용된다
	flex-wrap: nowrap; // 한줄에유지
	align-content: center;
}

.child:nth-child(2) {
	align-self: center;
	order: 1; //클수록 뒤로 간다 zerobase
	flex-shrink: 2; // 2배로줄어든다
	flex-basis: 300px; //기본사이즈가300이고 늘리거나줄이면바뀐다
}

-------------------------------------------------------------

align-content: center; // 윗줄과 아랫줄사이간격 조절하기
grid - flex의단점보완
dsplay: grid;
grid-template-areas: ;



.father {
	display: grid;
	grid-template-columns: 20px 20px 20px;
	grid-templa-rows: 20px, 20px, 20px; // 행크기없으면 자식의 font-size가 행크기다
	column-gap: 10px;
	row-gap: 10px;
}

.grid {
	display: grid;
	grid-template-columns: 20px 20px 20px 20px; // repeat(4, 20px);
	grid-template-rows: 20px 20px 20px 20px; // auto 20px;
	grid-template-areas:
	"header header header header"
	"content content content nav"
	"content content content nav"
	"footer footer footer footer"; //자식에 grid-area: header;
}

.header {
	grid-column-start: 1;
	grid-column-end: 5; // 라인 단위
}

.header {
	grid-column: 1 / -1;
}

.header {
	grid-column: span 4; // 셀단위
}









line naming

.grid {
	height: 50vh;
	display: grid;
	grid-template-columns: 1fr 1fr 1fr 1fr; // fraction단위
}

.grid {
	display: grid;
	grid-template-areas:
	"header header header header" 1fr
	"content content content nav" 2fr
	[footer-start] "footer footer footer footer" 1fr [footer-end] / 1fr 1fr 1fr 1fr;
}

justify-items: start;
align-items: start;
place-items: start start;

justify-content: start;
align-content: start;
place-content: start start;

justify-self: center;
align-self: start;
place-self: start;





.grid {
	grid-template-rows: repeat(4, 100px);
	grid-template-columns: repeat(4, 100px);
	grid-auto-rows: 100px;
	grid-auto-columns: 100px;
	grid-auto-flow: column; // 아래로 자동생성이아니라, 옆으로 자동생성
	grid-auto-columns: 100px;
}

.grid {
	grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
	grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); // stretch 빈공간을만들지않는다
}

.grid {
	grid-template-columns: max-content min-content;
	grid-template-columns: repeat(auto-fit, minmax(max-content, 1fr))
}



-------------------------------------------------------------

node.js설치해야 SCSS사용가능

scss sass stylus less // css컴파일러 일반css로바꿔준다
scss->gulp->css

gulpfile.babel.js // node.js패키지 다운받기
dist폴더에 컴파일된css가 저장된다
npm install
npm run dev





src/scss/_variables.scss //변수파일 언더바있으면css로컴파일안된다
$bg: red;

src/scss/styles.scss
@import '_variables';
body {
	background: $bg;
}



.box {
	&:hover {
		background-color: green;
	}
	h2 {
		color: blue;
	}
	button {
		color: red;
	}
}







src/scss/_mixins.scss
@mixin sexyTitle {
	color: blue;
	font-size: 30px;
	margin-bottom: 12px;
}

src/scss/styles.scss
@import '_mixins';
h1 {
	@include sexyTitle();
}

@mixin link($color) {
	text-decoration: none;
	display: block;
	color: $color;
}

a {
	&:nth-child(odd) {
		@include link(blue);
	}
}

@mixin link($word) {
	text-decoration: none;
	display: block;
	@if $word == 'odd' {
		color: blue;
	} @else {
		color: red;
	}
}
a {
	&:nth-child(odd) {
		@include link(odd);
	}
}







src/scss/_buttons.scss
%button {
	border-radius: 7px;
	font-size: 12px;
	text-transform: uppercase;
	padding: 5px 10px;
}

src/scss/styles.scss
@import '_buttons';
a {
	@extend %button;
}

button {
	@extend %button;
}





src/scss/_mixins.scss
@mixin responsive($device) {
	@if $device == 'iphone' {
		@media screen and (min-width: 500px) and (max-width: 690px) {
			@content
		}
} @else if $device == 'tablet' {

} @else if $device == 'iphone-l' {

} @else if $device == 'ipad-l' {

}
}

@import '_mixins'
h1 {
	color: red;
	@include responsive('iphone') {
		color: yellow;
	}
	@include responsive('iphon-l') {
		font-size: 60px;
	}
}
