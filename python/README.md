# PYTHON [작성중]

까먹기 쉬운 내용을 정리하는 공간입니다



출제의도 자료구조 알고리즘
쉽게생각하기 vs 구현하기
엣지케이스
0나누기조심
시간복잡도-1초에2000만번
	from collections import deque
import sys
input = sys.stdin.readline

파이썬 fstring
람다
	max(queue, key=lambda x: x[1])
Zip Enumerate
	for pair in zip(numbers, letters)
	프린터
itertools
	소수찾기
	per += list(permutations(numbers, i))


n진법함수
	int()
소수 – 루트까지만 확인하기
제곱근판별법
	math.sqrt(n).is_integer()





알고리즘+자료구조 / 문제해결능력(출제의도파악 이론찾기) / 구현능력(다른사람코드빨리흡수)



시간복잡도-빅오표기법
파이썬은 1초에 2천만번

공간복잡도 - 변수의개수

​	512MB == 1.2억개의 int 변수 생성가능 // int 1개는 4바이트

​	리스트길이1백만 -> 4MB

​	정수 자료형의 범위
​		integer 오버플로우
​	실수 자료형의 범위
​		반드시오차가생긴다, == 사용하지마라

자료복사 조심해라
	값을복사 vs 주소를복사

참조형은 global 안써도 된다

====================

배열 발상의전환

긴배열선언해놓고 시간복잡도줄이는법생각하기

반복문조건 참신하게 생각해보기

소수구하기 = 2부터 루트까지만

소수점출력

그리디-가장큰단위가 항상작은단위의 배수일때만가능

=======================================

divmod(5, 2)
0b111 0o111 0x111
complex(1.2, 1.3)
print(1, 2, 3, sep=' ')
print(1, end='')
a is b #객체가 같냐?
id(a) # 주소값
bool(1) #True
a = list(range(0, 10, 2))
a = (1, 2, 3) # 튜플은 읽기전용
시퀀스객체 + * len() 인덱스 a.__getitem__(인덱스) 슬라이싱 slice(4, 7)

딕셔너리생성시key가중복되면뒤에있는값사용 / key중복불가
dict(zip([], []))
map안에는 시퀀스만가능

reversed(range(10))
range(10).reverse
random.randint(1, 6)
random.choice(리스트)

a.append()
a.extend()
a.insert(2, 3) # 2번에넣고밀기
a.pop() vs a.remove(값)
a.index(값) a.count(값) a.clear()
b = a.copy()

for i, v in enumerate(a, start=1):
print(i, v)
a.sort(reverse=True)
a = [i for i in range(10)]
a = [i * j for j in range(2, 10) for i in range(1, 10)]

from pprint import pprint
pprint(a, indent=4, width=20)

sorted(a, key=lambda a: a[1])

import copy
b = copy.deepcopy(a)

'hello python'.replace('hello', 'hi')

table = str.maketrans('aeiou', '12345')
'apple'.translate(table)
''.join(리스트)
.upper() .lower() .lstrip() .rstrip() .strip()

import string
string.punctuation

''.ljust(10) ''.rjust(10) ''.center(10)
''.zfill(4)
''.find('a') ''.index('a')

'%.2f' % 2.3 #2.30
'%-10s' % 'python'
'{}'.format(a)

딕셔너리.setdefault('e') #딕셔너리추가하기
딕셔너리.update(a=90)

set

try except exit()

string.replace(a, b)
file

---------------------------------------------------------------------------

[자료구조]
연결리스트
asdf
스택 큐 덱
트리 트리순회
그래프
	DFS BFS
	최소신장트리 - 크루스칼 프림
	최단경로 - 다익스트라 벨만포드 플로이드마샬

[정렬]
버블정렬
선택정렬
삽입정렬



퀵정렬 - 비추 NlogN~N**2

병합정렬 - 분할하기 합치기 / stable sort

카운팅소트-수의 범위가 한정적일때에만 사용

radix소트 - 일의자리수로카운팅, 십의자리수로카운팅, 백의자리수로카운팅... / 공간낭비심하다



셸정렬

힙정렬
트리정렬





