# [Swift] DataType(자료형)


## 자료형(Data Type)의 종류

### Int
Integer는 42와 -23과 같은 소수점이 없는 정수이다. 정수는 부호(양수, 0 또는 음수) 또는 부호가 없는(양수 또는 0)이다.

Swift는 8, 16, 32 및 64비트 형태로 Unsigned Integer를 지원한다. 이 Integer는 C와 유사한 명명 규칙을 따르며, 8비트 Unsigned Integer는 UInt8 유형이고 32비트 부호 있는 정수는 Int32 유형이다. Swift의 모든 유형과 마찬가지로, 이러한 Integer 유형에는 대문자를 사용한다.

하지만 애플은 특정 크기의 데이터 타입보다는 Int 데이터 타입 사용을 권장한다.

    Int 데이터 타입은 해당 코드가 실행되는 플랫폼에 맞는 정수 크기를 사용한다.

***

```swift

var [변수명] : Int = [초깃값] //초깃값 입력 시, Int 생략 가능

print(Int32.min) //최솟값
//-2147483648
print(Int32.max) //최댓값
//2147483647
```

해당하는 자료형의 .min, .max를 이용하면 최솟값과 최대값을 구할 수 있다.

### Float & Double

소수는 3.14159, 0.1 및 -273.15와 같은 소수점을 가진 숫자이다.

Float와 Double 데이터 타입은 Int 데이터 타입보다 훨씬 더 넓은 범위의 값을 나타내고 저장할 수 있습니다.

* Float 데이터 타입은 32비트로 부동 소수점 수를 저장하고, 소수점 6자리까지 정확도를 가집니다.

* Double 데이터 타비은 64비트로 부동 소수점 수를 저장하고, 소수점 15자리까지 정확도를 가집니다. 

> 소수를 표현하는 데이터 타입은 Double이 기본이다.

```swift
var [변수명] : Float = [초깃값] //초깃값 입력 시, Float 생략 가능 

var [변수명] : Double = [초깃값] //초깃값 입력 시, Double 생략 가능
```

### Bool

참 또는 거짓(1 또는 0) 조건을 처리하는 데이터 타입이다.

Boolean 데이터 타입을 처리하기 위하여 두개의 Boolean 상수 값(true/false)을 사용한다

```swift
var [변수명] : Bool = [true/false] //초깃값 입력 시, Bool 생략 가능
```

### Character

문자, 숫자, 문장 부호, 심볼 같은 유니코드(Unicode) 문자 하나를 저장한다.
* Swift에서의 문자들은 문자소 묶음(grapheme cluster)의 형태로 저장한다.
    * 문자소 묶음은 하나의 문자를 표현하기 위하여 유니코드 코드 값들로 이루어진다.

```swift
var [변수명] : Character = [초깃값] //Character 생략불가, 생략 시 String 데이터 타입이 된다.
```

### String

단어나 문장을 구성하는 일련의 문자다.

저장, 검색, 비교, 문자열 연결, 수정 등의 기능을 포함한다.

문자열 보간(string interpolation)을 사용하여 문자열과 변수, 상수, 표현식, 함수 호출의 조합으로 만들 수도 있다.

```swift
var [변수명] : String = [초기값] //String 생략하여 사용하는 것이 일반적임
```

#### 문자열 보간법(string interpolation)
문자열 보간법(String Interpolation)은 변수 또는 상수 등의 값을 문자열 내에 나타내고 싶을 때 사용하는데 문자열 내에 \(변수나 상수) 의 형태로 표기하면 이를 문자열로 치환해서 넣어 준다. 
문자열 보간법을 이용해 프로그래머가 원하는 문자열로 치환하려면 변수나 상수 타입을 CustomStringConvertible프로토콜을 준수하는 description프로퍼티로 구현한다.

## 참고자료
[Swift Language Guide](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)

[Smile Han Youtube - iOS 1주차-3 : Swift 데이터타입, var, let](https://www.youtube.com/watch?v=ct_pOhzeE-U&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=4)

[Mr.후:티스토리](https://effectivecode.tistory.com/970)
