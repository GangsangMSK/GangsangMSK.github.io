# [Swift Practice] in 22/10/11

# Function (함수)

```Swift
func add(first x: Int, second y: Int) -> Int {   
    // first, second : argument label
    // x, y : parameter name
    print(#function)  //add(first:second:)  
    return(x+y)
}
let a = add(first:10, second:20)
//add(first:second:)
```

```Swift
func add(_ x: Int, _ y: Int) -> Int {   
    print(#function)  //add(first:second:)  
    return(x+y)
}
let a = add(10, 20)
//add(_:_:)
```
***
```Swift
//Swift 2, 지금은 오류
var myValue = 10
func doubleValue (inout value: Int) -> Int {
    value += value
    return(value)
}
doubleValue(value:&myValue)
	
//Swift 3이후
var myValue = 10
func doubleValue (value: inout Int) -> Int { // Swift 에서 call by reference를 구현하는 방법 inout 사용
    value += value
    return(value)
}
print(myValue)
print(doubleValue(value : &myValue)) // 매개변수에 & 사용
print(myValue)
```
***

```Swift
func printName(firstName:String, lastName:String?){ 

    // if let
    if let lName = lastName {   // lastName이 nil이 아니면
        print(lName,firstName)
    }
    else {
        print("성이 없네요!")
    }

    // guard let
    guard let lName = lastName else { // lastName이 nil이면 
        print("성이 없네요!")
        return // early exit, nil 일경우 return을 만나서 종료된다.
    } 
    print(lName,firstName) // gurad let 바깥쪽의 구문에서도 내부 매개변수를 사용할 수 있다.
}
printName(firstName: "길동", lastName:"홍") // 길동 홍
printName(firstName: "길동", lastName:nil) // 성이 없네요!
```

***

```Swift
func multiplyByTen(value: Int?) {
    guard let number = value,  number < 10 else {//조건식(값이 있고 10보다 작은)이 거짓일 때 실행
        print("수가 없거나 10보다 크다.") //거짓 : 값이 없거나 10보다 크면 
        return
    }
    print(number*10) //조건식이 참일 때 실행, 주의 : number를 여기서도 사용 가능
}
multiplyByTen(value: 3)   //30
multiplyByTen(value: nil)   
multiplyByTen(value: 20)   
```

***

```Swift
import Foundation

let weight = 60.0
let height = 170.0
let bmi = weight / (height*height*0.0001) // kg/m*m 
var body = "" 

if bmi >= 40 { 
    body = "3단계 비만"
} else if bmi >= 30 && bmi < 40 {
    body = "2단계 비만"
} else if bmi >= 25 && bmi < 30 {
    body = "1단계 비만"
} else if bmi >= 18.5 && bmi < 25 {
    body = "정상"
} else {
    body = "저체중" 
}

print("BMI:",String(format:"%.1f",bmi), "판정:\(body)") // String 사용을 위해 Foundation 를 import 해줘야 한다.
```


BMI 측정 함수화
```Swift
#1 리턴 후 출력
import Foundation

func calcBMI(weight : Double, height : Double) -> String{
    let bmi = weight / (height*height*0.0001) // kg/m*m 
    let shortenedBmi = String(format: "%.1f", bmi) 
    var body = "" 

    if bmi >= 40{ 
        body = "3단계 비만"
    } 
    else if bmi >= 30 && bmi < 40 {
        body = "2단계 비만"
    } 
    else if bmi >= 25 && bmi < 30 {
        body = "1단계 비만"
    } 
    else if bmi >= 18.5 && bmi < 25 {
        body = "정상"
    } 
    else {
        body = "저체중" 
    }
    return "BMI:\(shortenedBmi), 판정:\(body)"
}

print(calcBMI(weight:62.5, height: 172.3))
// BMI:21.1, 판정:정상

#2 리턴 x
import Foundation

func calcBMI(weight : Double, height : Double) {
    let bmi = weight / (height*height*0.0001) // kg/m*m 
    let shortenedBmi = String(format: "%.1f", bmi) 
    var body = "" 

    if bmi >= 40{ 
        body = "3단계 비만"
    } 
    else if bmi >= 30 && bmi < 40 {
        body = "2단계 비만"
    } 
    else if bmi >= 25 && bmi < 30 {
        body = "1단계 비만"
    } 
    else if bmi >= 18.5 && bmi < 25 {
        body = "정상"
    } 
    else {
        body = "저체중" 
    }
    print("BMI:\(shortenedBmi), 판정:\(body)")
}

calcBMI(weight:62.5, height: 172.3)

#3 switch case 문 이용
import Foundation

func calcBMI (weight : Double, height : Double) {  //Void형
    let bmi = weight / (height*height*0.0001) // kg/m*m 
    let shortenedBmi = String(format: "%.1f", bmi) 
    switch bmi {
    case 0.0..<18.5:
        print("BMI:\(shortenedBmi),판정:저체중")
    case 18.5..<25.0 :
        print("BMI:\(shortenedBmi),판정:정상")
    case 25.0..<30.0 :
        print("BMI:\(shortenedBmi),판정:1단계 비만")
    case 30.0..<40.0 :
        print("BMI:\(shortenedBmi),판정:2단계 비만")
    default :
        print("BMI:\(shortenedBmi),판정:3단계 비만") 
    }
}
calcBMI(weight:62.5, height: 172.3)

```