[검색]
순차탐색
이진탐색
이진트리탐색
해싱



dfs - 스택에저장하는순서 vs pop순서 구분해서생각해라

​	트리에서주로사용, 생각보다많이안쓴다

​	올바르지않은괄호쌍3가지케이스

​	스택의길이활용하기

​	스택에 인덱스와값으로 저장하기

bfs - 구현방식그냥외월 while로구현

​	continue로 예외케이스먼저끝내기

​	큐에서뺄때방문처리x 큐에넣을때방문처리o

​	최단거리문제는 무조건 bfs다

dfs bfs는 탐색이다 내가원하는자료를찾기위한알고리즘

방문기록을저장할변수

그래프로 자료가저장되어있어야 dfs bfs 사용할 수 있다 / 그래프는 2차원리스트, 인접행렬로 구현



[기타]
그리디
다이나믹프로그래밍

==============================

실수형은 오차발생
round(123.457, 2) 123.46

a = [i for i in range(20) if i%2==1]
a = [[0]*m for _ in range(n)]
리스트copy조심

문자열은수정불가

튜플
	수정불가
	()
	리스트보다 공간효율적

딕셔너리

집합
	순서x
	중복x
	set()
	{}
	| &
	add update remove

----------------------------------------------------------------

import sys
data = sys.stdin.readline().rstrip()

print(+ , end=' ')
f"{}"

result = True if score >= 80 else False

파라미터 사용법

예외처리

global 바깥변수 수정하려면 가져오기 / 그냥읽기만할때는global없어도된다
전역변수의 내부메소드는 그냥사용가능

(lambda a, b: a + b)(3, 7)
sorted(array, key=lambda x: x[1])
result = map(lambda a,b: a+b, list1, list2)


heapq
bisect
collections
math
eval('(3+5)*7')
sorted(reverse=True, key=)

itertools 순열 조합
from itertools import permutations
data = ['a', 'b', 'c']
result = list(permutations(data, 3))

from itertools import combinations
result = list(combinations(data, 2))

from itertools import product #중복순열
result = list(product(data, repeat=2))

from itertools import combinations_with_replacement #중복조합
result = list(combinations_with_replacement(data, 2))

from collections import Counter
counter = Counter(['a', 'a' ,'a' ,'b' ,'b'])
print(counter['blue'])
print(dict(counter))

import math
math.gcd(21, 14)

========================================

일단그리디실행하기
최적의해인지판단하기

구현-시뮬레이션과 완전탐색
풀이는쉽지만 소스코드로옮기기어려운문제
알고리즘은쉬운데 코드가길어지는문제
문자열다루는문제
2차원행렬





그래프 탐색 알고리즘

스택자료구조 stack[::-1]

큐자료구조 시간복잡도때문에 라이브러리써라
from collections import deque
queue = deque()
queue.append(1)
queue.popleft()
queue.reverse()



cards = deque([i for i in range(1, N+1)])

deque사용법공부하기 / deque() vs deque([])

queue = deque([1, 2, 3], 3) / literal, maxlen

reverse() 시간복잡도 고려하기



재귀함수-자신을호출하는함수 / 스택 / 깊이제한
종료조건

팩토리얼구현-반복으로구현, 재귀로구현
유클리드호제법 최대공약수계산

DFS-방문처리, 스택
그래프자료구조-2차원리스트로표현
방문리스트

BFS-방문처리 큐



스택에 담긴 길이를 활용하기

어떤기준으로스택에담을것인가



[스택구현시 주의사항]

닫는괄호일때 스택이비어있으면 False
닫는괄호일때 스택의top이다른경우 False
끝났는데스택에남아있다면 False





시간복잡도
자료구조 / 리스트 셋 딕셔너리 튜플 스택 큐 트리 그래프
출제의도, 알고리즘
실수형 오차 / 실수형출력 / 소수점자리수 format(?, '.3f')
sys.stdin.readline() / sys.stdin.readline().rstrip()
f-string / print(end sep , +)
try except exit()
긴배열을미리만들어놓고 개수세기

N이 크다면 그냥 반복문 한번으로 하는 방법 생각해라



