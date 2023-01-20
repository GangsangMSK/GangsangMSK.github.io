# [Etc] 기술 면접 예상 질문


1. OOP란?

    OOP는 현실 세계를 프로그래밍으로 옮겨와 현실 세계의 사물들을 객체로 보고, 그 객체로부터 개발하고자 하는 특징과 기능을 뽑아와 프로그래밍하는 기법입니다. OOP로 코드를 작성하면 재사용성과 변형가능성을 높일 수 있습니다.
<br><br>

2. OOP의 5가지 설계 원칙

    * SRP(Single Responsibility Principle, 단일 책임 원칙): 클래스는 단 하나의 목적을 가져야 하며, 클래스를 변경하는 이유는 단 하나의 이유여야 한다.
    * OCP(Open-Closed Principle, 개방 폐쇠 원칙): 클래스는 확장에는 열려 있고, 변경에는 닫혀 있어야 한다.
    * LSP(Liskov Substitution Principle, 리스코프 치환 원칙): 상위 타입의 객체를 하위 타입으로 바꾸어도 프로그램은 일관되게 동작해야 한다.
    * ISP(Interface Segregation Principle, 인터페이스 분리 원칙): 클라이언트는 이용하지 않는 메소드에 의존하지 않도록 인터페이스를 분리해야 한다.
    * DIP(Dependency Inversion Principle, 의존 역전 법칙): 클라이언트는 추상화(인터페이스)에 의존해야 하며, 구체화(구현된 클래스)에 의존해선 안된다.
<br><br>

3. 절차지향 프로그래밍과 객체지향 프로그래밍의 차이

    ### 절차지향 프로그래밍

    * 물이 위에서 아래로 흐르는 것처럼 순차적인 처리를 중요시하는 프로그래밍 기법이다.
    * 가장 대표적인 언어로 C언어가 있다.
    * 컴퓨터의 처리구조와 유사해 실행속도가 빠르다.
    * 코드의 순서가 바뀌면 동일한 결과를 보장하기 어렵다.

    ### 객체지향 프로그래밍
    
    * 실제 세계의 사물들을 객체로 모델링하여 개발을 진행하는 프로그래밍 기법
    * 가장 대표적인 언어로 Java가 있다.
    * 캡슐화, 상속, 다형성 등과 같은 기법을 이용할 수 있다. 다형성은 동일한 키보드의 키가 다른 역할을 하는 것처럼 하나의 메소드나 클래스가 다양한 방법으로 동작하는 것을 의미한다.
    * 절치지향 언어보다 실행속도가 느리다.
<br><br>
 
4. RESTful API란? 

    * REST(REpresentational State Transfer)ful API는 HTTP 통신에서 어떤 자원에 대한 CRUD 요청을 Resource와 Method로 표현하여 특정한 형태로 전달하는 방식입니다. RESTful API는 아래와 같은 것들로 구성됩니다.
    * Resource(자원, URI)
    * Method(요청 방식, GET or POST 등)
    * Representation of Resource(자원의 형태, JSON or XML 등)
<br><br>

5. 함수형 프로그래밍란?

    함수평 프로그래밍의 가장 큰 특징은 immutable data와 first class citizen으로서의 함수입니다. 함수형 프로그래밍은 부수효과가 없는 순수 함수를 이용하여 프로그램을 만드는 것이다. 부수 효과가 없는 순수 함수란 데이터의 값을 변경시키지 않으며 객체의 필드를 설정하는 등의 작업을 하지 않는 함수를 의미합니다.
<br><br> 
 