# first class object

swift의 함수는 1급 객체이다. 

1급 객체(first class object) 또는 1급 시민(first class citizen)

다음 조건을 충족하는 객체를 1급 객체라고 한다.

* 변수에 저장할 수 있다.

    ```Swift
    func up(num: Int) -> Int {
    return num + 1
    }
    func down(num: Int) -> Int {
    return num - 1
    }

    let toUp = up

    print(up(num:10))
    print(toUp(10))

    let toDown = down

    print(down(num:10))
    print(toDown(10))                    
    ```

* 매개변수로 전달할 수 있다.

    ```Swift
    func upDown(Fun: (Int) -> Int, value: Int) {  
        let result = Fun(value)
        print("결과 = \(result)")
    }
    upDown(Fun:toUp, value: 10) //toUp(10)
    upDown(Fun:toDown, value: 10) //toDown(10)
    ```

* 리턴값으로 사용할 수 있다.

    ```Swift
    func decideFun(x: Bool) -> (Int) -> Int { 
    //매개변수형, 리턴형이 함수형             
        if x {
            return toUp   
        } else {
            return toDown
        }
    }
    let r = decideFun(x:true) // let r = toUp
    print(type(of:r))  //(Int) -> Int
    print(r(10))  // toUp(10)

    r = decideFun(x:false) // let r = toDown
    print(type(of:r))  //(Int) -> Int
    print(r(10))  // toDown(10)

    ```

***

# Closures

```Swift
func add(x: Int, y: Int) -> Int {
  return(x+y)
}
print(add(x:10, y:20))

let add1 = {(x: Int, y: Int) -> Int in return(x+y)}

print(add1(10,20))
```

# trailing closure

* 클로저가 함수의 마지막 argument라면 마지막 매개변수 이름(handler:)을 생략한 후 함수 소괄호 외부에 클로저를 구현한다.

* 마지막 argument에 closure를 써야할 경우 생략하고 함수 뒤에 클로저를 쓰게 할 수 있다.

```Swift
let removeAction = UIAlertAction(
    title: "제거",
    style: UIAlertAction.Style.destructive,
    handler: { 
        ACTION in self.lampImg.image = self.imgRemove
        self.isLampOn=false
    }
)

//trailing closure 일 경우, argument label를 생략 가능하다.
let onAction = UIAlertAction(title: "On", style: UIAlertAction.Style.default){ ACTION in self.lampImg.image = self.imgOn self.isLampOn=true}
```

* 여러 종류의 클로저 스타일

```Swift
let multiply = {(val1: Int, val2: Int) -> Int  in
        return val1 * val2
}
var result = multiply(10, 20)
print(result)
let add = {(val1: Int, val2: Int) -> Int  in
        return val1 + val2
}
result = add(10, 20) 
print(result)
func math(x: Int, y: Int, cal: (Int, Int) -> Int) -> Int {
    return cal(x, y)
}
result = math(x: 10, y: 20, cal: add)
print(result)
result = math(x: 10, y: 20, cal: multiply)
print(result)
```

```Swift
result = math(x: 10, y: 20, cal: {(val1: Int, val2: Int) -> Int in return val1 + val2}) //클로저 소스를 매개변수에 직접 작성 
print(result)

result = math(x: 10, y: 20) {(val1: Int, val2: Int) -> Int in return val1 + val2}//trailing closure
print(result)
```

```Swift
result = math(x: 10, y: 20, cal: {(val1: Int, val2: Int) in return val1 + val2}) //리턴형 생략
print(result)
result = math(x: 10, y: 20) {(val1: Int, val2: Int) in return val1 + val2} //trailing closure, 리턴형 생략
print(result)
```

```Swift
result = math(x: 10, y: 20, cal: {return $0 + $1}) //매개변수 생략하고 단축인자(shorthand argument name)사용, 매개변수를 순서대로 $로 표시
print(result)
result = math(x: 10, y: 20) {return $0 + $1} //trailing closure, 매개변수 생략하고 단축인자사용
print(result)
```

```Swift
result = math(x: 10, y: 20, cal: {$0 + $1}) //클로저에 리턴값이 있으면 마지막 줄을 리턴하므로 return생략 
print(result)
result = math(x: 10, y: 20) { $0 + $1 } //return 생략
print(result)
```
