# [Swift] Operator(연산자)

## Assingnment Operator (기본 할당 연산자)

할당 연산자는 두 개의 피연산자를 가진다.

왼쪽에 있는 피연산자는 값이 할당되는 변수 또는 상수이며, 오른쪽에 있는 피연산자는 할당할 값을 쓴다.

오른쪽 피연산자는 주로 산술식 또는 논리식을 수행하는 표현식이며, 그 결과는 왼쪽 피연산자인 변수나 상수에 할당한다.

```Swift
let a = 10
var b = 20
b = a
// b에 10이 들어간다.

let (x, y) = (1, 2) 
// x는 1이고, y는 2이다.
```

## Arithmetic Operators (산술 연산자)

보통 두 개의 피연산자를 받는 이항(binary) 연산자이다.

```Swift
*	곱셈
/ 	나눗셈
+ 	덧셈
- 	뺄셈
% 	나머지 연산

x = y * 10 + z - 5 / 4
// 하나의 표현식 안에 여러 개의 연산자를 사용할 수 있음
```

***

예외에는 값이 음수임을 가리키는 단항 마이너스 연산자(unary negative operator)인 ‘ - ’ 가 있다.

```Swift
var x = -10 // 변수 x에 -10을 할당하기 위해 사용되는 단항 - 연산자
// - (단항) 변수 또는 표현식의 값을 음수로 만듦
```

## Compound Assignment Operators (복합 할당 연산자)

C와 마찬가지로, Swift는 할당(=)을 다른 작업과 결합하는 복합 할당 연산자를 제공한다.


```Swift
x += y // == x = x + y
```

x += y라는 표현은 a = a + 2의 축약한 것이다. 추가와 할당은 두 작업을 동시에 수행하는 하나의 연산자로 결합할 수 있다.

```Swift
x += y 	x와 y를 더하고 그 결과를 x에 할당
x -= y 	x에서 y를 빼고 그 결과를 x에 할당
x *= y 	x와 y를 곱하고 그 결과를 x에 할당
x /= y 	x를 y로 나누고 그 결과를 x에 할당
x %= y 	x를 y로 나눈 나머지를 x에 할당
x &= y 	x와 y의 bit AND 연산 결과를 x에 할당
x |= y 	x와 y의 bit OR 연산 결과를 x에 할당
```

### Increment & Decrement Operator (증가 & 감소 연산자)

```Swift
// 다음과 같이 사용한다.
x = x + 1 // x 변수의 값을 1 증가시킴
x = x - 1  // x 변수의 값을 1 감소시킴

// C에서 사용되는 ++, -- 연산자는 Swift 3에서 없어졌다.
x++ // Cannot find operator '++' in scope; did you mean '+= 1'?
x-- // Cannot find operator '--' in scope; did you mean '-= 1'?
//라는 오류가 난다.
```

## Comparison Operators (비교 연산자)

비교의 결과 값으로 Boolean 값을 반환한다.

```Swift
var result: Bool?
var x = 10
var y = 20

result = x < y
//true

x == y 	x와 y가 같다면 true를 반환
x > y 	x가 y보다 크면 true를 반환
x >= y 	x가 y보다 크거나 같다면 true를 반환
x < y 	x가 y보다 작다면 true를 반환
x <= y 	x가 y보다 작거나 같다면 true를 반환
x != y 	x와 y가 같지 않다면 true를 반환
```

## Ternary Conditional Operator (삼항 연산자)

비교 연산을 빠르게 하기 위해 삼항 연산자를 지원한다.

> [조건] ? [참 표현식] : [거짓 표현식]

삼항 연산자는 [조건] 부분을 계산하여 참(true) 혹은 거짓(false)을 확인하여 결과가 참이면 [참 표현식] 부분이 실행되며, 거짓이면 [거짓 표현식] 부분을 수행한다.

```Swift
if question {
    answer1
} else {
    answer2
}

//삼항 연산자로의 변환
question ? answer1 : answer2
```

## Nil-Coalescing Operator (닐 병합 연산자)

옵셔널변수 ?? nil일 때 할당되는 값이다.

옵셔널 변수의 값이 nil이면 ?? 다음 값으로 할당된다.

옵셔널 변수의 값이 nil이 아니면 언래핑된 값이 나온다.


