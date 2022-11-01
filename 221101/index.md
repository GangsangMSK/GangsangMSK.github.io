# [Swift Practice] in 22/11/01


## Stored property

Stored property 는 초기화를 하지 않으면 에러가 난다.

초기화 방법으로는 다음 3가지가 있다.

1. 초기값이 있거나

2. init을 이용해서 초기화하거나

3. 옵셔널 변수(상수)로 선언(자동으로 nil로 초기화)

***

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5

    init(yourAge: Int, yourWeight : Double){
        age = yourAge
        weight = yourWeight
    } //designated initializer
    
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    
    class func cM(){
        print("cM은 클래스 메서드입니다.")
    }
    static func sM(){
        print("sM은 클래스 메서드입니다.(static)")
    }
    
}
//var kim : Man = Man()  //init()호출 : 오류
var kim : Man = Man(yourAge:10, yourWeight:20.5)
 //init(yourAge: Int, yourWeight : Double)호출
kim.display()
```

***

## Self

self 사용

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5

    init(age: Int, weight: Double){
        self.age = age //self
        self.weight = weight //self
    } //designated initializer

    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    
    class func cM(){
        print("cM은 클래스 메서드입니다.")
    }
    static func sM(){
        print("sM은 클래스 메서드입니다.(static)")
    }

}
//var kim : Man = Man()  //init()호출 : 오류
var kim : Man = Man(age:10, weight: 20.5)
 //init(yourAge: Int, yourWeight : Double)호출
kim.display()
```

***

## Computed property

Computed property 는 기존에 stored property 에서 계산해서 만든다.

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5
    
    //1.
    var manAge : Int{
        get{
            return age - 1
        }
        set(USAAge){
            age = USAAge + 1
        }
    } //computed property

    //2. getter 만 존재할 경우 get{ }가 생략가능하다
    var manAge : Int{
        //get{
            return age - 1
        //}
    } 

    //3. set newValue로 받을 경우 생략가능
    var manAge : Int{
        get{
            return age - 1
        }
        set{ //(newValue) 생략가능
            age = newValue + 1
        }
    }

    init(age: Int, weight: Double){
        self.age = age
        self.weight = weight
    } //designated initializer

    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    
    class func cM(){
        print("cM은 클래스 메서드입니다.")
    }
    static func sM(){
        print("sM은 클래스 메서드입니다.(static)")
    }
    
}
//var kim : Man = Man()  //init()호출 : 오류
var kim : Man = Man(age:10, weight: 20.5)
 //init(yourAge: Int, yourWeight : Double)호출
kim.display()
print(kim.manAge)
```

***

## Overloading

Overloading : 같은 이름의 함수를 사용

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5
    var manAge : Int{
        get{
            return age - 1
        }
        set(USAAge){
            age = USAAge + 1
        }
    }
    
    init(age: Int, weight: Double){
        self.age = age
        self.weight = weight
    } //designated initializer
    init(age: Int){
        self.age = age
    }
    
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    func display(age: Int){ //overloading
        print("나이=\(age), 몸무게=\(weight)")
    }
    
    class func cM(){
        print("cM은 클래스 메서드입니다.")
    }
    static func sM(){
        print("sM은 클래스 메서드입니다.(static)")
    }
    
}
//var kim : Man = Man()  //init()호출 : 오류
var kim : Man = Man(age:10, weight: 20.5)
 //init(yourAge: Int, yourWeight : Double)호출
kim.display()
print(kim.manAge)

var lee : Man = Man(age: 20)
lee.display()
```

***

## 상속

```Swift
class 자식클래스 : 부모클래스, 프로토콜1, 프로토콜2 ... {
}
```
* 부모 클래스는 하나만 가능하다.

* 콜론 다음이 여러 개이면 나머지는 프로토콜이다. 

* 부모클래스가 있을 때, 프로토콜이 오는 경우에는 부모클래스를 처음에 쓴다.

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5
    
    init(age: Int, weight: Double){
        self.age = age
        self.weight = weight
    } //designated initializer
    
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    
}
class Student : Man { //상속
    
}

