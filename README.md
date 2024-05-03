
# 유지환 <h1>202130221

## 3월 15일 Java2  강의
깃 허브 주소를 복사하여 vscode에 붙여넣고 깃허브를 쓰는법을 배웠다.
source control 에서 내용을 넣고 comit을 하고 업로드하면 깃허브 주소에 vscode에서 작성한 내용이 올라간다.
java 개발환경 구축
openJDK 설치, Eclips 설치, Eclips에 openJDK 연결
자바 프로젝트 생성

## 월 22일 강의

자바 프로젝트, 클래스 생성 뒤 소스 편집, 컴파일 및 실행
자바 으용 프로그램의 종류
- 데스크톱 응용프로그랩
- 자바 서블릿 응용프로그램
- 모바일 응용프로그램

자바의 특징
플래폼 독릭성,객체지향, 클래스로 캡슐화,소스와 클래스파일, 실행코드 배포 ,패키지, 멀티스레드,가비지컬렉션,실시간응용 시스템에 부적합, 자바 프로그램은 안전하다,프로그램 작서이 쉽다, 실행속도를 개선하기 위해 JIT 컴파일러가 사용됨.

자바 프로그램의 구조
- 클래스 만들기
- 주석문
- main() 메소드
- 메소드
- 메소드 호출
- 변수 선언
- 문장
- 화면 출력

식별자: 클래스,변수,상수,메소드에 붙이는 이름(identifier)
식별자 이름 규칙에서 식별자를 만들때 규칙을 준수하여야함.
1. 식별자로 한글을 사용할 수 있음.
2. 길이제한이 없음.
3. 대소문자를 구별한다.

## 3월 29일 강의

타입 변환이란 변수나 상수 혹은 리터럴을 다른 타입을 변환하는것을 말한다.
- 자동타입 변환: 치환문이나 수식 내에서 타입이 일치하지 않을때 컴파일러는 작은 타입을 큰 타입으로 자동변환
- 강제타입 변환(캐스팅) : 큰 타입을 작은 타입으로 변환해야 할때 자동 변환 대신 컴파일 오류 발생 손실이 발생한다는 사실을 알고 변환한다면 강제로()안에 타입을 지정

자바의 키 입력
- System.in
표준 입력 스트림 객체로, 키 값을 바이트 정보로 바꾸어 제공하는 저수준 스트림 객체

Scanner을 이용한 키 입력 
- scanner 객체는 다음과 같이 생성한다.
"scanner scanner - new scanner(system.in);"
- Scanner을 사용하기 위해서는 프로그램의 맨 앞줄에 "import" 문이 필요하다.
"import java.util.Scanner;"
import문은 scanner 클래스의 경로명이 java.utill.scanner임을 알려준다

예제 2-5 연습

식과 연산자
- 주어진 식을 계산하여 결과를 얻어내는 과정을 연산이라고 한다

산술연산
- 수직 계산에 사용하는 산술 연산자는 더하기,빼기, 곱하기, 나누기, 나머지(%)의 5갸더 /는 몫을 구하여, %는 나머지를 구한다

예제 2-6 연습

증강연산
-  ++,-- 피연산자의 앞 또는 뒤에 붙어 값을 1 증가시키거나 1 감소시킨다.
a++ a를 1 증가하고 증가전의 값 변환
++a a를 1증가하고 증가된 값 변환
a-- a를 1 가모하고 감소 전의 값 변환
--a a를 1 감소하고 감소된 값 변환

대입 연산 
- 연산자의 오른쪽 식의 결과를 왼쪽에 있는 변수에 대입

비교연산, 논리 연산
- 비교연산자는 두 개의 피연산자를 비교하여 true 또는 false의 논리 결과를 내는 연산자
- 논리 연산자는 논리 값을 대상으로 AND,OR,XOR,NOT의 논리 연산을 하여 논리 값을 내는 연산자

조건문
- 단순 IF문 조건식은 비교 연산이나 논리 연산의 혼합된 식으로 구성되며 결과는 불린 값이다.
- 조건식이 참이면 if 내부의 실행 문장이 실행되며 거짓이면 if문을 벗어난다
- 다중 if-else 문은 if의 '조건식'이 참인 경우와 거짓인 경우에 실행할 문장을 각각 지시한다

