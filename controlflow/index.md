# [Swift] ControlFlow(제어문)

## For-In Loops (For-In문)

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

## While Loops (While문)

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

## Conditonal Statements (조건적 구문)

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

C/C++, Objective-C와 달리 case문 다음에 break 문을 포함할 필요가 없다.

Swift는 일치하는 case문을 만나면 자동으로 빠져나온다. 

case별로 빠져 나가지 않고 아래로 계속 내려가게 하려면 [fallthrough](#fallthrough) 문을 사용할 수 있다.

***

case 안에는 최소 하나 이상의 구문이 존재 해야한다.

존재하지 않을 경우, 아래와 같이 오류가 발생한다.

```Swift
let anotherCharacter: Character = "a"
switch anotherCharacter {
case "a": // Invalid, case문에 body가 없으므로 에러가 발생한다.
case "A":
    print("The letter A")
default:
    print("Not the letter A")
}
// 컴파일 에러 발생!
```

***

case 안에 콤마(,)로 구분해서 복수의 case 조건을 [혼합(compound Cases)](#compound-cases)해 사용할 수 있습니다.

```Swift
let anotherCharacter: Character = "a"
switch anotherCharacter {
case "a", "A":
    print("The letter A")
default:
    print("Not the letter A")
}
// Prints "The letter A"
```

### Interval Matching

switch문에서 case에 숫자의 특정 범위를 조건으로 사용할 수 있다.

```Swift
let approximateCount = 62
let countedThings = "moons orbiting Saturn"
let naturalCount: String
switch approximateCount {
case 0:
    naturalCount = "no"
case 1..<5:
    naturalCount = "a few"
case 5..<12:
    naturalCount = "several"
case 12..<100:
    naturalCount = "dozens of"
case 100..<1000:
    naturalCount = "hundreds of"
default:
    naturalCount = "many"
}
print("There are \(naturalCount) \(countedThings).")
// Prints "There are dozens of moons orbiting Saturn."
```

### Tuples

튜플을 사용하여 동일한 switch문에서 여러 값을 테스트할 수 있다.
튜플의 각 요소는 다른 값이나 범위연산자, 밑줄 문자(_)를 조건으로 사용할 수 있다.

```Swift
let somePoint = (1, 1)
switch somePoint {
case (0, 0):
    print("\(somePoint) is at the origin")
case (_, 0):
    print("\(somePoint) is on the x-axis")
case (0, _):
    print("\(somePoint) is on the y-axis")
case (-2...2, -2...2):
    print("\(somePoint) is inside the box")
default:
    print("\(somePoint) is outside of the box")
}
// Prints "(1, 1) is inside the box"
```

### Value Bindings

switch문에서 각각의 case문에 임시적으로 상수 또는 변수와 일치하는 값을 선언할 수 있다.

값이 case 본문 내의 임시 상수 또는 변수에 바인딩되기 때문에 값 바인딩이라고 한다.

```Swift
let anotherPoint = (2, 0)
switch anotherPoint {
case (let x, 0):
    print("on the x-axis with an x value of \(x)")
case (0, let y):
    print("on the y-axis with a y value of \(y)")
case let (x, y):
    print("somewhere else at (\(x), \(y))")
}
// Prints "on the x-axis with an x value of 2"
```
### Where

switch, if 조건문에서 where를 사용하여 조건을 추가할 수 있다.

***

```Swift
let yetAnotherPoint = (1, -1)
switch yetAnotherPoint {
case let (x, y) where x == y:
    print("(\(x), \(y)) is on the line x == y")
case let (x, y) where x == -y:
    print("(\(x), \(y)) is on the line x == -y")
case let (x, y):
    print("(\(x), \(y)) is just some arbitrary point")
}
// Prints "(1, -1) is on the line x == -y"
```

***

```Swift
var numbers: [Int] = [1, 2, 3, 4, 5]
for num in numbers where num > 3 {
    print(num)
}
// 4 5
```

### Compound Cases

동일한 본문을 공유하는 여러 case는 각 조건 사이에 쉼표(,)로 결합하여 사용할 수 있다. 

조건이 길 경우, 개행할 수 있다.

```Swift
let someCharacter: Character = "e"
switch someCharacter {
case "a", "e", "i", "o", "u":
    print("\(someCharacter) is a vowel")
case "b", "c", "d", "f", "g", "h", "j", "k", "l", "m",
     "n", "p", "q", "r", "s", "t", "v", "w", "x", "y", "z":
    print("\(someCharacter) is a consonant")
default:
    print("\(someCharacter) isn't a vowel or a consonant")
}
// Prints "e is a vowel"
```

***

Compound Cases 에서도 Value Bindings을 할 수 있다.

```Swift
let stillAnotherPoint = (9, 0)
switch stillAnotherPoint {
case (let distance, 0), (0, let distance):
    print("On an axis, \(distance) from the origin")
default:
    print("Not on an axis")
}
// Prints "On an axis, 9 from the origin"
```
## Control Transfer Statements (제어 전송문)

제어 전송문은 한 코드에서 다른 코드로 제어를 전송하여 코드가 실행되는 순서를 변경한다.

Swift에는 다음과 같은 5가지의 제어 전송문을 사용한다.

* continue

* break

* fallthrough

* return

* throw

### Countinue

continue문은 현재 loop를 중단하고 다음 loop를 수행하게 만든다.

```Swift
let puzzleInput = "great minds think alike"
var puzzleOutput = ""
let charactersToRemove: [Character] = ["a", "e", "i", "o", "u", " "]
for character in puzzleInput {
    if charactersToRemove.contains(character) {
        continue
    }
    puzzleOutput.append(character)
}
print(puzzleOutput)
// Prints "grtmndsthnklk"
```
### Break

Break문은 전체 제어 흐름문의 실행을 즉시 종료합니다. 

Break문은 스위치 또는 루프 문의 실행을 종료하려는 경우, 스위치 또는 루프 문 내부에서 사용한다.

#### Break in a Loop Statement

```Swift
let puzzleInput = "great minds think alike"
var puzzleOutput = ""
let charactersToRemove: [Character] = ["a", "e", "i", "o", "u", " "]
for character in puzzleInput {
    if charactersToRemove.contains(character) {
        break
    }
    puzzleOutput.append(character)
}
print(puzzleOutput)
// Prints "gr"
```

#### Break in a Switch Statement

```Swift
let numberSymbol: Character = "三"  // Chinese symbol for the number 3
var possibleIntegerValue: Int?
switch numberSymbol {
case "1", "١", "一", "๑":
    possibleIntegerValue = 1
case "2", "٢", "二", "๒":
    possibleIntegerValue = 2
case "3", "٣", "三", "๓":
    possibleIntegerValue = 3
case "4", "٤", "四", "๔":
    possibleIntegerValue = 4
default:
    break
}
if let integerValue = possibleIntegerValue {
    print("The integer value of \(numberSymbol) is \(integerValue).")
} else {
    print("An integer value couldn't be found for \(numberSymbol).")
}
// Prints "The integer value of 三 is 3."
```

### Fallthrough

C/C++, Objective-C와 달리 break문을 사용하지 않고 조건이 충족되면 자동으로 break된다.

fallthrough 를 사용하면 이 자동으로 break가 사용되는 것을 막는 효과가 있다.

```Swift
let integerToDescribe = 5
var description = "The number \(integerToDescribe) is"
switch integerToDescribe {
case 2, 3, 5, 7, 11, 13, 17, 19:
    description += " a prime number, and also"
    fallthrough
default:
    description += " an integer."
}
print(description)
// Prints "The number 5 is a prime number, and also an integer."
```

### Labeled Statements

아래와 같은 형태로 label 이름과 while 조건을 넣어 특정 구문을 실행하는 구문으로 사용한다.

```Swift
(label name): while (condition) {
   (statements)
}
```

switch 문과 함께 다음과 같이 사용할 수 있다.

```Swift
gameLoop: while square != finalSquare {
    diceRoll += 1
    if diceRoll == 7 { diceRoll = 1 }
    switch square + diceRoll {
    case finalSquare:
        // diceRoll will move us to the final square, so the game is over
        break gameLoop
    case let newSquare where newSquare > finalSquare:
        // diceRoll will move us beyond the final square, so roll again
        continue gameLoop
    default:
        // this is a valid move, so find out its effect
        square += diceRoll
        square += board[square]
    }
}
print("Game over!")
```

## Early Exit

* guard문은 swift 2에 도입된 구문이다.

* guard문은 표현식이 거짓(false)으로 판단될 경우에 수행될 else 절을 반드시 포함해야 한다.

    * else 절에 속한 코드는 제어 흐름문(return, break, continue, throw 구문)을 반드시 포함해야 함

* guard문을 이용해 특정 조건을 만족하지 않으면 다음 코드를 실행하지 않도록 방어코드를 작성할 수 있다.

```Swift
func greet(person: [String: String]) {
    guard let name = person["name"] else {
        return
    }

    print("Hello \(name)!")

    guard let location = person["location"] else {
        print("I hope the weather is nice near you.")
        return
    }

    print("I hope the weather is nice in \(location).")
}

greet(person: ["name": "John"])
// Prints "Hello John!"
// Prints "I hope the weather is nice near you."
greet(person: ["name": "Jane", "location": "Cupertino"])
// Prints "Hello Jane!"
// Prints "I hope the weather is nice in Cupertino."
```

## 참고자료

[iOS 1주차-9 : 제어문(for-in, while, repeat~while, break, continue, if, guard, switch, where, fallthrough)](https://www.youtube.com/watch?v=3QKVkZj_Pzk&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=11)

[The Swift Programming Language - ControlFlow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)

[The Swift Programming Language(한국어) - 제어문(ControlFlow)](https://jusung.gitbook.io/the-swift-language-guide/language-guide/05-control-flow#for-in-for-in-loops)
