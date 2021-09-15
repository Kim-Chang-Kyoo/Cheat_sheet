# PYTHON

까먹기 쉬운 내용을 정리하는 공간입니다



리스트 거꾸로 출력

리스트 언팩

명령어 실행시간

시간복잡도

이진탐색

swea 4871번 스택



알고리즘+자료구조 / 문제해결능력(출제의도파악 이론찾기) / 구현능력(다른사람코드빨리흡수)



시간복잡도-빅오표기법
	1초에3~5억번연산?
	1
	logN
	N 1천만이하
	NlogN 1백만이하
	N**2 5천이하
	N**2logN 3천이하
	N**3 5백이하
	N**4 1백이하
	2**N 25이하
	N! 11이하
	

공간복잡도 - 변수의개수

​	512MB == 1.2억개의 int 변수 생성가능 // int 1개는 4바이트
​	정수 자료형의 범위
​		integer 오버플로우
​	실수 자료형의 범위
​		반드시오차가생긴다, == 사용하지마라

자료복사 조심해라
	값을복사 vs 주소를복사

====================

배열 발상의전환

긴배열선언해놓고 시간복잡도줄이는법생각하기

반복문조건 참신하게 생각해보기



소수점출력

input()대신하는법



그리디-가장큰단위가 항상작은단위의 배수일때만가능

=======================================

=======================================

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

file
==============================
==============================
==============================
[자료구조]
연결리스트
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
셸정렬
퀵정렬
기수정렬
병합정렬
힙정렬
트리정렬

[검색]
순차탐색
이진탐색
이진트리탐색
해싱

[기타]
그리디
다이나믹프로그래밍



==============================

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
```

