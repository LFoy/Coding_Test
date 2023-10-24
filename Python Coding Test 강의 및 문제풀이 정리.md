한줄 주석 #  
두줄이상 주석 ''' 주석내용 ''' : 큰따옴표 3개 or 작은따옴표 3개

if elif else

들여쓰기할떄  
탭이랑 스페이스 같이 쓰면 안되고 무조건 하나로만 써야함

문자열의 경우  
더하기 + 는 가능하다.  
하지만 배열은 아니기에 아래 처럼 사용하지 못한다  
*  
즉 a 변수에 "Pithon" 문자열을 대입하고 a[1]의 값이 i니까 a[1]을 y로 바꾸어 준다는 생각이다. 하지만 결과는 어떻게 나올까?

당연히 오류가 발생한다. 왜냐하면 문자열의 요솟값은 바꿀 수 있는 값이 아니기 때문이다(문자열 자료형은 그 요솟값을 변경할 수 없다. 그래서 immutable한 자료형이라고도 부른다).

문자열.replace("as-is문자열". "to-be문자열") 로 바꾸장  
*replace 함수 유의할점  
replace('바꿀문자열', '새문자열')은 문자열 안의 문자열을 다른 문자열로 바꿉니다(문자열 자체는 변경하지 않으며 바뀐 결과를 반환합니다).  
-> 따라서 다시 선언해줘야함. 문자열 자체가 바뀌는게 아니라서

문자열.len XXXXXXXXXX  
len(문자열) OOOOOOOOO

내가 짠 첫 코드 : 레벨1 둘만의 암호 // 정확도 52점

def solution(s, skip, index):  
answer = ''  
aToz = "abcdefghijklmnopqrstuwvxyz"

```
for i in skip:
    aToz = aToz.replace(i, "")

for i in s:
    answer += aToz[ (aToz.find(i) + index) % len(aToz) ]

return answer
```

- >  
    정확도에서 틀린 이유  
    stuvw 인데 struwv 해서....  
    알파벳 못외우니까

아래와 같이 string 모듈에서 ascii_lowercase 를 import 한다.

ascii_uppercase  
from string import ascii_lowercase

def solution(s, skip, index):  
answer = ''  
aToz = ascii_lowercase  
ascii_lowercase만으로 문자열이고 배열로 만들고 싶다면 list(ascii_lowercase) 사용하면됨

string type과 list type을 오가게 하는 함수 존재  
문자열을 배열로 : listA = strB.split("딜리미터")  
배열을 문자열로 : strB = "딜리미터".join(listA) // 배열 원소마다 딜리미터가 들어가며 문자열이 완성됨  
ex strB = " ".join(listA) -> Python is fun

문자열, 배열로 풀기 어려운 건 집합연산자로 사용 가능  
+배열 일때 중복제거 하고싶으면 set()함수 쓰면됨 ex) set("배열")  
기존 순서를 유지하면서 중복제거 하고 싶으면  
For value in array:  
if value not in result:  
result.append(value)

a = {1, 2, 3, 4}  
b = {3, 4, 5 ,6}  
a | b 합집합  
a & b 교집합  
a - b 차집합  
a ^ b 대칭차집함 // 무슨 의미냐면 ( a - b ) + ( b - a ) 라는 뜻. 서로 안겹치는 거 모조리 WOWWWWWWW

set()이 중복을 제거하는 것 외에도, 복잡도를 줄이기 위해서 쓰이고 있네요.  
집합.remove() 는 O(1)  
리스트.remove() 는 O(n)  
어쩌다보니 집합으로 풀어서 통과했나보네;;;

(1) sort()

리스트 전용 메소드로 리스트명.sort( )형식으로 사용함  
리스트 원본값을 직접 수정  
(2) sorted()

내장함수이며, 리스트 외에도 사용할 수 있음  
sorted( 리스트명 ) 형식으로 사용함  
리스트 원본 값은 그대로이고 정렬 값을 반환함

% 나머지의 느낌을 잘 기억하자  
배열을 몇번 띄어넘고 다시 처음으로 되돌아가야할때 나머지를...써야함...

두개의 문자열을 비교하는 방법을 보겠습니다. 비교 방법으로는 완전 일치, 부분 일치가 있습니다.・  
완전 일치 : == , != ・ 부분 일치 : in , not .

1. `pass : 실행할 코드가 없는 것으로 다음 행동을 계속해서 진행합니다.`  
    의미없는 줄
