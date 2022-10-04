# [Swift Practice] in 22/10/04


# if문

```Swift
var x = 1 
while true { 
    if x > 5 {
        break
    } //조건(x>5)이 참일 때 실행(break)
    print(x) //1 2 3 4 5
    x = x + 1 
}
```

# guard else문

```Swift
var x = 1 
while true { 
    guard x < 10 else { 
        break 
    }//조건(x<10)이 거짓일 때 실행(break)  
    print(x) //1 2 3 4 5 6 7 8 9, 조건(x<10)이 참일 때 실행 
    x = x + 1 
}
```

if문은 조건 다음에 있는 구문이 참일 때 실행되지만, guard문은 조검 다음에 있는 구문이 거짓일 떄 실행된다.

***

# switch case문

```Swift
var value = 7
switch value
{
    case 0:
        print("영")
    case 1:
        print("일")
    case 2:
         print("이")
    case 3:
        print("삼")
    default:
        print("4이상")
}
// 4이상
```

***

```Swift
let anotherCharacter: Character = "a" 
switch anotherCharacter { 
    case "a": // Invalid, the case has an empty body 
    case "A": 
        print("The letter A") 
    default: 
        print("Not the letter A") 
}
//error: 'case' label in a 'switch' should have at least one executable statement
```

**case별로 반드시 실행 가능한 구문이 있어야 한다.**

***

```Swift
var value = 9
var days : Int = 0
switch(value)
{
case 1,3,5,7,8,10,12:
     print("31 일입니다")
case 4,6,9,11:
     print("30 일입니다")
case 2:
     print("28 or 29 일입니다")
default:
    print("월을 잘못 입력하셨습니다")
}
//30 일입니다
```

***

```Swift
var temperature = 60
switch (temperature)
{
case 0...49 where temperature % 2 == 0:
    print("Cold and even")
case 50...79 where temperature % 2 == 0:
    print("Warm and even")
case 80...110 where temperature % 2 == 0:
    print("Hot and even")
default:
    print("Temperature out of range or odd")
}
//warn and enven
```

```Swift
var numbers: [Int] = [1, 2, 3, 4, 5]
for num in numbers where num < 2 {
    print(num)
}
// 1
```
where문을 통해 부가적인 조건을 제공한다.

***

```Swift
let weight = 100.0
let height = 170.0
let bmi = weight / (height*height*0.0001) // kg/m*m 
var body = "" 

switch bmi {
case 40...:
    body = "3단계 비만"
case 30...:
    body = "2단계 비만"
case 25...:
    body = "1단계 비만"
case 18.5...:
    body = "정상"
default:
    body = "저체중"
}

print("BMI:\(bmi), 판정:\(body)")
//BMI:34.602076124567475, 판정:2단계 비만
```

***

# fallthrough문

```Swift
var value = 2
switch (value)
{
case 4:
    print("4")
    fallthrough 
case 3:
    print("3")
    fallthrough 
case 2:
    print("2")
    fallthrough 
default:
    print("1")
}
// 4 3 2 1
```
fallthrough를 사용하면 조건에 상관없이 통과하여 케이스 안에 있는 구문을 실행한다.

***

# 함수

* parameter

    * 함수를 정의할 떄 받는 인자

    * 값을 넘겨 받는 매개변수

    * 형식 매개변수(formal parameter)

* argument 

    * 함소를 호출할 때 주는 인수
    
    * 값을 넘겨 주는 매개변수
    
    * 실 매개변수(actual parameter)

* 함수를 Swift Class 내에서 선언하면 메서드(method)라고 한다.

```Swift
func sayHelloWorld() -> Void { //리턴 값이 없을 경우 (-> Void) 생략가능
    print("Hello World!")
}
sayHelloWorld() //호출
//Hello World!
```

```Swift
func add(x: Int, y: Int) -> Int {
    return x + y
}
print(type(of:add))
//(Int, Int) -> Int

print(add(x: 5, y: 10))
// 15
let output = add(x: 10, y: 20)
print(output)
// 30
```

Swift에서 자료형은 () -> () 으로 쓰는 것이 기본이다.

***

스위프트에서 함수를 만드는 4가지 방법은 다음과 같다.

***

```Swift
func add(first x: Int, second y: Int) -> Int { // argument label 
    return x + y
}
print(add(first: 5, second: 10)) // argument label 이 있을 경우 label명으로 argument를 줘야한다.
// 15
// 함수명 : add(first:second:)
```
***
```Swift
func add(x: Int, y: Int) -> Int { // overloading 사용 시
//외부 매개변수명(argument label)을 생략하면 내부 매개변수명이 외부 매개변수명까지 겸한다.
    return x + y
}
print(add(x: 3, y: 5))
// 8
// 함수명 : add(x:y:)
```
***
```Swift
func add(_ x: Int, _ y: Int) -> Int { 
    return x + y
}
print(add(5, 10))
// 함수명 : add(_:_:)
```
***
```Swift
func add(_ x: Int, with y: Int) -> Int { // 이 경우를 가장 많이 사용한다.
    return x + y
}
print(add(5, with: 10))
// 함수명 : add(_:with:)
```

***

```Swift
func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int
//자료형: (UITableView, Int) -> Int 
//함수명: tableView(_:numberOfRowsInSection:)

func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell
// (UITableView, IndexPath) -> UITableViewCell
// tableView(_:cellForRowAt:)
```

***

```Swift
func print(
    _ items: Any...,
    separator: String = " ",
    terminator: String = "\n" //default argument, 전달받은 값이 없을 경우 디폴트 값을 사용
)
```

***

```Swift
func converter(length: Float) -> (yards: Float, centimeters: Float, meters: Float) { // 인자 값을 튜플로 주기
    let yards = length * 0.0277778
    let centimeters = length * 2.54
    let meters = length * 0.0254
    return (yards, centimeters, meters) // ()생략 불가
}
var lengthTuple = converter(length:30.8)
print(lengthTuple)  //(yards: 0.85555625, centimeters: 78.231995, meters: 0.78231996)
print(lengthTuple.yards) //0.85555625
print(lengthTuple.centimeters) //78.231995
print(lengthTuple.meters) //0.78231996
```

```Swift
func sss(x : Int, y : Int) -> (sum : Int, sub : Int, div : Double, mul: Int) {
    let sum = x+y
    let sub = x-y
    let div = Double(x)/Double(y) //같은 자료형만 연산 가능
    let mul = x*y
    return (sum, sub, div, mul)
}
var result = sss(x:10,y:3)
print(result.sum) // 13
print(result.sub) // 7
print(result.div) // 3.3333333333333335
print(result.mul) // 30
```
***

```Swift

func add(num:Int...) -> (Int) { // 가변 매개변수 (...)을 사용
//지정되지 않은 개수의 매개변수가 필요할 때 사용
    var sum = 0
    for nums in num {
        sum += nums
    }
    return sum
}
add(num:1,2,3) //6
add(num:2,2,2,2,2)  //10 
add(num:1,1,1,1,1,1,1,1,1,1) //10 
add(num:1,1,1,1) //4
```