## 4월 5일 강의
2차원 배열
- 2차원 배열의 선언과 생성
1차원 배열과 마찬가지로 2차원 배열에서도 레퍼런스 변수 선언 후 배열을 생성하며, 2차원 배열의 레퍼런스 변수를 선언
int inArray[][]; 또는 int [][] intArray; // 2차원 배열의 레퍼런스 변수 선언
intArray = new int[2][5]; // 2행 5열(2*5)의 2차원 배열 생성

2차원 배열의 초기화
- 2차원 배열을 선언할 때 각 원소를 초기화 할 수 있다. 자동으로 초기화된 배열이 생성된다.
int inArray[][] = { {0,1,2}, {3,4,5}, {6,7,8} }; // 3*3 배열 생성
char charArray[][] = { {'a','b','c'}, {'d','e','f'} }; // 2*3 배열 생성
double doubleArray[][] = { {0.01,0.02}, {0.03,0.04} }; // 2*2 배열 생성

자바의 예외 처리
예외한 실행 중 오동작이나 결과에 악영향을 미치는 예상치 못한 상황 발생을 예외라고 한다.
- 예외 발생 사례
정수를 0으로 나누는 경우
배열의 크기보다 큰 인덱스로 배열의 원소를 접근하는 경우
정수를 읽는 코드가 실행되고 있을 때 사용자가 문자를 입력한 경우

자바의 예외 처리,try-catch-finally 문
예외 처리란 발생한 예외에 대해 개발자가 작성한 프로그램 내에서 대응하는 것을 말한다. 자바는 예외 처리시 try,catch,finally문을 사용
try {
    예외가 발생할 가능성이 있는 실행문(try 블록)
}
catch (처리할 예외 타입 선언){
    예외 처리문(catch 블록)
}
finally {
    예외 발생 여부와 상관없이 무조건 실행되는 문장(finally 블록)
}

예외가 발생할 가능성이 있는 실행문들을 try{} 블록으로 묶고, 예외 처리 코드는 catch{} 블록에 작성한다.
catch() 문의 () 안에는 처리하고자 하는 예외의 타입을 선언한다. catch {} 블록은 예외마다 하나씩 작성되어야 한다.
finally {}는 선택적 구문으로서 생략해도 상관없으며 실제 많은 경우 생략된다.
finally 블록이 존재하는 경우, try 블록 실행 후 finally 블록이 순차적으로 실행되며, try 블록이 실행되는 도중 예외가 발생하였다면 catch 블록 실행 후 finally 블록을 실행한다. 그리고 finally 블록 아래의 코드를 계속 실행한다.

객체 지향 언어의 목적
- 소프트웨어의 생산성 향상
1. 컴퓨터 산업 발전에 따라 소프트웨어의 생명 주기(life cycle) 단축
2. 객체 지향 언어

- 실세계에 대한 쉬운 모델링
1. 초기 프로그래밍
2. 현대 프로그래밍
3. 객체 지향 언어

## 4월 12일 강의
static 멤버 
- 클래스의 멤버들 중 다음과 같이 static 지시어로 선언된 멤버를 
static 멤버라고 부른다
- static으로 선언된 멤버는 non-static 멤버와 매우 다른 특성을 가진다
- static 멤버는 클래스당 하나만 생성되는 멤버로서, 동일한 클래스의 
모든 객체들이 공유하므로 클래스 멤버라고 부른다
- non-static 멤버는 객체가 생길때 함께 생성되고 객체가 사라지면 함께 사라진다 그러나 static 멤버는 프로그램을 시작할 때나 클래스 로딩 시에 생성된다
- 객체를 생성하기 전에도 static 멤버는 사용
-  생성된 객체가 소멸된 후에도 static 멤버는 여전히 살아 공간을 차지하고 있으며 프로그램이 종료할 때 함께 소멸

static 멤버 사용
non-static 멤버가 객체 이름으로만 활용 할 수 있는 것과는 달리
static멤버는 객체 이름이나 클래스 이름으로 모두 활용 가능하다.
   staticsample.m =3; // 클래스 이름으로 static필드 접근
   staticsample.f(); // 클래스 이름으로 static 메소드 호출

static 메소드의 제약 조건
static 메소드는 두 개의 제약 사항을 가진다

