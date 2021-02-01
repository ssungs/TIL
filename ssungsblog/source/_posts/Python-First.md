---
title: Python First
date: 2021-01-27 12:00:28
tags:[python][string]
---

# Python

## 변수와 인수

def add(a, b) return a + b 에서 a , b 는 변수

print(add(3, 4)) 에서 3 , 4 는 인수

7 > 리턴값(return a + b)

변수에 넣은 값이 인수 > 위 예제에서는 a , b 변수에 3 , 4 라는 인수가 주어짐

 def : 함수를 만들 때 사용하는 예약어

```
def bank(a , b):
    return a + b
print(bank('300', 'Dollor'))
>> 300Dollor
```
## 문자열

### 인덱싱

변수에 적용된 문자열을 번호로 호출

적용된 문자열은 왼쪽부터 0 , 1 , 2 , ... 순서로 읽음

-1은 문자열 가장 오른쪽 즉, 제일 마지막 (-0은 0이므로 첫번째 문자열을 가리킴)

```
a = 'python3'
     0123456
a[0]
>>'p'
a[5]
>>'n'
a[-1]
>>'3'
```

변수에 적용된 문자열을 구간을 나누어 호출

변수[시작번호, 종료번호]

변수의 시작번호부터 종료번호 미만의 문자열을 호출 ( 시작번호 <= 변수 < 종료번호 ) 따라서 종료번호는 포함하지 않고 그 이전의 문자열까지 호출

시작번호와 종료번호가 문자열 마지막 (시작점은 0 , 종료점은 -1) 일 경우에는 생략가능

```
a = 'Python is very easy.'

a[2: 9]
>>'thon is'
a[:13]
>>'Python is ver
a[6:]
>>' is very easy.'
a[-15: 12]
>>'n is ve'
a[2: -3]
>>'thon is very ea'
```

### 슬라이싱

변수에 적용된 문자열을 새로운 변수에 지정하여 나눔

```
a = 'pineapple'

a1 = a[:4]
print(a1)
>>pine
a2 = a[4:]
print(a2)
>>apple
```

중간 문자열 바꾸기

중간 문자열을 바꾸는 것보다 바꿀 문자열 앞과 뒤를 호출하고 바꿀문자와 합치는 형식으로 가능

```
a = pinaapple'
a[:3] + 'e' + a[4:]
>>'pineapple'
```

### 문자열 포매팅


변수에 문자열을 적용할때 문자열 안에 숫자, 문자열, 변수를 삽입하는 방식

%문자 로 표현하며 표현하는 방식으로 이용

%문자에 맞는 타입을 입력해야 오류가 안뜸

%s : 문자열 / 정수, 실수 모두 사용가능

%c : 문자 1개

%d : 정수

%f : 부동소수(실수)

%o : 8진수

%x : 16진수

%% : 문자 % 자체

```
'i like %s' % 'python'
>>'i like python'
'i like %c' % 'c'
>>'i like c'
'i like %d' % 13
>>'i like 13'
'i like %d' % 0.144568
>>'i like 0'
'i like %f' % 0.144568
>>'i like 0.144568
'i like %o' % 101  >>  8진수
>>'i like 145' 
'i like %x' % 101  >>  16진수
>>'i like 145'
'i like %d%%' % 100  >> Literal % : %%만으로는 사용안되고 문자뒤에 % 문자를 표현하고자 할때 사용
2가지 값 넣기
number = 13
birth = 'October'
'My birthday is %d, %S' % (number, birth)
>>'My birthday is 13, October'
포맷 코드와 숫자 함께 사용가능
정렬, 공백, 소수점을 표현하기 위해 사용
'%25s' % 'wow'
>>'                         wow'
'%-10sgood' % 'wow'
>>'wow          good'
'%0.7f' % 0.457845745126
>>'0.4578457'
'5.7f' % 0.457845745126
>>'     0.4578457'
```

