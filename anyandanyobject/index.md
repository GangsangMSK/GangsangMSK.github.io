# [Swift] Any & AnyObject

## AnyObject(protocal)

* AnyObject can represent an instance of any class type.

* AnyObject는 범용 타입이고 상속관계가 아니라도 타입 캐스팅 가능한 타입이다.

* 어떤 클래스의 객체도 저장 가능하다.

* 가장 추상화된 최상위 개념이고 Objective-C의 id와 같다.

* 클래스만 허용하며 구조체나 열거형은 허용하지 않는다.


```Swift
var x : Any = "Hi"

print(x, type(of:x))
// Hi String

x = 10

print(x, type(of:x))
// 10 Int

x = 3.5

print(x, type(of:x))
// 3.5 Double

//type을 검사해서 사용

```
## Any

* Any can represent an instance of any type at all, including function types.

* 클래스, 구조체, 열거형, 함수타입도 타입 캐스팅이 가능하다. (AnyObject와 차이점)

## 참고자료

[Smaile Han - iOS 1주차-7 : Swift문법 Any, AnyObject](https://www.youtube.com/watch?v=t3LGui2HsQE&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=9)