6. 메모리 구조 

    <p align="center"><img class="lazyload" src="/svg/loading.min.svg" data-src="/images/Blog/interview/1.png" data-srcset="/images/Blog/interview/1.png, /images/Blog/interview/1.png 1.5x, /images/Blog/interview/1.png 2x" data-sizes="auto" alt="/images/Blog/interview/1.png" title="1" width="300px"/></p>
    
    * 코드 영역: 실행할 프로그램의 코드가 저장되는 영역으로 텍스트 영역이라고도 부릅니다. 사용자가 프로그램 실행 명령을 내리면 OS가 HDD에서 메모리로 실행 코드를 올리게 되고, CPU는 코드 영역에 저장된 명령어를 하나씩 처리하게 됩니다.

    * 데이터 영역: 프로그램의 전역 변수(global)와 정적 변수(static)가 저장되는 영역입니다. 데이터 영역은 프로그램의 시작과 함께 할당되며, 프로그램이 종료되면 소멸합니다.

    * 힙 영역: 프로그래머가 직접 관리할 수 있는 메모리 영역으로 이 공간에 메모리를 할당하는 것을 동적 할당이라고 부릅니다. Java에서는 가비지 컬렉터가 자동으로 해제해줍니다. 힙 영역은 스택 영역과 달리 낮은 주소에서 높은 주소로 메모리가 할당됩니다.

    * 스택 영역: 함수의 호출과 함께 할당되며 지역 변수와 매개 변수가 저장되는 영역입니다. 스택 영역에 저장되는 함수의 호출 정보를 스택프레임이라고 합니다. 스택 영역은 함수의 호출이 완료되면 소멸합니다. 스택 영역은 높은 주소에서 낮은 주소로 메모리가 할당됩니다.
<br><br>
 
7. Parameter와 Argument의 차이

    * Parameter: 함수를 선언할 때 사용된 변수
    * Argument: 함수가 호출되었을 때 함수의 파라미터로 전달된 실제 값
<br><br>
 
8. Call By Value와 Call By Reference 차이

    ### Call By Value
    인자로 받은 값을 복사하여 처리하는 방식

    ### Call By Reference
    인자로 받은 값의 주소를 참조하여 직접 값에 영향을 주는 방식

    * Call By Value에 의해 넘어온 값을 증가시켜도 원래의 값이 보존된다.
    값을 복사하여 넘기기 때문에 메모리 사용량이 늘어난다.

    * Call By Reference는 값을 복사하지 않고 직접 참조하기 때문에 속도가 빠르다.
    원래의 값에 영향을 주는 리스크가 존재한다.
    
    예를 들어 아래와 같은 코드가 있다고 할 때, changeStr라는 새로운 변수가 생성되어 Call By Value로 전달되기 때문에 메모리를 많이 사용하지만 changeStr를 변경하여도 원래 값인 str는 영향을 받지 않습니다.
    
    ```Java
    public class Main {

        public static void main(String[] args) {
            String str = new String("str");
            changeReference(str); // It won't change the reference!
            modifyReference(str); // It will modify the object that the reference variable "modifyStr" refers to!
        }

        public static void changeReference(String str) {
            String changeStr = new String("changeStr");
            str = changeStr;
        }

        public static void modifyReference(String str) {
            str.setAttribute("modifyStr");
        }

    }
    ```
<br><br>
 
9. 프레임워크와 라이브러리 차이

    * 라이브러리: 사용자가 흐름에 대한 제어를 하며 필요한 상황에 가져다가 쓸 수 있다.
    * 프레임워크: 전체적인 흐름을 자체적으로 제어한다.
    * 프레임워크와 라이브러리는 실행 흐름에 대한 제어 권한이 어디 있는지에 따라 달라집니다. 프레임워크를 사용하면 사용자가 관리해야 하는 부분을 프레임워크에 넘김으로써 신경써야 할 것을 줄이는 제어의 역전(IoC, Inversion Of Control)이 적용됩니다.
<br><br> 
 
10. 병렬 처리 프레임워크의 종류와 특징

    ### Hadoop

    * HDFS(Hadoop Distributed File System)를 활용해 데이터를 주고 받는다.
    * 데이터가 여러 노드에 분산되어 저장되기 때문에 손실의 우려가 없다는 장점이 있다.
    * 하지만 File I/O를 기반으로 작동하기 때문에 처리 속도가 느리다.

    ### Spark

    * In-Memory 상 에서 데이터를 주고받고 연산을 수행한다.
    * 메모리를 사용해 데이터를 처리하기 때문에 Hadoop보다 속도가 약 100배 정도 빠르다.
    * 하지만 메모리상에서 처리하기 때문에 장애가 발생한 경우 응용 프로그램을 처음부터 다시 시작해야 한다.
<br><br> 
 