2. `continue : 바로 다음 순번의 loop를 수행합니다.`  
    continue 밑에 실행 안하고 그 다음 loop 계속 타는거임
3. `break : 반복문을 멈추고 loop 밖으로 나가도록합니다`  
    만나자마자 얘가 속한 loop가 아예 걍 끝남

# 다른 언어

i++;  
i--;  
++i;  
--i;

# Python ++ 증감연산자 이런거 없음 ㄷㄷ += 으로 해야함

i += 1  
i -= 1

For 문 돌릴때 유의사항

range(10)은 0부터 10 미만의 숫자를 포함하는 range 객체를 만들어 준다.

시작 숫자와 끝 숫자를 지정하려면 range(시작 숫자, 끝 숫자) 형태를 사용하는데, 이때 끝 숫자는 포함되지 않는다.  
*따라서 range(10) 과 range(1, 11)은 같다고 착각할수 있는데 같지않다  
range(10) 은 0~9 이고  
range(1, 11)은 1~10이다 ㅋㅋ

- C처럼 for i in 10 이렇게하면 ㅈ된다ㅋ for i in range(10) 해야함

으앙.... 이거 시간초과뜸 10초 이내로 테스트케이스 소화못해서...  
그래도 맞긴해서 기분이 너무 좋당ㅠㅠ

첨에 짠건 최대 20만건인 배열을 두번 포문 돌게 짰음...  
딕셔너리 이용해서 한번만 돌게끔 바꾸니까 속도 바로 개선돼서 정답됨  
시간이 중요해보이는 건 최대건수가 젤 높은 배열이 뭔지 빨리 캐치해서  
그 배열을 한번만 돌릴수 있는 방법을 머리를 굴려야함.

def solution(id_list, report, k):  
uni_report = set(report) # 중복제거한 신고 목록  
warning = {} # 신고 받은 사람 : 키, 신고한 사람 리스트: 밸류  
mail = {} # 신고한 사람이 메일 받을 횟수 저장한 딕셔너리

```
# 딕셔너리 생성
for user in id_list:
    mail[user] = 0
    warning[user] = []

#신고 당한 사람 : 신고자 리스트 를 가진 딕셔너리 생성
for i in uni_report:
    warning[i.split(" ")[1]].append(i.split(" ")[0])

# k번 이상 신고당한 유저를 찾고 그 유저를 신고한 신고자의 메일 카운트를 +1한다
for key, val in warning.items():
    if len(val) >= k:
        for singoer in val:
            mail[singoer] = mail[singoer]+1

return list(mail.values())
------------------------------------------------
```

딕셔너리 두개 안쓰고 index 함수 이용해서 해당 문자열이 몇번째 인덱스에 있는지  
알려주는 함수로 주어진 answer 배열을 이용할수 있었겠군

def solution(id_list, report, k):  
answer = [0] * len(id_list)  
dic_report = {id: [] for id in id_list} # 해당 유저를 신고한 ID  
for i in set(report):  
i = i.split()  
dic_report[i[1]].append(i[0])

```
for key, value in dic_report.items():
    if len(value) >= k:
        for j in value:
            answer[id_list.index(j)] += 1

return answer
```

문자열 find, index 차이  
find는 못찾으면 -1 리턴  
index는 못찾으면 에러 리턴

문자열, 배열, 딕트 주어진 문제에 맞게 length를 초기화 하는 함수 정리  
배열 : listA = [0] * len(주어진파라미터) or  
listA = [0 for i in range(len(주어진파라미터))]

ord 문자의 유니코드 반환 chr는. 유니코드를 문자로 반환

> ord('a')  
> 97  
> ord('가')  
> 44032

나눗셈 후 몫을 반환하는 // 연산자  
7 // 4 = 몪만  
7/ 4 = 소수점까지

리스트, 딕셔너리, 집합 시간복잡도

Set과 Dictionary는 삽입, 제거, 탐색, 포함여부확인 연산에 O(1)의 시간 복잡도를 가지고 있습니다.  
탐색과 확인이 주로 필요한 연산이라면 Set이나 Dictionary를 사용하는 것이 좋고 순서와 index에 따른 접근이 필요하다면 List 자료형을 사용하는 것이 좋을 것입니다.

```
Operation	Example	Class	Notes
```

