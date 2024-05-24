
# 유지환 <h1>202130221

##### 이벤트 기반 프로그래밍
- 이벤트의 발생에 의해 프로그램 흐름이 결정되는 방식
   - 이벤트가 발생하면 이벤트를 처리하는 루틴 실행
   - 실행될 코드는 이벤트의 발생에 의해 전적으로 결정

- 반대되는개념: 배치실행(batch programming)
   - 프로그램의 개발자가 프로그램의 흐름을 결정하는 방식

- 이벤트 종류
   - 사용자의입력: 마우스드래그, 마우스클릭, 키보드누름등
   - 센서로부터의입력, 네트워크로부터데이터송수신
   - 다른응용프로그램이나다른스레드로부터의메시지

- 이벤트 기반 응용 프로그램의 구조
   - 각 이벤트마다 처리하는 리스너 코드 보유

- GUI 응용프로그램은 이벤트기반프로그래밍으로작성됨
    - GUI 라이브러리 종류
      C++의MFC, C# GUI, Visual Basic, X Window, Android 등

##### 자바 스윙 프로그램에서 이벤트 처리 과정

- 이벤트가처리되는과정
   - 이벤트 발생
   - 이벤트 객체 생성
      - 현재 발생한 이벤트에 대한 정보를 가진 객체
- 응용 프로그램에 작성된 이벤트 리스너 찾기
- 이벤트 리스너 실행
   - 리스너에 이벤트 객체 전달
   - 리스너 코드 실행

##### 이벤트 객체
- 이벤트 객체
   - 발생한 이벤트에 관한 정보를 가진 객체
   - 이벤트 리스너에 전달됨
       - 이벤트 리스너 코드가 발생한 이벤트에 대한 상황을 파악할 수 있게 함

- 이벤트 객체가 포함하는 정보
   - 이벤트종류와이벤트소스
   - 이벤트가발생한화면좌표및컴포넌트내좌표
   - 이벤트가발생한버튼이나메뉴아이템의문자열
   - 클릭된마우스버튼번호및마우스의클릭횟수
   - 키의코드값과문자값
   - 체크박스, 라디오버튼 등과같은컴포넌트에이벤트가발생하였다면체크상태

-  이벤트소스를알아내는메소드
   - Object getSource()
      발생한이벤트의소스컴포넌트리턴
      Object 타입으로 리턴하므로캐스팅하여사용
      모든이벤트객체에대해적용

##### 리스너 인터페이스
- 이벤트 리스너
   - 이벤트를 처리하는 자바 프로그램 코드, 클래스로 작성

- 자바는 다양한 리스너 인터페이스 제공
   -  예) ActionListener 인터페이스– 버튼 클릭 이벤트를 처리하기 위한 인터페이스
      interface ActionListener { // 아래 메소드를 개발자가 구현해야 함
      public void actionPerformed(ActionEvent e); // Action 이벤트 발생시 호출됨
      }
   
   -  예) MouseListener 인터페이스– 마우스 조작에 따른 이벤트를              
      처리하기위한인터페이스
      interface MouseListener { // 아래의 5개 메소드를 개발자가 구현해야 함
      public void mousePressed(MouseEvent e); // 마우스 버튼이 눌러지는 순간 호출
      public void mouseReleased(MouseEvent e); // 눌러진 마우스 버튼이 떼어지는 순간 호출
      public void mouseClicked(MouseEvent e); // 마우스가 클릭되는 순간 호출
      }
      public void mouseEntered(MouseEvent e); // 마우스가 컴포넌트 위에 올라가는 순간 호출
      public void mouseExited(MouseEvent e); // 마우스가 컴포넌트 위에서 내려오는 순간 호출

- 사용자의 이벤트 리스너 작성
   - 자바의 리스너 인터페이스를 상속받아 구현
   - 리스너 인터페이스의 모든 추상 메소드 구현

