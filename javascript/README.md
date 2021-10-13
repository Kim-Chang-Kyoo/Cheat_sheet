# JavaScript [작성중]

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
-랜덤구현하기

-------------------------------------------------------------------------------------------------------------------



null /아무것도없음 / 질적개념
undefined / 아직없음
NaN

const a = []
a.push()

const player = {
	name: 'a',
	points: 10,
	fat: true,
}
player['name']
player.name = 'b' // 수정가능
player.lastname = 'aa' //추가가능

function sayHello(name) {
	console.log('hi', name)
}
sayHello('kkk')

sayHello: function() {
}

const age = parseInt(prompt('how old are you')) // 비추
typeof age / typeof(age)
&& ||

if (isNan(age)) {
	console.log()
} else if (age < 18) {
	console.log()
} else {

}


================================
console.dir(document)
document.title
document.body

const title = document.getElementById('title') // 태그와 요소 모두 가져옴
console.dir(title)
title.innerText = 'zz'
title.className
const hellos = document.getElementsByClassName('hello')
const title = document.getElementsByTagName('h1')

const title = document.querySelector('.hello h1')
const title = document.querySelectorAll('.hello h1')
title.style.color = 'blue'

function a() {
}
title.addEventListener('click', a)
title.onclick = a
title.addEventListener('mouseenter', a)

function b() {
	document.body.style.backgroundcolor = 'tomato'
}
window.addEventListener('resize', b)
window.addEventListener('copy', b)
window.addEventListener('offline', b)
window.addEventListener('online', b)

function a() {
	const currentColor = h1.style.color
	let newColor
	if (currentColor === 'blue') {
		newColor = 'tomao'
	} else {
		newColor = 'blue'
	}
	h1.style.color = newColor
}
h1.addEventListener('click', a)


h1 {
	color: blue;
}
.active {
	color: tomamo;
}
function a() {
	if (h1.className === 'active') {
		h1.className = ''
	} else {
		h1.className = 'active'
	}
}
h1.addEventListener('click', a)

function a() {
	const clickedClass = 'clicked'
	if (h1.classList.contains(clickedClass)) {
		h1.classList.remove(clickedClass)
	} else {
		h1.classList.add(clickedClass)
	}
}

function a() {
	h1.classList.toggle('clicked')
}

-----------------------------------------------------
form input submit //form은자동으로 submit한다, 새로고침실행
event.preventDefault()


.hidden {
	display: none;
}
const HIDDEN_CLASSNAME = 'hidden'
const USERNAME_KEY = 'username'

const savedUsername = localStorage.getItem(USERNAME_KEY)
if (savedUsername === null) {
	loginForm.classList.remove(HIDDEN_CLASSNAME)
	loginForm.addEventListener('submit', a)
} else {
	paintGreetings(savedUsername)	
}

function a(event) {
	event.preventDefault()
	loginForm.classList.add(HIDDEN_CLASSNAME)
	localStorage.setItem(USERNAME_KEY, username)
	paintGreetings(username)
}

function paintGreetings(username) {
	const username = localStorage.getItem(USERNAME_KEY)
	greetings.innerText = `hello ${usename}`
	greeting.classList.remove(HIDDEN_CLASSNAME)
}

========================================
setInterval(a, 5000)
setTimeout(a, 5000)

const date = new Date()
String(date.getHours()).padStart(2, '0') // .padEnd()

-----------------------------------------------------
const quotes = [
	{quote: 'a', author:'a'},
	{quote: 'b', author:'b'},
]

Math.floor(Math.random() * quotes.length) // round() ceil()


-----------------------------------------------------------------------------------------------


const images = ['0.jpg', '1.jpg', '2.jpg']
const chosenImage = images[~]

const bigImage = document.createElement('img')
bigImage.src = `img/${chosenImage}`
document.body.appendChild(bigImage)

==========================================

function deleteTodo(event) {
	const li = event.target.parentElement
	li.remove()
}

로컬스토리지에는 텍스트만 저장할 수 있다
localStorage.setItem('todos', JSON.stringify(todos))
JSON.parse(localStorage.getItem('todos'))

parsedTodos.forEach(sayHello)
parsedTodos.forEach((item) => console.log('hi', item))

let todos = []

const newTodoObj = {
	text: newTodo,
	id: Date.now()
}
li.id = newTodo.id
todos.push(newTodoObj)

function sexyFilter(item){return item !== 3}
[1, 2, 3, 4].filter(sexyFilter)
todos = todos.filter((todo) => todo.id !== parseInt(li.id))

===========================================
navigator.gelocation.getCurrentPosition(success, error)
function success(position) {
	console.log(position)
}

openweathermap.org

fecth(url)
	.then(response => response.json())
	.then(data => console.log(data))

--------------------------------------------------------
String() vs stringify()


------------------------------------------------------------

-------------------------------------------------------------





[그림판 만들기]

깃헙에서 새로 만들기
.gitignore node
깃클론
index.html
style.css / import reset.css
app.js
git push

-------------------------------------------------------
캔버스만들기
id는js, class는css
<canvas></canvas>

색상선택만들기
cursor: pointer;

버튼만들기
fill
save

붓두께
<input type='range' min='0.1' max='5.0' value='2.5' step='0.5' />

-----------------------------------------------------------
mousemove이벤트 만들기
mousedown이벤트 만들기
mouseup이벤트 만들기
mouseleave이벤트 만들기

선그리기
mdn에서 canvas 알아보기

색바꾸기

브러쉬두께

바탕채우기

저장하기





--------------------------------------------

-------------------------------------

---------------------------------------------

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