```Swift
let defaultColor = "black"
var userDefinedColor: String? // defaults to nil

var myColor = userDefinedColor ?? defaultColor // nil이므로 defaultColor인 black으로 할당됨 

print(myColor) // black

userDefinedColor = "red"

myColor = userDefinedColor ?? defaultColor //nil이 아니므로 언래핑된 red가 할당됨
print(myColor) // red
// 중요! optional(red)가 아니다.
```

## Range Operators (범위 연산자)

### Closed Range Operator (닫힌 범위 연산자)

* 닫힌 범위 연산자(a...b)는 a에서 b까지 실행되는 범위를 정의하고 값 a와 b를 포함한다. 

    * 단 a의 값은 b보다 크지 않아야 한다.

* 닫힌 범위 연산자는 for-in 루프와 같이 모든 값을 사용하려는 범위를 반복할 때 유용한다.

```Swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```

### Half-Open Range Operator (반 열린 범위 연산자)

* 반 열린 범위 연산자(a..<b)는 a에서 b까지 실행되지만 b를 포함하지 않는 범위를 정의한다. 

    * 닫힌 범위 연산자와 마찬가지로, a의 값은 b보다 크지 않아야 한다.

* 첫 번째 값을 포함하지만 최종 값은 포함하지 않기 때문에 반쯤 열려 있다고 한다.

```Swift
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

### One-Sided Ranges (단방향 범위)

* 아래와 같은 형태로 범위의 시작 혹은 끝만 지정해 사용하는 범위 연산자이다.

* 지정한 시작 값 혹은 끝 값은 범위에 포함된다.

```Swift
let names = ["A", "B", "C", "D"]
   for name in names[2...] {  //[...2], [..<2] 와 같이도 사용가능 하다.
      print(name)
   } 
// C
// D
```

## Logical Operators (논리 연산자)

### NOT Operator (!)

* 불리언 값 또는 표현식의 결과를 현재와 반대로 바꿈

```Swift
let flag = true // 변수는 참
let secondFlag = !flag // secondFlag는 거짓으로 설정됨
```

### AND Operator (&&)

논리 AND 연산자(a && b)는 전체 표현식이 참이 되려면 두 값이 모두 참이어야 하는 논리 표현식을 만든다.

```Swift
let id : Bool
let password : Bool

if id && password {
    print("Login success")
}
else {
    print("Login failed")
}
// id = true, password = true 일 경우 Login success
// id = true, password = false 일 경우 Login failed
// id = false, password = true 일 경우 Login failed
// id = false, password = false 일 경우 Login failed
```

첫번 쨰 값이 false 면, 표현식이 true 가 될 수 없기에 두번째 값은 생략될 것이다. 이 것을 **short-circuit evaluation** 이라고 한다.

### OR Operator (||)

논리 OR 연산자(a || b)는 전체 표현식이 참이 되려면 두 값 중 하나만 true여야 하는 논리 표현식을 만드는 데 사용합니다.

```Swift
let id : Bool
let password : Bool

if id || password {
    print("Login success")
}
else {
    print("Login failed")
}
// id = true, password = true 일 경우 Login success
// id = true, password = false 일 경우 Login success
// id = false, password = true 일 경우 Login success
// id = false, password = false 일 경우 Login failed
```


### Combining Logical Operators (논리 연산자의 결합)

두 개 이상의 논리 연산자를 결합해 사용할 수 있다.

왼쪽의 표현이 우선순위가 높아 먼저 계산된다.

```Swift
if enteredDoorCode && passedRetinaScan || hasDoorKey || knowsOverridePassword {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Prints "Welcome!"
```

### Explicit Parentheses (명시적 괄호)

논리 연산자의 적용 우선 순위를 연산자에 맡지기 않고 명시적으로 괄호를 사용해 계산 순서를 지정할 수 있다.

```Swift
if (enteredDoorCode && passedRetinaScan) || hasDoorKey || knowsOverridePassword {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Prints "Welcome!"
```
아니 저도 아무것도 모르는데 저 어캄? 저 암것도 모름

## 참고자료

[Smile Han - iOS 1주차-8 : Swift 연산자](https://www.youtube.com/watch?v=fCutR0YgUng&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=10)

[The Swift Programming Language - Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)

[Apple Developer Documentation - Operator Declarations](https://developer.apple.com/documentation/swift/operator-declarations)
