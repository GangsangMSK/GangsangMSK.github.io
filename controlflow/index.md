# [Swift] ControlFlow(제어문)

## For-In Loops

for-in 반복문은 컬렉션 또는 숫자 범위 내에 있는 목록을 반복한다.

```Swift
for 상수명 in 컬렉션 또는 범위 {
    // 실행될 코드
}
```

'상수명'은 반복문이 돌면서 컬렉션 또는 범위에서 가져온 항목을 담게 될 상수이다.

'컬렉션 또는 범위'는 반복문이 반복되면서 현재의 항목을 참조한다.

문자열 값들의 배열이거나 범위 연산, 문자들로 구성된 문자열일 수 있다.

```Swift
for index in 1...5 {
    print(index)
} // index라는 이름의 상수에 현재 항목이 할당되면서 시작
// 1 2 3 4 5
```
```Swift
for _ in 1...5 {
    print("Hello") // _로 참조체 생략 가능
}
// Hello Hello Hello Hello Hello
```
```Swift
// 배열의 요소 접근
let names = ["A", "B", "C", "D"]
for name in names {
    print(name)
}
// A B C D
```
```Swift
let numberOfLegs = ["Spider": 8, "Ant": 6, "Dog": 4]
//dictionary는 key:value형식의 배열
for (animalName, legCount) in numberOfLegs {
    print("\(animalName)s have \(legCount) legs")
}
// Spiders have 8 legs
// Ants have 6 legs
// Dogs have 4 legs

//dictionary에는 순서가 없어, 출력되는 순서는 매번 다를 수 있다.

```

***

**아래와 같은 C 스타일의 for문은 Swift 3에서 없어졌다.**
```Swift
for 초기화; 조건식; 증감식 {
    // 실행될 구문
}

for var i = 0; i < 10; i+=1 {  // for i in 0..<10 로 수정해야 함
   print(i)
}  //error: C-style for statement has been removed in Swift 3
```

## While Loops 

for 반복문은 몇 번 정도 반복해야 할지를 이미 아는 경우에 사용하기 적합하다. 

어떠한 조건이 되기 전에 대체 몇 번 정도 반복해야 할지를 알 수는 없지만 그 조건을 만족할 때까지는 반복해야 하는 경우 while 반복문 사용한다.

지정된 조건을 만족할 때까지 작업을 반복한다.

```Swift
while 조건식 {
    // 구문
}
```

***

```Swift
var myCount = 0
while myCount < 1000 {
   myCount+=1
}
print(myCount)
// myCount 변수가 1000보다 크지 않을 때까지 반복, 1000이 되는 시점에 반복문이 종료된다.
```

## Repeat-While

다른 언어의 do-while문과 유사한 반복문이다.

```Swift
repeat {
    // 구문
} while 조건식
```

***

While문과는 다르게 최소 한번이상 구문을 실행하고, 조건이 거짓일 때까지 반복한다.

```Swift
var i = 10
repeat {
  i=i-1
  print(i)   //출력 결과
} while (i > 0)
```

## Conditonal Statements

Swift에서는 두가지 조건문을 제공한다.

### IF

다른 프로그래밍 언어들과는 다르게, Swift에서는 if 문 다음의 실행 코드가 한 줄이라도 중괄호({})를 필수적으로 사용해야 한다. 

기본적으로 ‘Boolean 표현식’이 참(true)으로 판단되면 중괄호로 감싸인 코드 실행되고 거짓(false)이면 중괄호로 감싸인 코드는 건너뛴다.

사용법으로는 아래와 같다.

***
if만 사용한 경우
```Swift
if Boolean 표현식 {
    // Boolean 표현식이 참일 경우 수행될 구문
}
```

***
if, else를 사용한 경우
```Swift
if Boolean 표현식 {
    // 표현식이 참일 경우 실행되는 구문
}
else {
    // 표현식이 거짓일 경우 실행되는 구문
}
```

***
if, else if, else를 사용한 경우
```Swift
if Boolean 표현식 {
    // 표현식이 참일 경우 실행되는 구문
}
else if Boolean 표현식 {
    // 선행되는 표현식이 거짓일 경우, 표현식이 참일 경우 실행되는 구문
}
else {
    // 표현식이 거짓일 경우 실행되는 구문
}
```

***
if, else if를 사용한 경우
```Swift
if Boolean 표현식 {
    // 표현식이 참일 경우 실행되는 구문
}
else if Boolean 표현식 {
    // 선행되는 표현식이 거짓일 경우, 표현식이 참일 경우 실행되는 구문
}
```

### Switch

Swift에서의 Switch문의 기본 사용방법이다.

```Swift
switch (some value to consider) { 
case (value 1):
    (respond to value 1)
case (value 2),
     (value 3):
    (respond to value 2 or 3)
default:
    (otherwise, do something else)
}
```
```Swift
let someCharacter: Character = "z"
switch someCharacter {
case "a":
    print("The first letter of the alphabet")
case "z":
    print("The last letter of the alphabet")
default:
    print("Some other character")
}
// Prints "The last letter of the alphabet"
}
```
### No Implicit Fallthrough

### Interval Matching

### Tuples
![1](https://docs.swift.org/swift-book/_images/coordinateGraphSimple_2x.png)
### Where

### Value Bindings

### Compound Cases

## Control Transfer Statements

### Countinue

### Break

#### Break in a Loop Statement

#### Break in a Switch Statement

### Fallthrough

### Labeled Statements

## Early Exit


## 참고자료

[iOS 1주차-9 : 제어문(for-in, while, repeat~while, break, continue, if, guard, switch, where, fallthrough)](https://www.youtube.com/watch?v=3QKVkZj_Pzk&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=11)

[The Swift Programming Language - ControlFlow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)

[The Swift Programming Language(한국어) - 제어문(ControlFlow)](https://jusung.gitbook.io/the-swift-language-guide/language-guide/05-control-flow#for-in-for-in-loops)