var kim : Man = Man(age:10, weight: 20.5)
kim.display() // 나이=10, 몸무게=20.5

var lee : Student = Student(age: 20, weight: 50)
lee.display() //나이=20, 몸무게=50.0
```

### super

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5
    
    init(age: Int, weight: Double){
        self.age = age
        self.weight = weight
    } //designated initializer
    
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    
}
class Student : Man { //상속
    var name : String
    func displays(){
        print("이름=\(name), 나이=\(age), 몸무게=\(weight)")
    }
    init(age: Int, weight: Double, name: String){
        self.name = name
        super.init(age: age, weight: weight)
    }
}

var hong : Student = Student(age: 20, weight: 50, name: "홍길동")
hong.displays() //이름=홍길동, 나이=20, 몸무게=50.0
```

***

## Overriding
```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5
    
    init(age: Int, weight: Double){
        self.age = age
        self.weight = weight
    } //designated initializer
    
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    
}
class Student : Man { //상속
    var name : String
    init(age: Int, weight: Double, name: String){
        self.name = name
        super.init(age: age, weight: weight)
    }
    override func display(){ //overriding
        print("이름=\(name), 나이=\(age), 몸무게=\(weight)")
    }
}

var hong : Student = Student(age: 20, weight: 50, name: "홍길동")
hong.display()
```

***

![https://en.wikipedia.org/wiki/Access_modifiers](/images/Blog/221101/1.png)

* 접근 속성(접근 수정자, 액세스 수정자, 액세스 지정자 )는 클래스, 메서드, 멤버의 접근 가능성을 설정하는 객체 지향 언어의 키워드

* 구성 요소를 캡슐화 하는 데 사용 

* 노란 색은 언어별 디폴트 접근 속성

```Swift
public class MyClass{ 
    // 모듈의 모든 소스 파일 내에서 접근+정의한 모듈을 가져오는 다른 모듈의 소스파일에서도 접근 가능
    fileprivate var name : String = "Kim"
    //현재 소스 파일 내에서만 사용 가능
    private func play() {}
    //현재 블럭 내에서만 사용 가능
    func display(){} //internal은 디폴트 속성으로 생략됨
    //해당 모듈의 모든 소스 파일 내에서 사용
}

```

## Type property

Property 앞에 static이 올 경우 type property라고 한다.

```Swift
class SClass {
    var storedProperty = 2
    static var storedTypeProperty = 1 //type property
    static var computedTypeProperty: Int {
        return 10
    }
    class var overrideableComputedTypeProperty: Int {
        return 100
    }
}
var x = SClass() 
print(x.storedProperty)
print(SClass.storedTypeProperty)
print(SClass.computedTypeProperty)
print(SClass.overrideableComputedTypeProperty)
```
***

## Protocol

```Swift
protocol Runnable { //대리하고 싶은 함수 목록 작성
    var x : Int {get set} //읽기와 쓰기 가능 프로퍼티,{get}은 읽기 전용
    //property in protocol must have explicit { get } or { get set } specifier
    func run() //메서드는 선언만 있음
    //바디({ })가 있을 경우 에러가 남 Protocol methods must not have bodies
}
```

```Swift
protocol Runnable { //대리하고 싶은 함수 목록 작성
    var x : Int {get set} //읽기와 쓰기 가능 프로퍼티,{get}은 읽기 전용
    //property in protocol must have explicit { get } or { get set } specifier
    func run()//메서드는 선언만 있음
}

class Man : Runnable {
    var x : Int = 1
    func run() {
        print("달린다")
    }
}
var kim = Man()
kim.run()
```

## 최종 과제
```Swift
protocol B {
    func bb(num:Int) -> Int
}
class C {
    
}
class A : C, B {
    func bb(num: Int) -> Int {
        return num * 2
    }
}
let a = A()
print(a.bb(num: 3))
```

## 참고자료
[위키백과 - Access_modifiers](https://en.wikipedia.org/wiki/Access_modifiers)
