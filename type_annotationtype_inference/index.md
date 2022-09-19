# 타입 어노테이션(Type annotation)과 타입 추론(Type inference)

Swift는 타입 안전(Type safe) 프로그래밍 언어이다. 그로 인해 변수의 타입이 식별되면, 그 변수는 다른 타입의 데이터를 저장하는데 사용할 수 없다. 변수가 선언되 후에도 다른 타입의 데이터를 저장할 수 있는 loosely typed(Ex:JavaScript) 언어와 대조적이다.

변수 또는 상수의 식별 방법엔 두 가지가 존재한다.

1. **타입 어노테이션(Type annotation)**

    변수 또는 상수가 코드 내에서 선언되는 시점에 데이터 타입을 정해주는 경우

    * 변수 또는 상수 이름 다음에 타입 선언을 하면 된다.

    ```Swift
    var num : Int = 10 // : Int가 Type annotation
    ```

    ***

    상수를 선언할 때도 타입 어노테이션을 통해 나중에 값을 할당할 수 있다.

    ```Swift
    let bookTitle : String
    var book = true
    if book {
        bookTitle = "iOS"
    }
    else {
        bookTitle = "Android"
    }
    print(bookTitle) // 값이 한번만 할당되어 사용가능
    //iOS
    ```
2. **타입 추론(Type inference)**

    선언부에 타입 어노테이션이 없어, 컴파일러가 데이터 타입 식별을 위해 변수 또는 상수에 값이 할당되는 시점에 값의 타입을 확인하여 정해주는 경우

    ```Swift
    var num = 10 
    // 10(Int)를 통해 num이라는 변수의 타입을 Int라 추론
    // var num : Int = 10
    ```
