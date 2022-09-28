# [Swift] Optinal(옵셔널), Optional Binding(옵셔널 바인딩)


## Optional (옵셔널)

값을 반환할 때 오류가 발생할 가능성이 있는 값은 옵셔널 타입이라는 객체로 감싸서 반환한다. 

```Swift
print(Int("123")) 
// Optional(123) 을 출력
print(Int("Hi")) 
// Int("Hi") 은 정수 값을 반환할 수 없음, 아무런 값도 반환할 수 없다는 의미로 nil을 반환 
```

### Optional Type (옵셔널 타입)

Swift에서는 기본 자료형(Int, Double, String 등)은 기본적으로는 nil값을 저장할 수 없지만 옵셔널 타입을 이용하여 nil 값을 저장할 수 있다.

* 옵셔널 타입은 변수 또는 상수에 아무런 값이 할당되지 않는 상황을 안전하게 처리하기 위한 방법 제공한다.
* 옵셔널 타입 변수를 선언하기 위해서는 타입 선언부 뒤에 “?” 문자를 쓴다.

```Swift
let num : Int?
num = 10
print(num) // Optional(10)
```

> 중요 : 데이터 타입 뒤에 "?" 가 온다.

### Optional Forced Unwrapping (옵셔널 강제 언래핑)

옵셔널 변수에 값이 있으면 옵셔널로 "래핑되었다(wrapped)"고 한다.

옵셔널에 래핑된 값은 강제 언래핑(forced unwrapping)으로 풀어준다.

```Swift
var x : Int?
x = 10
print(x) // Optional(10)
print(x!) // 10

// 옵셔널형 선언 : 자료형 뒤 ? 
// 옵셔널 언래핑 : 변수명 뒤 !
```



## Optional Binding (옵셔널 바인딩)

옵셔널에 할당된 값을 임시 변수 또는 상수에 할당하여 사용하는 방법이다.

```Swift
if let constantName = someOptional {
    statements
} // 기본 사용법
```


```Swift
var pet1: String?
var pet2: String?
pet1 = "cat"
pet2 = "dog"
if let firstPet = pet1, let secondPet = pet2 { 
   print(firstPet, secondPet) // cat dog
} else {
  print("nil")
}
// pet1, pet2 가 nil 이 아닐 때 if 실행, nil일 경우 else 실행

```

Swift 5.7 버전 이후로 Optional Binding을 다음과 같이 작성할 수 있다.

```Swift
var pet1: String?
var pet2: String?
pet1 = "cat"
pet2 = "dog"
if let pet1, let pet2 { // Swift 5.7 버전 이후 지원
   print(pet1, pet2) // cat dog
} else {
  print("nil")
}
```

## Implicitly Unwrapped Optionals (암묵적 언래핑)

옵셔널이 항상 유효한 값을 가질 경우 옵셔널이 암묵적인 언래핑(implicitly unwrapped)이 되도록 선언할 수 있다.

암묵적인 언래핑 방법으로 옵셔널이 선언된다면 강제 언래핑이나 옵셔널 바인딩을 하지 않아도 값에 접근할 수 있다.

* 클래스의 아웃렛 변수 초기화에서 많이 사용된다. (자동 생성되는 코드)

* 암묵적인 언래핑으로 옵셔널을 선언하기 위해서는 선언부에 물음표(?) 대신에 느낌표(!)를 사용한다.

```Swift
let x : Int? = 1
let y : Int = x!
let z = x
print(x,y,z)
//Optional(1) 1 Optional(1) 
print(type(of:x),type(of:y),type(of:z))
//Optional<Int> Int Optional<Int>

```

## 참고자료

[Smile Han - iOS 1주차-5 : optional 변수, forced unwrapping, optional binding, nil](https://www.youtube.com/watch?v=YsubSk4JxYw&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=6)

[Smile Han - iOS 1주차 5-1 : implicitly unwrapped optional](https://www.youtube.com/watch?v=BndDgrLpdT0&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=7)

[The Swift Programming Language](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID333)
