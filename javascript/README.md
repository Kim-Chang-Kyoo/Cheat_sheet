# JavaScript

[momentum]

open with live server 에러해결하는방법
크로미움기반 브라우저 / 브레이브
넷스케이프 브라우저
replit.com 온라인ide

document == HTML
console.dir(title)
요소 리스트로가져오기 vs 요소 한개만가져오기

title.addEventListener('click', handleTitleClick) //소괄호넣으면바로실행한다
title.onclick = handleTitleClick

function handleWindowReisze () {
	document.body.style.backgroundcolor = 'tomato'
}
window.addEventListener('resize', handleWindowResize)

css파일에 클래스를만든다 -> js파일에 함수를 만든다
function a () {
	if (h1.className === 'active') {
		h1.className = ''
	} else {
		h1.className = 'active'
	}
}

// className대신 classList사용해라 / 안그러면 기존에 있던거 사라진다
if (h1.classList.contains('active')) {
	h1.classList.remove('active')
} else {
	h1.classList.add('active')
}

// toggle이더편하다
function hadleTitleClick () {
	h1.classList.toggle('clicked')
}
h1.addEventListener('clilck', handleTitleClick)

form은 submit할때마다 페이지가새로고침된다
페이지 전체 새로고침하는건 좋지않아
로컬스토리지에는 text만 저장할수있다
forEach, filter
fetch // js가url요청대신해준다

요소찾기->이벤트리스너->함수구현
최대한변수로빼라
최대한함수로빼라
-로그인
	로컬스토리지에 아이디없으면 입력보이게하기, 로그인이벤트실행
	입력숨기기, 입력값로컬스토리지에저장하기, 환영인사보이기
	로컬스토리지에아이디있으면 환영인사보이기
-시간
	setInterval
	함수에소괄호넣으면바로실행한다
	String()으로만든다 -> padStart(2, '0')
-할일
	로컬스토리지에있으면 JSON으로바꾸기 -> todos변수에넣기 -> forEach
	입력할때마다 이벤트연결하기
	입력값 객체로만들어서 todos에넣기 -> 출력하기 -> 로컬스토리지에저장하기
	삭제버튼만들기 -> filter -> 저장하기
-명언
	랜덤구현하기
-날씨
	navigator.geolocation.getCurrentPosition(pass, fail)
	pass함수에서 position인자받기 -> fetch로 api요청하기
-배경
	랜덤구현하기
===========================================
===========================================
===========================================
[zoom]

백엔드 설치
npm init -y //프로젝트 이름 조심
npm install nodemon -D
babel.config.json
nodemon.json
src/server.js
npm install @babel/core @babel/cli @babel/node @babel/preset-env -D
.gitignore
npm install express
npm insall pug
npm run dev

프론트엔드 설치