- static 메소드는 오직 static 멤버만 접근 할 수 있다.
static 메소드는 객체가 생성디지 않은 상황에서도 사용이 가능하므로
객체에 속한 인스턴스 메소드, 인스턴스 변수 등을 사용할 수 없고
static 멤버들만 사용 가능하다.
인스턴스 메소드는 static멤버들을 사용할 수 있다.

- static 메소드에서는 this를 사용할 수없다
static메소드는 객체 없이도 존재하기 때문에, static 메소드에서 
this를 사용할 수 없다.

final 클래스
final 클래스 이름 앞에  사용되면 클래스를 상속받을 수 없음을 지정한다.

final 메소드
메소드 앞에 final이 붙으면 이 메소드는 더 이상 오버라이딩 할 수 없음을 지저한다
자식 클래스가 부모 클래스의 특정 메소드를 오버라이딩 하지 못하게 하고 
무조건 상속받아 사용하도록 하고자 한다면 final로 지정하면 된다.

final 필드 
자바에서 final로 필드를 선언하면 필드는 상수가 된다.
상수 필드는 한번 초기화 되면 값을 변경할수없다.
final 키워드를 public static와 함께 선언하면 프로그램 전체에서 공유할 수 있는
상수가된다

상속(interitance)
- 객체 지향 상속
자식이 부모 유전자를 물려받는 것과 유사한 개념

상속의 장점
- 클래스의 사이의 멤버 중복 선언 불필요 - 클래스의 간결화
- 클래스들의 계층적 분류로 클래스 관리 용이
- 클래스 재사용과 확장을 통한 소프트웨어의 생산성 향상

클래스 상속과 객체
- 상속 선언
extends 키워드로 선언(부모 클래스 물려받아 확장한다는 의미)
부모 클래스 -> 슈퍼 클래스(super class)
자식클래스  -> 서브 클래스(sub class)

자바 상속의 특징
- 클래스 다중 상속(multiple ingeritance) 불허
C++는 다중 상속 가능(C++는 다중 상속으로 멤버가 중복 생성되는 문제 있음)
자바는 인터페이스(interface)의 다중 상속 허용
- 모든 자바 클래스는 묵시적으로 Object클래스 상속 받음
java.iang.Object는 클래스는 모든 클래스의 슈퍼 클래스

슈퍼 클래스의 멤버에 대한 서브 클래스의 접근
- 슈퍼 클래스의 private 멤버
서브 클래스에서 접근할 수 없음
-슈퍼 클래스의 디폴트 멤버
서브 클래스가 동일한 패키지에 있을 때, 접근 가능
- 서브 클래스의 public 멤버
서브 클래스는 항상 접근 가능
- 서브 클래스의  protected 멤버
같은 패키지 내의 모든 클래스 접근 허용
패키지 여부와 상관없이 서브 클래스는 접근 가능

protected 멤버
- proctected 멤버에 대한 접근
같은 패키지의 모든 클래스에게 허용
상속되는 서브 클래스(같은 패키지든 다른 패키지든 상관 없음)에게 허용

서브 클래스/슈퍼 클래스의 생성사 호줄과 실행
- 서브 클래스의 객체가 생성될 때
슈퍼 클래스 생성자와 서브 클래스 생성자 모두 실행
호출 순서
- 서브 클래스의 생성자 먼저 호출
-서브 클래스의 생성자는 실행 전 슈퍼 클래스 생성자 호출
실행 순서
- 슈퍼 클래스의 생성자가 먼저 실행된 후 서브 클래스의 생성자 실행

서브 클래스와 슈퍼 클래스의 생성자 선택
- 슈퍼 클래스와 서브 클래스
각각 여러 개의 생성자 작성 가능
- 서브 클래스의 객체가 생성될 때
슈퍼 클래스 생성자 1개와 서브 클래스 생성자 1개가 실행
- 서브 클래스의 생성자와 슈퍼 클래스의 생성자가 결정되는 방식
1. 개발자의 명시적 선택
 - 서브 클래스 개발자가 슈퍼 클래스의 생성자 명시적 선택
 - super() 키워드를 이용하여 선택
