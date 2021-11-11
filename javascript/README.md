# JavaScript [작성중]





자바스크립트 클래스
constructor({ $target, setPlayers }) {
    this.$target = $target;
    this.$input = this.$target.querySelector(`#${ID.CAR_NAMES_INPUT}`);
}

userInputNumbers = Array.from(userInputNumbers).map((num) => parseInt(num));

export default BaseballGame

const strike = target.filter((num, i) => num === inputs[i]).length;
forEach
map

return result ? result : MESSAGE.NOTHING;

const result = new Set();

return [...result];

bind()

try{} catch{}
JSON.parse()
JSON.stringfy()



동적웹사이트를만들고싶어 script언어
1. 넷스케이프 네비게이터 브라우저 + JavaScript
2. MS 익스플로러 + Jscript
ECMA스크립트 협의
3. 모질라의 파이어폭스 + ActionScript
4. 구글의 크롬
ECMA스크립트5 2009
ECMA스크립트6 2015

브라우저마다 자바스크립트 엔진이 다르다
BABEL - 자바스크립트 컴파일러
SPA - 페이지 일부분만 업데이트하기 -> 뷰 리액트 앵귤러
MDN 참고해라
입력 -> 연산 -> 출력
유효성검사 중요하다
다이나믹 타이핑 - 변수가 바뀐다
객체내용물은 수정가능
mutable(all, objects) vs immutable(primitive, frozen objects)

script를 head에 넣을지 body에넣을지
async vs defer
head에 defer넣어라
'use strict';
let const var / hoisting / block {}
early return, early exit

primive type - number(Infinity -Infinity NaN bigInt) string boolean null undefined symbol
object type - const a = {name: "aa", age: 20};
function - first class function

`${a}`
typeof a
a.charAt(0)
console.log('1' + 2)
console.log(2 ** 3)
const b = ++a // 더하고 할당
const b = a++ // 할당하고 더하기
|| && ! // simple한것을 앞에 조건으로두고 무거운조건을뒤로보내기
== vs ===
console.log(0 === false)

if () {

} else if () {

} else {

}
console.log(name === 'elie' ? 'yes' : 'no')

switch (browswer) {
	case 'IE':
		console.log('a');
		break;
	case 'chrome':
	case 'firefox':
		console.log('b');
		break;
	default:
		console.log('c'):
		break;
}

let i = 3;
while (i > 0) {
	console.log(i);
	i--;
}

do {
	console.log('i');
	i--;
} while (i > 0);

for (i = 3; i > 0; i--) {
	console.log(i);
}

function a (a, b='unknown') {
	console.log(a);
}

function a (...args) {
	for (let i = 0; i < args.length; i++) {
		console.log(args[i]);
	}
	
	for (const arg of args) {
		console.log(arg);
	}
	
	args.forEach((arg) => console.log(arg));
}
a('1', '2', '3')
----------------------------------------------------
1등급함수-할당, 인자, 리턴값

익명함수
const print = function () {
};
print();

콜백함수-함수에서다른함수호출하기
function a (answer, yes, no) {
	if (answer === 'a') {
		yes()
	} else {
		no()
	}
}

기명함수
const a = function a() {
	a();
}

화살표함수
const a = (b, c) => return b+c;

즉시호출
(function a () {
	console.log('a');
})();







-----------------------------------------------------------------------------

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



zoom폴더만들기
npm init -y //프로젝트이름조심

백엔드
package.json수정하기
README만들기
npm install nodemon -D
babel.config.json만들기
nodemon.json만들기
src/server.js만들기
npm install @bable/core @babel/cli @babel/node @babel/preset-env -D
.gitignore만들기 /node_moules추가
nodemon수정하기
babel.config.json수정하기
package.json 수정
npm install express
npm install pug //git commit해야함
server.js수정하기
npm run dev
localhost:3000 작동확인하기

프론트엔드
src/public/js/app.js 만들기
src/views/home.pug만들기
server.js에 pug입력

nodemon -> babel -> server.js -> home.pug