11. 동기와 비동기의 차이

    ### 동기(Synchronous) 방식
    * 요청을 보내고 실행이 끝나면 다음 동작을 처리하는 방식
    * 순서에 맞추어 진행되기 때문에 제어하기 쉽다.
    * 여러가지 요청을 동시에 처리할 수 없어 효율이 떨어진다.
    * 동기 방식의 예시로는 콜센터 종업원이 일을 처리하는 방식이 될 수 있다. 콜센터의 직원은 한 손님의 전화 응대가 끝난 후에 다음 손님의 응대를 진행할 수 있다.

    ### 비동기(Asynchronous) 방식
    * 요청을 보내고 해당 동작의 처리 여부와 상관없이 다음 요청이 동작하는 방식
    * 작업이 완료되는 시간을 기다릴 필요가 없기 때문에 자원을 효율적으로 사용할 수 있다.
    * 작업이 완료된 결과를 제어하기 어렵다.
    * 비동기 방식의 예제로는 이메일이 있다. 우리는 한 사람에게 이메일을 보냈을 때 답변을 받지 않고도 이메일을 다시 보낼 수 있다. 
<br><br>

12. SQL Injection이란? 

    * SQL Injection이란 공격자가 악의적인 의도를 갖는 구문을 삽입하여 공격자가 원하는 SQL을 실행하도록 하는 웹해킹기법입니다. 
    
    예를 들어 아래와 같은 간단한 SQL 문이 있을 때 INPUT1에 'OR 1=1--을 넣는 것입니다.
    
    ```SQL
    SELECT * FROM USER WHERE ID = 'INPUT1' AND PASSWORD = 'INPUT2'

    SELECT * FROM USER WHERE ID = '' OR 1=1 --INPUT1' AND PASSWORD = 'INPUT2'
    ```
    
    * INPUT1으로 'OR 1=1--을 넣으면 보이는 것처럼 뒤의 내용은 주석처리가 되고 WHERE 문은 항상 참이 됩니다.
    
    ### 이러한 공격을 방지하기 위해 특수문자 및 SQL 예약어들을 필터링하거나 SQL 오류 메세지를 노출하지 않는 등의 방법을 취해야 합니다.
<br><br> 
 
13. Docker(도커)와 Kubernates(쿠버네티스)란? 

    Docker는 컨테이너 기반의 가상화 기술입니다. 기존에는 하드웨어를 가상화하였기 때문에 Host OS 위에 Guest OS를 설치해야 했습니다. 하지만 이러한 방식은 상당히 무겁고 느려 한계가 많이 있었습니다.

    그래서 이를 극복하고자 프로세스를 격리시킨 컨테이너를 통해 가상화를 하는 Docker(도커)와 같은 기술들이 등장하게 되었고, 도커를 통해 구동되는 컨테이너를 관리하기 위한 Kubernates(쿠버네티스)가 등장하게 되었습니다.
<br><br> 
 
14. Docker(도커)의 장/단점

    장점
    * 쉽고 빠른 실행 환경 구축
    * 하드웨어 자원 절감
    * Docker Hub와 같은 공유 환경 제공

    단점
    * 개발 초기의 오버헤드
    * Linux 친화적
<br><br>

15. 자료구조와 알고리즘이란?

    자료구조는 데이터를 원하는 규칙 또는 목적에 맞게 저장하기 위한 구조이고, 알고리즘이란 자료구조에 쌓인 데이터를 활용해 어떠한 문제를 해결하기 위한 여러 동작들의 모임입니다.
<br><br> 
 
16. 스택, 큐, 트리, 힙 구조 설명

    * 스택: 세로로 된 바구니와 같은 구조로 먼저 넣게 되는 자료가 마지막으로 나오게 되는 First-In Last-Out(FILO) 구조이다.
    * 큐: 가로로 된 통과 같은 구조로 먼저 넣게 되는 자료가 가장 먼저 나오는 First-In First-Out(FIFO) 구조이다.
    * 트리: 정점과 간선을 이용해 사이클을 이루지 않도록 구성한 Graph의 특수한 형태로, 계층이 있는 데이터를 표현하기에 적합하다.
    * 힙: 최댓값 또는 최솟값을 찾아내는 연산을 쉽게 하기 위해 고안된 구조로, 각 노드의 키값이 자식의 키값보다 작지 않거나(최대힙) 그 자식의 키값보다 크지 않은(최소힙) 완전이진트리이다.
