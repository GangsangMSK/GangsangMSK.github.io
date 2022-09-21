# [Swift] var과 let

## var / 변수

변수는 프로그램에서 사용될 데이터를 저장하기 위한 메모리 공간이다.

변수는 할당된 값의 변경이 가능하다.

```Swift
var 변수명 : 데이터 타입 // 사용법
var x = 0.0,  y= 0.0, z = 0.0 // ,를 사용하여 여러개의 변수 선언 가능

var num = 10 // : Int 생략가능
num = 20 //문제 없음
```
## let / 상수

상수(const)는 데이터 값을 저장하기 위한 메모리 공간을 제공하는 점은 변수와 비슷하나, 한번 할당되면 그 이후로는 값을 변경할 수 없다.

상수는 코드 내에서 반복적으로 사용하는 값이 있을 경우, 상수에 할당하여 사용하면 유지보수에 도움이 된다.


```Swift
let 상수명 : 데이터 타입
let test : String //선언 시, 초기화를 안해주어도 사용가능함
let text : String = "상수"
text = "변수" //syntax error 발생
```

> 애플은 코드의 효율성과 실행 성능을 높이기 위해서 변수(var)보다는 상수(let) 사용을 권장한다.

## 참고자료

[Swift Language Guide](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)

[Smile Han Youtube - iOS 1주차-3 : Swift 데이터타입, var, let](https://www.youtube.com/watch?v=ct_pOhzeE-U&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=4)

[다소니닷넷:티스토리](https://dasony-lib.tistory.com/10)