##### 이벤트 리스너 작성 방법
- 3가지 방법
   - 독립 클래스로 작성
     - 이벤트 리스너를 완전한 클래스로 작성
     - 이벤트 리스너를 여러 곳에서 사용할 때 적합
   - 내부 클래스로 작성
     - 클래스 안에 멤버처럼 클래스 작성
     - 이벤트 리스너를 특정 클래스에서만 사용할때 적합
   - 익명 클래스로 작성
     - 클래스의 이름 없이 간단히 리스너 작성
     - 클래스 조차 만들 필요 없이 리스너 코드가 간단한 경우에 적합

##### 어댑터 클래스
- 이벤트 리스너 구현에 따른 부담
   - 리스너의 추상 메소드를 모두 구현해야하는 부담
   - 예) 마우스리스너에서마우스가눌러지는경우(mousePressed())만처리하고자 하는    경우에 도나머지4 개의메소드를모두구현해야하는부담

- 어댑터 클래스
   - 리스너의모든메소드를단순리턴하도록만든클래스(JDK에서제공)

##### KEY 이벤트와 포커스
- 키 입력 시, 다음 세 경우 각각 KEY 이벤트 발생
   - 키를누르는순간
   - 누른키를떼는순간
   - 누른키를떼는순간(Unicode 키의 경우에만)

- 키이벤트를받을수있는조건
    - 모든 컴포넌트
    - 현재 포커스를 가진 컴포넌트가 키 이벤트 독점

- 포커스 
    - 컴포넌트나 응용프로그램이 키 이벤트를 독점한느 권한
    - 컴포넌트에 포커스 설정 방법 : 다음 2라인 코드필요

##### 유니코드(Unicode) 키
- 유니코드 키의 특징
    - 국제 산업 표준
    - 전 세계의 문자를 컴퓨터에서 일관되게 표한하기 위한 코드 체계
    - 문자들에 대해서만 키 코드 값 정의
       - A~Z, a~z, 0~9, !, @, & 등
    -  문자가아닌키경우에는표준화된키코드값없음
       - <Function> 키, <Home> 키, <Up> 키,<Delete> 키, <Control> 키, <Shift> 
          키, <Alt> 등은 플랫폼에 따라 키코드값이다를수있음
    - 유니코드 키가 입력되는 경우 
       - keyPressed(), keyTyped(), keyReleased() 가 순서대로 호출
    - 유니코드 키가 아닌 경우
       - keyPressed(), keyReleased() 만 호출됨
     
## 5월 17일 강의

##### 컨테이너의 배치관리자
- 컨테이너마다 하나의 배치관리자 존재
- 컨테이너에 부착되는 컴포넌트의 위치와 크기 결정
- 컨테이너의 크기가 변경되면, 컴포넌트의 위치와 크기 재결정

##### 배치 관리자 대표 유형 4가지
- FlowLayout 배치관리자
     컴포넌트가삽입되는순서대로왼쪽에서오른쪽으로배치
     배치할공간이없으면아래로내려와서반복한다.
- BorderLayout 배치관리자
     컨테이너의공간을동(EAST), 서(WEST), 남(SOUTH), 북(NORTH), 
     중앙(CENTER)의 5개 영역으로나눔
     5개영역중응용프로그램에서지정한영역에컴포넌트배치
- GridLayout 배치관리자
     컨테이너를프로그램에서설정한동일한크기의2차원격자로나눔
     컴포넌트는삽입순서대로좌에서우로, 다시위에서아래로배치
- CardLayout
     컨테이너의공간에카드를쌓아놓은듯이컴포넌트를포개어배치

##### BorderLayout 생성자와 add() 메소드
- 생성자
   BorderLayout()
   BorderLayout(int hGap, int vGap)
     - hGap : 좌우 두 컴포넌트사이의수평간격, 픽셀단위(디폴트: 0)
     - vGap : 상하 두 컴포넌트사이의수직간격, 픽셀단위(디폴트: 0)

- add() 메소드
      void add(Component comp, int index)
      - comp 컴포넌트를 index 위치에 삽입한다.
      - index : 컴포넌트의 위치
                동: BorderLayout.EAST
                서: BorderLayout.WEST 
                남: BorderLayout.SOUTH 북 : BorderLayout.NORTH
                중앙: BorderLayout.CENTER

