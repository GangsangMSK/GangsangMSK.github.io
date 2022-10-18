# [Swift Practice] in 22/10/18

# Class (클래스)
```Swift
class Man{
    var age : Int = 1 // Stored property
    var weight : Double = 3.5
}
```

```Swift
class Man{
    var age : Int?
    var weight : Double?
}
```

```Swift
class Man{
    var age : Int?
    var weight : Double?
    func display(){
        print("나이는 \(age!), 몸무게는 \(weight!)")
    }
}

var MS : Man = Man() //클래스명 다음의 괄호는 눈에 보이지 않는 default initializer를 나타냄

MS.age = 23
MS.weight = 90

MS.display()
```

# (Type or Class) method

* 클래스명.클래스메서드()
* 타입 메서드 또는 클래스 메서드는 클래스 레벨에서 동작
* 타입 메서드는 인스턴스 메서드와 동일한 방법으로 선언하지만 class 나 static 키워드를 앞에 붙여서 선언
* class키워드로 만든 클래스 메서드는 자식 클래스에서 override가능 함

```Swift
class Man{
    var age : Int = 1
    var weight : Double = 3.5
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    class func cM(){
        print("cM은 클래스 메서드입니다.")
    }
    static func scM(){
        print("scM은 클래스 메서드(static)")
    }
}
var kim : Man = Man()
kim.display() //인스턴스 메서드는 인스턴스가 호출 
Man.cM()  //클래스 메서드는 클래스가 호출
Man.scM() //클래스 메서드는 클래스가 호출
```

# designated initializer
```Swift
class Man{
    var age : Int
    var weight : Double
    func display(){
        print("나이=\(age), 몸무게=\(weight)")
    }
    init(age: Int, weight : Double){
        self.age = age // self.age는 프로퍼티 age를 접근
        self.weight = weight
    } //designated initializer
}
//init()을 하나라도 직접 만들면 default initializer는 사라짐
var kim : Man = Man(age:10, weight:20.5)
kim.display()

```

* 클래스, 구조체, 열거형(enum) 인스턴스가 생성되는 시점에서 해야 할 초기화 작업
* 인스턴스가 만들어지면서 자동 호출됨 
* 모든 프로퍼티(age, weight)를 다 초기화시키는 생성자
* init()을 하나라도 직접 만들면 기본적으로 만들어지는 눈에 안보이는 default initializer는 사라짐

소멸자
* 인스턴스가 사라질 때 자동 호출
* deinit{} 