2. 컴파일러가 기본생성자 선택
 - 서브 클래스 개발자가 슈퍼 클래스의 생성자를 선택하지 않는 경우
 - 컴파일러가 자동으로 슈퍼 클래스의 기본 생성자 선택

 서브 클래스 객체 생성
 Point 클래스의 객체 p와 Colorpoint 클래스의 객체 cp는 다음가 같이 생성한다
    Point p = new Point();
    ColorPoint cp = new ColorPoint(); // 서브 클래스 객체 생성

## 4월 19일 강의
추상 클래스
   추상 메소드를 가지며 abstract로 선언된 클래스
   추상 메소드를 없이 abstract로 선언한 클래스
   추상 클래스를 상속받으면 추상클래스가 됨 서브 클래스도  abstract
   서브 클래스에서 슈퍼클래스의 추상메소드 구현(오버라이딩)
   추상클래스를 구현한 서브 클래스는 추상 클래스가 아님
목적
   상속을 위한 슈퍼클래스로 활동
   
자바의 인터페이스
- 클래스가 구현해야 할 메소드들이 선언되는 추상형
- 인터페이스 선언
 
자바 인터페이스에 대한 변화
- JAVA 7까지
- JAVA 8부터
- 여전히 인터페이스에는 필드(멤버 변수) 선언불가

자바 인터페이스 특징

인터페이스 상속
- 인터페이스간에 상속 가능
- 인터페이스 다중 상속 허용

패키지 개념과 필요성
   3명이 분담하여 자바 응용프로그램을 개발하는 경우
   동일한 이름의 클래스가 존재할 가능성 있음
 
자바 모듈화의 목적
 모듈화의 목적
- JAVA9부터 자바 API를 여러 모듈(99)로 분할
- 응용 프로그램이 실행할 때 꼭 필요한 모듈들로만 실행환경 구축

 모듈의 현실
- JAVA9부터 전면적으로 도입
- 복작한 개념
- 큰 자바 응용프로그램에는 개발 유지보수 등의 적합
- 현실적으로 모듈로 나누어 자바 프로그램을 작성할 필요 없음

자바 API의 모듈 파일들
- 자바JDK에 제ㅔ공되는 모든 파일들
- 자바가 설치된 jmods 디렉터리에 모듈 파일 존재

## 5월 3일 강의

컬렉션의 개념
- 요소(element)라고 불리는 가변 개수의 객체들의저장소
- 고정크기의배열을다루는어려움해소
- 다양한객체들의삽입, 삭제, 검색등의관리용이

컬렉션의 특징
- 제네릭
  특정타입만다루지않고,여러종류의타입으로변신할수있도록클래스나 
  메소드를일반화시키는기법
  클래스나인터페이스이름에<E>, <K>, <V> 등 타입매개변수 포함

제네릭
- 클래스나메소드를형판에서찍어내듯이생산할수있도록
일반화된형판을만드는기법

제네릭의 기본 개념
- JDK 1.5부터 도입(2004년 기점)모든종류의데이터타입을다룰수있도록일반화된타입매개변수로
클래스(인터페이스)나 메소드를작성하는기법
- C++의 템플릿(template)과 동일

벡터의 특성
- <E>에 사용할요소의특정타입으로구체화
- 배열을가변크기로다룰수있게하는컨테이너
- 요소객체들을삽입,삭제,검색하는컨테이너
-  Vector에 삽입 가능한 것
- Vector에 객체 삽입
- Vector에서 객체 삭제

ArrayList<E>
- 가변크기배열을구현한클래스
   <E>에 요소로사용할특정타입으로구체화
- 벡터와거의동일
   요소삽입, 삭제, 검색 등벡터기능과거의동일
   벡터와달리스레드동기화기능없음

컬렉션의순차검색을위한Iterator
- Iterator<E> 인터페이스
     리스트구조의컬렉션에서요소의순차검색을위한인터페이스
- Iterator 객체 얻어내기
    컬렉션의iterator() 메소드 호출

HashMap<K,V>
- 키(key)와 값(value)의 쌍으로 구성되는 요소를 다루는 컬렉션
        K : 키로 사용할요소의타입
        V : 값으로사용할요소의타입
        키와값이한쌍으로삽입
        ‘값’을 검색하기위해서는반드시‘키’이용
-  삽입및검색이빠른특징
        요소삽입: put() 메소드
        요소검색: get() 메소드