재귀함수

자신을 호출하는 함수

절차지향적사고 vs 수학적귀납법

1번도미노가쓰러진다 / k번도미노가쓰러지면 k+1번도미노가쓰러진다

모든 재귀는 반복문으로 풀 수 있다

조기 리턴

꼬리 재귀 - 함수만 리턴하기 / 지원 가능한 언어인지 확인해라

스택메모리 제한 해제하는 법 알아둬라

1. 귀납적사고하기 / k+1
2. 종료조건 생각하기 - 함수를호출x, 수렴하는조건
3. 함수의 인자, 리턴
4. 재귀식 - 분기해서 처리하기



부분집합, 부분집합의합, 순열, 조합, 중복조합

비트연산, 반복, 재귀



시간초과 줄이기

- import sys
- from collections import deque
- 엣지케이스를 생각해라, 입력범위의 처음과 끝이 주어졌을 때

------------------------------------------------

```python
numbers = [5, 4, 3, 2, 1]

def bubble_sort(numbers):
    for i in range(len(numbers)-1, 0, -1):
        for j in range(0, i, 1):
            if numbers[j] > numbers[j+1]:
                temp = numbers[j+1]
                numbers[j+1] = numbers[j]
                numbers[j] = temp
            print(j, i)
    return numbers
print(bubble_sort(numbers))

for i in range(0, len(a)):
    for j in range(0, len(a)-1-i):
        if a[j] > a[j+1]:
            a[j], a[j+1] = a[j+1], a[j]
print(a)

for i in range(len(a)-1, 0, -1):
    max_index = 0
    for j in range(1, i+1):
        if a[max_index] < a[j]:
            max_index = j
    a[max_index], a[i] = a[i], a[max_index]
print(a)
```

```python
# 전체 경우의 수 - 트리로 생각해라 / 노드와 엣지 모두 의미가 있다
'''
def solution(remain, seated):
    global count

    if remain < 0:
        return
    if remain == 0:
        count += 1
        return

    for i in range(seated, max_value+1):
        solution(remain-i, i)


n = int(input())
min_value = 2
max_value = 10
count = 0

solution(n, min_value)

print(count)
'''

'''
def solution(remain, seated):
    key = str((remain, seated))

    if remain < 0:
        return 0
    if remain == 0:
        return 1

    count = 0
    for i in range(seated, max_value+1):
        count += solution(remain-i, i)
    return count


n = int(input())
min_value = 2
max_value = 10

print(solution(n, min_value))
'''

'''
def solution(remain, seated):
    key = str((remain, seated))
    if key in memo:
        return memo[key]

    if remain < 0:
        return 0
    if remain == 0:
        return 1

    count = 0
    for i in range(seated, max_value+1):
        count += solution(remain-i, i)

    memo[key] = count
    
    return count


n = int(input())
min_value = 2
max_value = 10
memo = {}

print(solution(n, min_value))
'''
#########################################
'''
n = int(input())

count = 0
for rock in range(0, n+1):
    remain = n - rock

    for cissor in range(0, remain+1):
        paper = remain - cissor

        temp_list = [rock, cissor, paper]
        if temp_list.count(max(temp_list)) == 1:
            count += 1

print(count)
'''
##########################################
'''
n = int(input())
lights = [6, 2, 5, 5, 4, 5, 6, 3, 7, 6]

def count_light(number):
    output = 0
    for i in '{:02}'.format(number):
        output += lights[int(i)]
    return output

count = 0
for h in range(24):
    for m in range(60):
        for s in range(60):
            if count_light(h) + count_light(m) + count_light(s) == n:
                count += 1

print(count)
'''

n = int(input())
lights = [6, 2, 5, 5, 4, 5, 6, 3, 7, 6]
memo = {}

def count_light(number):
    if number in memo:
        return memo[number]
    
    output = 0
    for i in '{:02}'.format(number):
        output += lights[int(i)]

    memo[number] = output
    
    return output

count = 0
for h in range(24):
    for m in range(60):
        for s in range(60):
            if count_light(h) + count_light(m) + count_light(s) == n:
                count += 1

print(count)

```