1 Add s.add(5) O(1) 집합 요소 추가  
2 Containment x in/not in s O(1) 포함 여부 확인  
3 Remove s.remove(..) O(1) 요소 제거  
4 Discard s.discard(..) O(1) 특정 요소 제거  
5 Pop s.pop() O(1) 랜덤하게 하나 pop  
6 Clear s.clear() O(1) similar to s = set()  
7 Construction set(...) O(len(...)) 길이만큼  
8 check ==, != s != t O(len(s)) 전체 요소 동일 여부 확인  
9 <=/< s <= t O(len(s)) 부분집합 여부  
10 >=/> s >= t O(len(t)) 부분집합 여부  
11 Union s, t O(len(s)+len(t)) 합집합  
12 Intersection s & t O(len(s)+len(t)) 교집합  
13 Difference s - t O(len(s)+len(t)) 차집합  
14 Symmetric Diff s ^ t O(len(s)+len(t)) 여집합  
15 Iteration for v in s: O(N) 전체 요소 순회  
16 Copy s.copy() O(N) 복제

```
Operation	Example	Class	Notes
```

1 Store d[k] = v O(1) 데이터 저장  
2 Length len(d) O(1) 길이 출력  
3 Delete del d[k] O(1) 요소 제거  
4 get/setdefault d.get(k) O(1) key에 따른 value 확인  
5 Pop d.pop(k) O(1) pop  
6 Pop item d.popitem() O(1) 랜덤하게 선택해서 pop  
7 Clear d.clear() O(1) similar to s = {} or = dict()  
8 View d.keys() O(1) same for d.values() / 키값 전체 확인  
9 Construction dict(...) O(len(...)) (key, value) 튜플 개수만큼  
10 Iteration for k in d: O(N) 전체 딕셔너리 순회

```
Operation	Example	Class	Notes
```

1 Index l[i] O(1) 인덱스로 값 찾기  
2 Store l[i] = 0 O(1) 인덱스로 데이터 저장  
3 Length len(l) O(1) 리스트 길이  
4 Append l.append(5) O(1) 리스드 뒤에 데이터 저장  
5 Pop l.pop() O(1) 가장 뒤의 데이터 pop  
6 Clear l.clear() O(1) l = []  
7 Slice l[a:b] O(b-a) 슬라이싱되는 요소들 수 만큼 비례  
8 Extend l.extend(...) O(len(...)) 확장되는 길이만큼  
9 Construction list(...) O(len(...)) 리스트 길이만큼  
10 check ==, != l1 == l2 O(N) 전체 리스트가 동일한지 확인  
11 Insert l[a:b] = ... O(N) 데이터 삽입  
12 Delete del l[i] O(N) 데이터 삭제  
13 Containment x in/not in l O(N) 포함 여부 확인  
14 Copy l.copy() O(N) 복제  
15 Remove l.remove(...) O(N) 제거  
16 Pop l.pop(i) O(N) 제거된 값 이후를 전부 한칸씩 당겨줘야함  
17 Extreme value min(l)/max(l) O(N) 전체 데이터를 확인해야함  
18 Reverse l.reverse() O(N) 뒤집기  
19 Iteration for v in l: O(N) 전체 데이터 확인하므로  
20 Sort l.sort() O(N Log N) 파이썬 기본 정렬 알고리즘  
21 Multiply k*l O(k N) 리스트의 곱은 리스트 개수 늘어남

딕셔너리 key값 중복으로 넣는법  
각 Key를 각각의 객체로 만들어버리는것이다.