<br><br>
 
17. 우선순위 큐와 내부 구조 및 시간복잡도

    우선순위큐는 가장 우선순위가 높은 데이터를 먼저 꺼내기 위해 고안된 자료구조입니다. 우선순위 큐를 구현하기 위해서 일반적으로 힙을 사용합니다. 힙은 완전이진트리를 통해서 구현되었기 때문에 우선순위 큐의 시간복잡도는 O(logn)입니다.
<br><br>
 
18. 해시 테이블과 해시 테이블의 시간 복잡도

    해시 테이블은 (Key, Value)로 데이터를 저장하는 자료구조 중 하나로 빠른 데이터 검색이 필요할 때 유용합니다. 해시 테이블은 Key값에 해시함수를 적용해 고유한 index를 생성하여 그 index에 저장된 값을 꺼내오는 구조입니다.

    <p align="center"><img class="lazyload" src="/svg/loading.min.svg" data-src="/images/Blog/interview/2.png" data-srcset="/images/Blog/interview/2.png, /images/Blog/interview/2.png 1.5x, /images/Blog/interview/2.png 2x" data-sizes="auto" alt="/images/Blog/interview/2.png" title="2" width="400px"/></p>
    
    해시 테이블은 고유한 index로 값을 조회하기 때문에 평균적으로 O(1)의 시간복잡도를 갖습니다. 하지만 해시의 index값이 충돌이 발생한 경우 충돌된 index값에 대해 연결된 데이터들을 조회하여 원하는 값을 조회하기 때문에 O(N)까지 증가할 수 있습니다.
<br><br> 
 
19. LinkedList와 ArrayList 차이

    ArrayList는 데이터들이 순서대로 늘어선 배열의 형식을 취하고 있지만, LinkedList는 자료의 주소값으로 서로 연결된 형식을 가지고 있습니다. 이러한 구조에 의해 둘은 각각의 장단점을 가지고 있습니다.
    
    ### ArrayList
    * 원하는 데이터에 무작위로 접근할 수 있다.
    * 리스트의 크기가 제한되어 있으며, 리스트의 크기를 재조정하는 것은 많은 연산이 필요하다.
    * 데이터의 추가/삭제를 위해서는 임시 배열을 생성하여 복제하고 있어 시간이 오래 걸린다.

    ### LinkedList
    * 리스트의 크기에 영향 없이 데이터를 추가할 수 있다.
    * 데이터를 추가하기 위해 새로운 노드를 생성하여 연결하므로 추가/삭제 연산이 빠르다.
    * 무작위 접근이 불가능하며, 순차 접근만이 가능하다.

    <p align="center"><img class="lazyload" src="/svg/loading.min.svg" data-src="/images/Blog/interview/3.png" data-srcset="/images/Blog/interview/3.png, /images/Blog/interview/3.png 1.5x, /images/Blog/interview/3.png 2x" data-sizes="auto" alt="/images/Blog/interview/3.png" title="3" width="800px"/></p>
<br><br> 
 
20. 큐와 스택의 구현

* 큐(Queue): Array로 구현하면 poll 연산 이후 객체를 앞당기는 작업이 필요하다. 하지만 List로 구현하면 객체 1개만 제거하면 되므로 삽입 및 삭제가 용이한 LinkedList로 구현하는 것이 좋다.
* 스택(Stack): List로 구현하면 객체를 제거하는 작업이 필요하다. 하지만 Array로 구현하면 삭제할 필요 없이 index를 줄이고 초기화만 하면 되므로, Array로 구현하는 것이 좋다. 서비스 간의 호출이 연속적이기 때문에 디버깅 및 에러 트레이싱이 어렵다.
<br><br>

## 출처  

[망나니개발자 - [기술면접] CS 기술면접 질문 - 프로그래밍 공통 (1/8)](https://mangkyu.tistory.com/88)

[망나니개발자 - [기술면접] CS 기술면접 질문 - 자료구조 (2/8)](https://mangkyu.tistory.com/89)
