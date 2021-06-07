# 파이썬 기초 공부

**파이썬은 블록을 표현하기 위해 들여쓰기를 함 (다른 언어에서는 스코프를 주로 사용함)**

**주석을 달기 위해선 #을 사용한다**

---

### 자료형

일반적으로 int,float,bool,string으로 다른 언어들과 유사하나 특이하게 none (Null과 같은 개념)과 복소수 개념이 존재한다

#### List

파이썬의 List는 다양한 타입을 가질 수 있으며 자유롭게 확장 가능한 **동적 배열이다**

#### Tuple

파이썬의 Tuple은 수정이 불가능한 List를 의미한다

#### 변수 선언

파이썬은 별 다른 변수의 선언 과정이 필요하지 않다

**이름=값**만으로 변수의 선언이 가능하다

```python
a = 10
```

**문자열**의 경우 **큰따옴표(")와 작은 따옴표(')** 모두 사용 가능하다

```python
a="me"
```

**list**를 선언할 때에는 대괄호([])를 사용한다

```python
animal=['pig','cow','dog']
```

**엔터는 \n을 사용한다.**

---

### 연산자

#### 산술연산자

기본적인 +, -, /, *, % 외에도 ** (제곱), // (소숫점 이하를 버리는 나눗셈), divmode(x,y) (나눗셈의 몫과 나머지를 모두 표시) 등이 있다

#### 비교연산자

다른 언어와 유사하게 ==, !=, <=, >= 등을 사용한다

#### 논리 연산자

and, or, not 을 사용한다 (Bool 자료형에 해당)

#### 비트연산자

비트단위 연산자

&, |,  ^, << 등을 사용한다

#### 그 외 연산자

- a in b : a가 b에 해당되는지 확인하여 Bool 값을 반환한다

- a not in b : a가 b에 해당되지 않는지 확인하여 Bool 값을 반환한다

- a is b : a와 b가 동일한지 확인하여 Bool 값을 반환한다

#### list 메서드

```python
mList = ['a',123,'abc',18.5]
mList.append('xyz') # list의 맨 뒤에 요소를 추가한다
mList[1] = 5 # list의 1번 인덱스의 값을 5로 바꾼다
del mList[5] # list의 5번 인덱스의 값을 삭제한다
mList.index(123) # 해당 요소의 인덱스를 반환한다
mList.count('a') # list안 해당 요소의 개수를 반환한다의
```

#### 문자열 메서드

```python
a = 'Someone Like You'
a * 2 # a를 두번 출력
len(a) # a의 길이를 출력
a[1:5] # a의 인덱스 1번부터 5번까지를 출력
a.count('o') # a에서 'o'의 개수를 반환
a.find('m') # 가장 먼저 나온 m의 인덱스를 반환 존재하지 않다면 -1을 반환
a.upper() + a.lower() # a를 대문자로, 소문자
a.replace('You','me') # You를 me로 대체
a.split('e') # e를 기준으로 구분, 공백시 띄어쓰기
```

### 제어문

#### while

while 뒤의 조건이 만족할 때 까지 반복한다

```python
a = 1
while a < 10:
    print a
    a = a + 1
```

#### for

변수 하나를 선언하여 해당 범위만큼 실행한다

```python
for i in range(10):
    print i
```

**range(10)은 0부터 9까지의 10개의 범위를 의미한다**

**in 배열명**을 사용하여 배열 안을 순회할 수도 있다

```python
animal = ['pig', 'dog', 'cat']
for i in animal:
    print i
```

#### break & continue

break는 가장 가까운 반복문을 종료, continue는 밑의 코드를 실행하지 않고 가장 가까운 반복문으로 다시 돌아간다

#### if 

제시된 조건이 참(True)이라면 같은 블록의 코드를 실행한다

```python
if(1>10):
    print 'true'
elif(1==10):
    pass
else:
    print 'false'
```

다른 언어와 다르게 외의 조건을 확인할 때에 if else 대신 **elif**를 사용한다

아무 문항을 실행하고 싶지 않을 때엔 **pass** 키워드를 사용한다

### 함수

**def 함수명(파라미터) : return 값**의 형식으로 쓰인다

사용할 때에는 **함수명(파라미터)**의 형식을 사용한다

```python
def f1(n1,n2):
    return n1+n2
```

#### 기본값 파라미터

파라미터의 값이 넘어오지 않을 경우 파라미터의 기본값을 정해줄 수 있다

```python
def f1(n1,n2,n3=3):
```

#### 가변길이 파라미터

파라미터의 수가 정해져있지 않을 경우. 파라미터 앞에 ***** 을 사용하여 가변 길이임을 명시할 수 있다 

```python
def f1(*n):
```

### Class

**class 이름** 의 형식으로 class를 선언할 수 있다.

class는 attribute (속성)과 method (메서드)를 포함한다.

파이썬에서는 **별도의 접근제한자를 갖지 않는다 (모두 public 취급)** 

**__class명** 을 사용하면 **private** 취급한다

```python
class c1:
    n = 3  # class 변수

    def __init__(self, n2, n3):  # 초기자
        self.n2 = n2
        self.n3 = n3

    @classmethod  # class 메서드
    def m1(cls, m):
        return cls.n + m

    @staticmethod  # 정적 메서드
    def m2(n, m):
        return n + m


class c2(c1): # 상속
    @staticmethod
    def m3():
        return c1.m2(1, 2)
      
c1 = c1(3, 4) # 인스턴스 생성
```

#### 변수

1. **class 변수**

class 변수는 instance 생성에 따라 바뀌지 않는 **class 내부의 변수**를 말한다

2. **instance 변수**

Instance 변수는 초기화 시점에서 정해지는 **instance마다 다르게 부여되는 변수**를 말한다

#### 메서드

1. **초기자**

초기자는 인스턴스 생성 시 가장 먼저 실행되는 함수로 instance 변수를 선언하고 초기 설정을 하는 데 사용된다

2. **instance 메서드**

instance 메서드는 파라미터로 self를 갖고 **self.** 을 통해 instance 변수와 class 변수에 접근 가능하다

3. **class 메서드**

class 메서드는 **@classmethod**를 통해 class 메서드임을 명시하며 파라미터로 cls를 갖고 **cls.** 을 통해 class변수에 접근 가능하다

4. **static 메서드**

static 메서드 (정적 메서드)는 **@staticmethod** 를  통해 정적 메서드임을 명시하며 class 내의 어떤 변수에도 접근할 수 없다

#### 상속

class를 생성할 때, **class명(부모 class명):** 의 형식으로 상속받을 수 있다

자식 class는 부모 class의 멤버를 호출할 수 있다

#### instance 생성

**class명(파라미터)** 의 형식으로 생성한다 







---

#### 공부한 곳 

파이썬 더 쉽게, 더 깊게 (저자 : 츠지 신고)

예제로 배우는 파이썬 프로그래밍 (http://pythonstudy.xyz)

점프 투 파이썬 위키 독스 (https://wikidocs.net/book/1)