class person(object):  
def **init**(self,name):  
[self.name](http://self.name/) = name

```
def __str__(self):
    return self.name

def __repr__(self):
    return "'"+self.name+"'"
```

def solution():  
tmp_dict = {}

```
tmp_dict[person("bob")] = 18
tmp_dict[person("bob")] = 20
tmp_dict[person("anna")] = 15

print (tmp_dict)
```

딕셔너리 키,밸류 모두 in 연산 가능  
d.keys(), d.values()의 결과를 보면 리스트처럼 나오는 것을 볼 수 있습니다.  
네, 맞습니다. 그렇기 때문에 value 들도 in 연산자이 가능하게 됩니다.

딕셔너리  
value를 이용해 key를 찾아보겠습니다. 'CC'를 검색하니 '2'가 잘 나왔습니다.

[k for k, v in aa.items() if v == 'CC']

에러 잡는법

try:  
age=int(input('나이를 입력하세요: '))  
except:  
print('입력이 정확하지 않습니다.')  
else:  
if age <= 18:  
print('미성년자는 출입금지입니다.')  
else:  
print('환영합니다.')

list 를 for 문 돌릴때  
여기서 원소 뿐만 아니라 인덱스(index)도 함께 출력하고 싶을 때는 어떻게 해야할까요? 이 부분은 다른 프로그래밍 언어를 사용하시다가 파이썬으로 넘어오신 분들이 처음에 흔히 하는 질문이기도 한데요.

이러한 분들이 흔히 아래와 같은 코드를 작성하는 것을 종종 보게 됩니다.(내가 이렇게 짜지ㅋㅋ)

> i = 0  
> for letter in ['A', 'B', 'C']:  
> ... print(i, letter)  
> ... i += 1

바로 파이썬의 내장 함수인 enumerate()를 이용하면 되는데요. for 문의 in 뒷 부분을 enumerate() 함수로 한 번 감싸주기만 하면 됩니다.

> for entry in enumerate(['A', 'B', 'C']):  
> ... print(entry)  
> ...  
> (0, 'A')  
> (1, 'B')  
> (2, 'C')  
> enumerate() 함수는 기본적으로 인덱스와 원소로 이루어진 튜플(tuple)을 만들어줍니다. 따라서 인덱스와 원소를 각각 다른 변수에 할당하고 싶다면 인자 풀기(unpacking)를 해줘야 합니다.

> for i, letter in enumerate(['A', 'B', 'C']):  
> ... print(i, letter)  
> ...  
> 0 A  
> 1 B  
> 2 C

import collections

collections.Counter(paticipant) - collections.Counter(complement)  
counter 인자에 list를 넣으면 counter는 key가 list 값이고, 그 값들의 개수를 value로 가지는 딕셔너리 반환

hash 딕셔너리 구조  
hash(value) : value

마지막에 return dictC[hash(sum)] 해서 틀린거임 sum 자체가 해시값이라 dictC[sum] 했어야...

---

강의 내용

10^8 의 시간복잡도를 넘기면 안된다.  
파이썬의 sort는 nlogn 의 시간복잡도를 가진다.

## sort + two pointers(정렬한 배열에서 포인터가 양 끝을 가르키면서 중간에서 모이게)

파이썬 and, or 연산이 특이함 true, false 객체를 반환하지 않고 0이면 0, 1이면 1 3이면 3 등등

and 는 거짓일 경우 거짓인 표현식 자체를 리턴해줌  
ex)

> '' and True  
> ''  
> 0 and True  
> 0  
> False and True  
> False

A and B

A가 참이라면 연산의 결과는 뒤에 B에 달려있습니다. B가 참을 뜻하는 객체인지 거짓을 뜻하는 객체인지 확인할 필요가 있을까요?  
확인할 필요가없습니다. 그냥 B의 결과 리턴해주면됩니다.  
B가 참이라면 A and B연산의 결과는 참인거고, B가 거짓이라면 A and B연산의 결과는 거짓인거죠.

---

or 은 둘중 하나만 참이면 참인 표현식 자체를 리턴해줌  
ex)  
표현식1이 참이라면 뒤에 표현식은 신경 쓰지 않습니다. 그냥 표현식1을 리턴

> 1 or ''  
> 1

만약 표현식1이 거짓이라면 or연산자는 표현식2는 신경도 안씁니다. 어차피 결정은 표현식2가 참이냐 거짓이냐에 따라 달려있습니다.

그냥 표현식2의 계산결과를 리턴해줍니다.

> 0 or 1 * 2 * 3 * 0  
> 0

---

not 표현식은 and, or이랑 다르게 false, true 객체를 반환

> False or 'False'  
> 'False'

---

트리는 구현부터 문제풀이 까지 무조건 재귀로 해결한다  
예를 들면 트리가 주어지면 우선 subtree(노드 3개)짜리로 생각해서 거기서 알고리즘을 만든다음  
subtree를 인자로하는 left, right 각각 재귀함수를 호출하여 확장시켜나가는 식으로 해결

tree랑 bfs, dfs 중요, BFS는 특히 levelorder 방법과 같아서 더 중요. (pre, in, postorder 이건 DFS 재귀방식)  
그래서 BFS 구현은 그냥 암기해야함.  
postorder도 좋음 방문이란건 어떤 행위를 한다는 것과 같은게 postorder는 내가 가진 섭트리 다 끝내고 나자신을 방문(어떤 행위를 할지 결정)한다는 것이므로

  

