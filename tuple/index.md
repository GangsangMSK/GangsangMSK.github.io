# [Swift] Tuple

## Tuple(튜플)
* 튜플은 Swift 에서 가장 강력한 기능 중 하나이다.
* 여러 값을 하나의 개체에 일시적으로 묶는 방법이다.
* 튜플에는 타입과 상관없이 요소들을 저장할 수 있고, 저장된 값들이 모두 동일한 타입이어야 한다는 제약이 없다.

튜플의 요소들은 다양한 방법들을 이용해 접근할 수 있다.

***

1. 인덱스 위치를 참조하여 접근할 수 있다.

```Swift
let myTuple = (10, 12.1, "Hi") 

let myString = myTuple.2
print(myString) //Hi
```

***

2. 튜플의 요소를 추출하여 번수 또는 상수에 할당하여 사용할 수 있다.

```Swift
let myTuple = (10, 12.1, "Hi")
let (myInt, myFloat, myString) = myTuple

let (myInt2, _, myString2) = myTuple //튜플의 값을 선택적으로 추출할 수 있고, 무시하고 싶은 값에 밑줄을 사용하면 된다.

```

***

3. 튜플을 생성할 때 각 값에 이름을 할당하여 사용할 수 있다.

```Swift
let myTuple = (count: 10, length: 12.1, message: "Hi")
//튜플에 저장된 값에 할당된 이름은 각 값을 참조하는데 사용된다.
print(myTuple.message) //Hi
```

***

**튜플의 가장 강력한 점은 함수에서 여러 값들을 한번에 반환하는 것이다.**

## 참고자료

[Smile Han Youtube - iOS 1주차-4 : Swift Tuple](https://www.youtube.com/watch?v=n34BiC9TgVI&list=PLJqaIeuL7nuEEROQDRcy4XxC9gU6SYYXb&index=5)

[ZeddiOS - Swift)tuple](https://zeddios.tistory.com/238)