##### GridLayout 생성자
- 생성자
  - GridLayout()
  - GridLayout(int rows, int cols)
  - GridLayout(int rows, int cols, int hGap, int vGap)
         rows : 격자의 행수 (디폴트 : 1)
         cols : 격자의 열수 (디폴트 : 1)
         hGap : 좌우 두 컴포넌트사이의수평간격, 픽셀단위(디폴트: 0)
         vGap : 상하 두 컴포넌트사이의수직간격, 픽셀단위(디폴트: 0)
         rows x cols 만큼의 셀을 가진 격자로 컨테이너 공간을분할, 배치


##### 배치관리자가 없는 컨테이너
-  배치관리자가없는컨테이너가필요한경우
      응용프로그램에서직접컴포넌트의크기와위치를결정하고자하는경우
      1. 컴포넌트의 크기나위치를개발자임의로결정하고자하는경우
      2. 게임 프로그램과같이시간이나마우스/키보드의입력에따라
         컴포넌트들의위치와크기가수시로변하는경우
      3. 여러 컴포넌트들이서로겹쳐출력하고자하는경우
- 컨테이너의 배치 관리자 제거 방법
    - container.setLayout(null);
    
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

자바의GUI(Graphical User Interface)
- GUI 응용프로그램
   GUI
   사용자가편리하게입출력할수있도록그래픽으로화면을구성하고, 마우스나키보드로입력
   받을수있도록지원하는사용자인터페이스
   자바언어에서GUI 응용프로그램작성
   AWT와Swing 패키지에 강력한 GUI 컴포넌트 제공

컨테이너와 컴포넌트
- 컨테이너
    다른컴포넌트를포함할수있는GUI 컴포넌트
    다른컨테이너에포함될수있음

- 컴포넌트 
   컨테이너에포함되어야화면에출력될수있는GUI 객체
   다른컴포넌트를포함할수없는순수컴포넌트
   모든GUI 컴포넌트가상속받는클래스: java.awt.Component
   스윙컴포넌트가상속받는클래스: javax.swing.JComponent

- 최상위컨테이너
  다른컨테이너에포함되지않고도화면에출력되며독립적으로존재가능한
  컨테이너

스윙GUI 프로그램 만들기
 - 스윙GUI 프로그램을만드는과정
1. 스윙 프레임만들기
2. main() 메소드 작성
3. 스윙 프레임에스윙컴포넌트붙이기

- 스윙프로그램작성에필요한import문
 import java.awt.*;
 import java.awt.event.*; 
 import javax.swing.*; 
 import javax.swing.event.*; 

 스윙프레임
 - 스윙프레임: 모든스윙컴포넌트를담는최상위컨테이너
      JFrame을상속받아구현
      컴포넌트들은화면에보이려면스윙프레임에부착되어야함

- 스윙프레임(JFrame)기본구성
    프레임–스윙프로그램의기본틀
    메뉴바–메뉴들이부착되는공간
    컨텐트팬–GUI 컴포넌트들이부착되는공간

프레임만들기, JFrame 클래스 상속
-  스윙프레임
     JFrame 클래스를 상속받은 클래스작성
     프레임의크기반드시지정: setSize() 호출
     프레임을화면에출력하는코드반드시필요: setVisible(true) 호출

스윙응용프로그램에서main()의 기능과위치
- 스윙응용프로그램에서main()의 기능최소화바람직
    스윙응용프로그램이실행되는시작점으로서의기능만
    스윙프레임을생성하는정도의코드로최소화
    
스윙응용프로그램의종료
- 응용프로그램 내에서 스스로 종료하는 방법
   System.exit(0);
   언제 어디서나 무조건 종료

- 프레임의오른쪽상단의종료버튼(X)이클릭되면어떤일이일어나는가?
   프레임종료,프레임윈도우를닫음
       프레임이화면에서보이지않게됨
   프레임이보이지않게되지만응용프로그램이종료한것아님
       키보드나마우스입력을받지못함
       다시setVisible(true)를 호출하면, 보이게 되고 이전 처럼 작동함
    프레임종료버튼이클릭될때,프레임과함께프로그램을종료시키는방법  
       frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