```
from collections import deque

def bfs(root):
visited = []

if root is None:
	return 0

q = deque()
q.append(root)

while q:
	cur_node = q.popleft()
	visited.append(cur_node.value)

	if cur_node.left:
		q.append(cur_node.left)
	if cur_node.right:
		q.append(cur_node.right)

return visited
```

  

```
def postorder_DFS(cur_node):

if cur_node is None:
	return

postorder(cur_node.left)
postorder(cur_node.right)
print(cur_node.value) <------------여기가 print가 아니라 다른 코드를 작성하면 액션하는 시점이 됨
```

  

파이썬은 뭔가 카운트를 위한 전역변수 선언을 잘 안하고  
tuple이나 dictionary로 선언해서 쌍으로 카운트를 가지고 있던가  
enumerate를 하던가... 그런식으로 카운트를 한다.

Graph 도 BFS, DFS 템플릿처럼 외워야함.

  

==미로찾기, 최단거리 -> BFS 로 풀어야함 ( BFS가 주어진 노드로부터 가까운 것부터 방문하기 때문에)==

  

# DP(동적프로그래밍)

완전탐색이 아닌 재귀(or반복문)로 문제를 풀때 메모리를 활용하여 ==중복된 하위문제(subproblem의 계산값)를 저장하여 저장공간을 쓰되 시간을 줄이는 방법==

subproblem을 해결하는 최적해법으로 원래 problem의 최적해법을 구할수 있다.

==문제에 최대,최소, 방법의 가짓수 + 미래의 계산이 앞선 계산결과에 영향을 받을때(분할정복 문제가 아닐때) DP를 떠올리면 좋다==

점화식(재귀관계식)+base case

**일반 재귀함수**

def recursion(n):

if n == 1:

return 1

  

return recursion(n-1) + rescursion (n-2)

  

**DP 활용 ver (top-down방식) 재귀, memorization 방식**

memo = {}

def recursion(n):

if n == 1:

return 1

  

if n not in memo:

memo[n] = recursion(n-1) + rescursion (n-2)

==return memo[n]==

  

**DP 활용 ver (bottom-up방식) 반복문 iteration 방식(DP table,tablulation 방식)**

memo = {}

def recursion(n):

if n == 1:

return 1

  

for i in range(2, n+1): \#2부터 n까지

memo[n] = memo[i-1] + memo[i-2]

return memo[n]

  

# 튜플 정렬(lambda 활용)

lambda 매개변수들 : 식

ex) lambda x : x+10

x를 파라미터로 하고 x+10을 리턴해주는 익명함수

(lambda x : x+10)(1) // 1을 인자로 준것

  

arr.sort(key = lambda x:(-x[0],x[1]))

튜플 첫번째 원소로는 내림차순 같을땐, 두번째 원소로는 오름차순

  

### sort(어레이 직접수정) 와 sorted(어레이 리턴) 차이

+arr.sort 이고 sorted(arr) 이다 ㅋㅋ

  

  

match (n):

case (1) :ㄴ

### **case문은 아래처럼 여러 개를 하나로 합칠 수도 있습니다.**

> case 401 | 403 | 404:

근데 버전이 3.10이라 프로그래머스에서는 안되네

그냥 elif n == 401 or n == 403 or 404

  

**while True:**

  

  

if (four, direction) in {("s", "S"), ("w", "L"), ("e", "R")}:

이렇게 짜기

if four == s or w or e 이렇게 짜면 안먹음 ㅋㅋ

[[1일차 백준 (브론즈1)]]

[[2일차 백준]]

[[3일차 백준]]

[[4일차 백준(실버5 진입)]]

[[5일차 백준]]

[[6일차 백준(Oct 1)]]

[[7일차 백준]]

[[8일차 백준]]

[[9일차 백준]]

[[10일차 백준]]

[[11일차 백준]]

[[12일차 백준]]

[[13일차 백준]]

[[14일차 백준]]

[[15일차 백준]]

[[16일차 백준]]

[[17일차 백준]]

[[18일차 백준]]

[[19일차 백준]]

[[20일차 백준]]

[[21일차 백준]]

[[22일차 백준]]

[[23일차 백준]]