### 포맷 함수를 사용한 포매팅

format 함수를 이용하면 문자열 포매팅 예제를 좀 더 발전된 스타일로 지정가능

{ } 안에 함수 순서나 변수를 넣고 .format(변수나 인수) 을 넣어 사용

```
'i like {0}'.format(13)
>>'i like 13'
'i like {0}'.format('blue')
>>'i like blue'
a = 100
'number is {0}'.format(a)
''number is 100'
a = 100
b = '180'
'first number is {0}, second number is {1}'.format(a, b)
>>'first number is 100, second number is 180'
'first number is {first}, second number is {second}'.format(first=100, second=180)
>>'first number is 100, second number is 180'
"{0:<10}".format('hi')
>>'hi        '
"{0:>10}".format('hi')
>>'        hi'
"{0:^10}".format('hi')
>>'    hi    '
"{0:-^10}".format('hi')
>>'----hi----'
y = 12.4512547895465
'{0:0.4f}'.format(y)
>>'12.4513'
'{0:10.4f}'.format(y)
>>'   12.4513'
'{{ wow }}'.format()
>>{ wow }
name = 'kim'
age = 30
f'My name is {name}, age is {age}.'
>>'My name is kim, age is 30.'
f"나는 내년에 {age+1}살이 된다."
>>'나는 내년에 31살이 된다.'
d = {'name1':'kim', 'age1':30}
f'My name is {d["name1"]}, age is {d["age1"]}.'
>>My name is kim, age is 30.'
print(f'{"hi":<10}')  #왼쪽정렬
print(f'{"hi":>10}')  #오른쪽정렬
print(f'{"hi":^10}')  #중앙정렬
>>hi
>>        hi
>>    hi    
print(f'{"hi":-^10}') #공백 채우기
>>----hi----
```

### 문자열 관련 함수들

```
a = 'apple'
a.count('p')    #문자 개수 세기 (.count(찾는 문자))
>>2
b = 'Python is the best choice'
b.find('y')    #문자 위치 찾기1 (.find(찾는 문자))
>>1
b.find('a')      #선언된 문자열 안에 찾는 문자가 없는 경우 -1 출력
>>-1
c = 'Life is too short'      #문자 위치 찾기2 (.index(찾는 문자))
c.index('t')                 #중복된 문자가 있는 경우 앞에 위치 출력
>>8
','.join('abcde')    #문자열 삽입
>>'a,b,c,d,e'
','.join(['a', 'b', 'c', 'd'])     #문자열 삽입 (리스트)
>>'a,b,c,d'
d = 'hello'
d.upper()          #소문자를 대문자로 바꾸기 (.upper()) 전체 문장 대문자로 바꾸기
d                  #함수를 사용해서 바꿨지만 변수로 따로 저장을 하지 않을 경우,
                   #다시 같은 함수를 불러왔을때 변경 전 함수가 호출됨
>>'hello'        
e = 'HELLO'
e.lower()         #대문자를 소문자로 바꾸기 (.lower()) 전체 문장 소문자로 바꾸기
>>'hello'
f = '  wow   '
f.rstrip()        #오른쪽 공백 지우기 (.rstrip())
>>'  wow'
f.lstrip()        #왼쪽 공백 지우기 (.lstrip())
>>'wow  '
f.strip()         #공백 지우기 (.strip())
'wow'
g = 'python is awesome!'
g.replace('awesome!', 'good!')     #문자열 바꾸기 (.replace(바뀌는문자, 바꿀문자))
'python is good!'
h = "I'm so sorry, but i love you."
h.split()      #문자열 나누기 (.split(나눌문자)) 나눌문자를 공백으로 하면 띄어쓰기로 나눔
>>["1'm", "so", "sorry", "but", "i" , "love", 'you.']
h.split(',')     #나눌문자를 지정하면 예시와 같이 나눌문자를 기준으로 문장이 나뉨
>>["I'm so sorry', 'but i love you.]

