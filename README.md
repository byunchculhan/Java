# 1. 자바 개요

## 1.1 특징

* 이식성이 높다.  OS 제약 없음
* 객체 지향 . 부품(객체) 처럼 조립하여 개발
  *  캡슐화, 상속, 다형성 지원 => 재사용 등 효율적으로 개발 가능
     *  `캠슐화`
     *  `상속`
     *  `다형성`
* 람다식 지원. 코드 간결함
* 메모리 자동 관리, 멀티 스레드(다중/대용량 작업), 동적 로딩, 오픈 소스 등



## 1.2 프로그램 개발~실행 과정

1. 소스 작성: .Java 소스 작성
2. 컴파일: .class(바이트 코드 파일) 생성
3. 명령어 실행:JVM 구동 명령어(Java.exe)

>.java > `javac.exe` > .class > `java.exe` > 기계어 > `실행`  



# 2. 변수와 타입

## 2.1 변수

변수란? 하나의 값을 저장 할수 있는 메모리 공간 => 무언가를 담기위한 그릇

* 사용법: `타입` `변수이름`
* (처음 담는 내용)초기화: 변수는 초기화 되어야 읽기 가능
* (그릇의크기):int < long, float<double
* (그릇에 담긴 내용 그 자체)`리터럴(literal)`: 소스 상에서 직접 인력된 값 자체
* (내용물 교체)타입변환
  * 자동 타입 변환(promotion): 작은 타입에서 큰타입은 손실 없이 가능

  * 강제 타입 변환(casting): 변경되는 타입 명시 팔요.  큰 타입에서 작은 타입으로 변환 시 일부 손실 발생

## 2.2 타입(데이터 타입)

타입? 다양한 변수의 크기를 정의 => 미리 메모리 공간을 확보. 메모리 관리의 효율성

* 기본(Primitive) 타입: 정수, 실수 문자(소수점), 논리(참/거짓)

* 최소 단위: 8bit => 1 byte

  

# 3. 연산자

## 3.1 연산자와 연산식

연산이란? 데이터를 처리(+,-,/,* 등) 하여 결과를 산출 하는것

* 연산자(Operation: 데이터(변수 등) 처리 방법

* 피연산자(Operand): 연산 대상 데이터

* 연산식(Expression): 처리 식, 연산자와 피연산자로 구성

  

# 4. 조건문과 반복문

## 4.1 조건문

(판단)조건(True/False)에 따라 실행 여부를 결정

* If {} ELSE{}: If  조건 결과에 따른 실행
* Switch() Case, default: 조간 값에 따른 실행

## 4.2 반목문

(반복)조건에 맞을떄 까지 반복 실행

* for: 반복 횟수를 알고 있을 떄
* while: 조건에 따른 반복
* do {} while: 최초 한번은 실행 후 조건에  반복  => 입력 받아서 반복을 종료할떄
* break: 반복에서 Exit
* continue: 반복 조건으로 Jump



# 5. 참조 타입

메모리 공간에 값이 아니라 값을 가지고 있는 주소를 저장. 기본 타입외에는 참조 타입임

## 5.1 메모리 영역

1. 메소드 영역(클래스 정의) 및 객체를 힙 영역 로딩(method 및 heap 영역)

2. 쓰레드 단위로 프로그램 실행 => 쓰레드 스택(Stack 영역) 내 변수값 및 객체의 주소값을 이용하여 연산 수행 

   

* method(staic) 영역:코드에서 사용되는 클래스 코드 저장
  * JVM 시작시 생성
  * 모든 스레드에서 공유

* 힙(heap) 영역: New 연산자로 생성된 객체(인스턴스)와 배열 저장 => 프로그램 상 데이터 저장

  * JVM 시작시 생성
  * JVM의 GC(Garbage Collector)에 의해 자동적으로 제거 => 참조하는 개체가 없을 떄

* JVM 스택(stack) 영역: 기본 타입의 변수값을 저장. 참조 타입은 주소 저장

  * LIFO 구조
  * 스레드 별 생성. 스택안에 Frame 생성 
  * 메소드 호출 시 Frame 생성 =>  스택에 frame 추가(push)
  * 메소드 종료시 Frame에 제거(pop)

* (참조타입)String 타입: 문자열을 저장하는 클래스 타입

  * 문자열 리터럴이 동일하다면 String 객체 공유 => 다른 변수로 정의하더라도 동일한 주소값
  * 단, new 연산자로 객체 생성시는 문자열이 동일하더라도 다른 주소값을 가짐

* (참조타입)배열 타입: 같은 타입의 데이터를 연속된 공간에 저장하는 자료 구조 => 그릇을 담는 서랍장

  * 각 데이터 저장 위치는 인덱스를 부여하여 접근

  * > 타입[] 변수; or 타입 변수[]; 

  * 배열 선언 방법

    * 값을 지정하여 배열 생성
    * 값을 모를 경우 new 로 새로운 객체 생성 => 초기값 자동 할당

  * 배열 복사: system.arrayCopy() 사용

#### #자바 실행 과정

<img src="https://t1.daumcdn.net/cfile/tistory/2540294C5654207F26" alt="자바 메모리 구조" style="zoom:50%;" />

#### #Runtime Data Area

<img src="https://t1.daumcdn.net/cfile/tistory/216AE04C5654207F0A" alt="Runtime Data Areas & Heap Area" style="zoom:50%;" />





# 6.클래스

## 6.1 객체 및 객체 지향 프로그래밍

> 자바에서 객체란. (추상적인)객체의 설계도 즉 클래스를 구체화 한것. 
> 클래스에는 필드(속성), 메소드(동작방법)의 정의만 있을 뿐 객제화 되어서
> 속정의 값이 정해지고, 그 값을 이용하여 동작할수 있음. 그 결과가 객체
> 객체 지향 프로그래밍은 클래스를 이용하여 프로그래밍 하는 것임 

* 특징

  * 캡슐화: 객체의 구현 내용을 감추는 것. 모든 내용을 공유하지 않고 약속된 통로로만 객체를 이용하는 것

  * 상속: 다른 클래스를 기반으로 객체를 업그레이드 하는 것 => 내것 처럼 사용하여 더욱 확장

  * 다형성: 동일한 유형의 객체 이지만 실행 결과 다른 다양한 객체를 이용 => 타입에 대입하여 다양한 객체의 기능을 사용

    * 타입 변환 가능

      * 부모 클래스 => 모든 자식  객체 대입 가능
      * 인터페이스 타입 => 인터페이스 구현 객체는 모두 대입 가능

    * 부모 자식객체 

      

## 6.2 객체(Object)와 클래스(Class)

클래스(필드+메소드)  ==인스턴스 ==> 객체

* 객체 생성 방법: new 클래스()  => heap 영역 생성 후 주소값 리턴
* 클래스 변수: new 연산자에 의해 리턴된 객체의 주소 저장(참조 타입 변수) 
  * 클래스 변수 = new 클래스
* 클래스 구성
  * 필드(field): 객체의 데이터가 저장되는 곳
  * 생성자(consuructor): 객체 생성시 초기화
  * 메소드(method): 객체의 동작에 해당되는 실행 블록

> public class `ClassName`{
>
> ​	int fieldName;
>
> ​	className() {...}
>
> ​	void methodName() { ...}
>
> }

## 6.3 생성자

객체 생성시 외부값으로 객체를 초기화 할수 있음

* 생성자 오버로딩: 매개변수 타입, 개수, 순서가 다른 생성자를 여러개 선언할수 있음



## 6.4 메소드

객체의 동작(기능)을 정의

>  리턴값 메소드 이름 (매개변수 선언,  ...) {}

* 메소드 오버로딩: 클래스 내에 같은 이름의 메소들을 여러개 선언 하여 사용



## 6.5 인스턴스/스태틱(정적) 멤버

* 인스턴스 멤버 : 객체(인스턴스) 마다 가지고 있는 필드와 메소드
  * 인스턴스 필드, 인스턴스 메소드
  * heap 영역에 존재 =>  객체가 없이 사용 불가
* 스태틱 멤버: 클래스에 고정된 필드와 메소그
  * 스태틱 필드, 스태틱 메소드
  * method 영역에 존재 =>  객체 생성 없이 사용 가능
    * 클래스 == 클래스 로더(바이트 코드 적제) ==> 메소드 영역
  * 블록 내 인스턴스 필드 및 메소드 사용 불가, this 사용 불가
  * 싱글톤(singleton): 하나의 객체만 생성
    * new 연산자로 생성 불가
      * 'private static 클래스 sigleton=new 클래스();' => 클래스 외부에서 new 연산자로 접근 불가
      * getInstance 메소드로 접근 가능



## 6.6 접근 제한자

클래스 및 클래스의 멤버에 대한 접근을 제한

* public: 제약 없음
* protected: 같은 패지지 내+자식 클래스는 접근 가능
* default: 같은 패키지 내에서만 접근 가능
* private: 클래스 내에서만 접근

## 6.7 final 필드와 상수

* final 필드: 최종적인 값을 갖고 있는 필드(값을 변경할수 업음)
  * 초기값 지정 방법: 필드 선언시, 생성자
* 상수: static final 필드(객체마다 가지고 있지 않고 공용 데이터로 사용)



#  7. 상속

자식 클래스가 부모(상위) 클래스의 멤버(필드, 메소드)를 몰려 받는것

* 제한: Private, 다른 패키지의 default 

> public class B extends A { }

* 자식 객체 생성 시 부모 객체로 부터 생성 후 자식 객체 생성  => 부모 생성자 먼저
  * super() 부모 생성자 호출
* 메소드 오버라이드(@Override): 부모 클래스에서 상속 받은 메소드를 자식 클래스에서 재정의
  * 부모의 메소드와 동일한 시그너처를 가져야함(리턴타입, 메소드 이름, 매개 변수 리스트)
  * super.부모메소드
* final 클래스, final 메소드는 오버라이딩 불가



##  7.1 타입변환

* 자동타입 변환(promotion): 프로그램 실행 도중 자동 타입 변환
  * `부모클래스 변수 = 자식클래스타입` => 부모 타입으로 자식 클래스를 사용
    * 스택영역에 부모 및 자식 클래스 주소 할당
  * 직계가 아니더라도 상속 계층의 상위면 가능
* 강제타입 변환(casting):부모 타입을 자식 타입으로 변환 하는 것
  * `자식클래스 변수 = (자식클래스) 부모클래스타입` => 자식 타입을 부모 타입으로 자동변환 후 다시 자식 타입으로 변환만 가능



## 7.2 추상 클래스

실체 클레스의 공통 필드와 메소드 정의한 클래스 => 설계도 규격

* 무조건 상속 받아야 사용 가능

> public abstract class 클래스{
>
> }



#  8. 인터페이스

개발 코드와 객체 사이의 통신 접점 => 통신 규약을 이용하여 다양한 방법 적용 가능

> [public] interface 인터페이스명 {}

* 상수 필드만 선언 가능, 모두 public
* 인터페이스를 통해 호출된 메소드는 최종적으로 객체에서 실행(추상 메소드임)
* 디폴트 메소드의 경우 실행 블록을 가지고 있음



## 8.1 인터페이스 구현

* 인터페이스의 추상 메소드에 대한 실체 메소드를 가진 객체(구현객체)

> public class 구현클래스명 implements 인터페이스명{}

* 익명 구현 객체: 명시적인 구현 클래스를 작성하지 않고 바로 구현 객체를 생성

  * > 인터페이스 변수 = new 인터페이스() {}



## 8.2 타입 변환

* 자동타입 변환(promotion): 프로그램 실행 도중 자동 타입 변환

  * > 인터페이스 변수 = 구현 객체

* 매개 변수의 타입이 인터페이스 인 경우

  * 어떠한 구현 객체도 매개값으로 사용가능하며, 구현 객체에 따라 실행 결과가 달라짐

* 강제 타입 변환(casting): 인터페이스 타입으로 자동 타입 변환 후 구현 클래스 타입으로 변환

  * 구현 클래스의 다른 멤버 사용 목적 

    

#  9. 중첩 클래스와 중첩 인터페이스

## 9.1 중첩 클래스

중첩 클래스: 클래스 멤버로 선언된 클래스

* 두 클래스 간의 멤버들에게 쉽게 접근	

* 분류(선언위치)

  * 멤버 클래스: 인스턴스 멤버클래스(인스턴트 필드/메소드만 생성 가능), 스태틱 멤버클래스(모든  필드와 메소드 생성 가능)

    * 인스턴트 멤버 클래스는 바깥 클래스의 모든 필드와 메소드 접근 가능
    * 스태틱 멤버 클래스는 바깥 클래스의 스태틱 필드와 메소드만 접근 가능

  * 로컬 클래스: 메소드안에 정의 (인스턴트 필드/메소드만 생성 가능)

    

## 9.2 중첩 인터페이스

클래스 멤버로 선언된 인터페이스

* UI 컴퍼넌트 내부 이벤트 처리에 사용

  

##  9.3 익명 객체

이름이 없는 객체

* 단독 생성 불가: 클래스 상속, 인터페이스 구현 필요

* 필드의 초기값, 로컬 변수의 초기값, 매개 변수의 매개값에 주로 대입

* UI 이벤트 처리 객체나, 스레드 객체를 간편하게 생성할 목적

* 생성 방법

  * `익명 자식 객체 생성`: 자식 클래스가 재사용되지 않고 필드와 변수 초기화 용도로 사용 할 경우

    * > 부모 클래스 [필드:변수]  = new 부모클래스(매개값, ...) { };

  * `익명 구현 객체 생성`: 인터페이스 타입으로 필드, 변수를 선언하고 구현 객체를 초기값으로 대입

    * > 인터페이스 [필드:변수] = new 인터페이스() { };

      

# 10. 예외처리

* 에러(error): 하드웨어의 잘못된 동작 또는 고장으로 인한 오류
* 오류(exception: 사용자의 잘못된 조작 또는 개발자의 잘못된 코딩으로 이한 오류
  * 일반예외(컴파일예외): 예외 처리 코드가 없으면 컴파일 오류 발생
  * 실행예외(runtime exceptiopn): 예외 처리 코드를 생략 하더라도 컴파일이 되는 예외 => 경험적 예외처리 필요
    * NullPointerExceoption:null값을 가지고 있는 객체 참조 시
    * ArrayIndexOutOfBoundsException:배열에서 인덱스 범위 초과하여 사용
    * ClassCastException:타입 변환이 되지 않을 경우

> try {
>
> } catch(예외클래스 e){
>
> } finally { 항상실행 
>
> }

* throws: 메소드에서 처리하지 않은 예외를 호출한 곳으로 떠 넘기는 역할



# 11. 기본 API 클래스

* 자바 API: 기본 제공 라이브러리, 범용적인 클래스 및 인터페이스 모음

  * object: 최상위 클래스
  * 객체 비교: euqlals() 메소드

* 객체 해시코드: 객체의 메모리 번지를 이용하여 해시 코드를 만들어 리턴

  * 개별 객체별 고유 값을 가짐

* 객체 복제: 원본 객체의 필드값과 동일한 값을 가지는 새로운 객체 생성

  * 얕은 복제(thin clone): 필드 값만 복제(참조 필드는 주소 공유)
  * 깊은 복제(deep clone): 참조하고 있는 객체도 복제
    * clone() 메소드를 재정의해서 참조 객체를 복제하는 코드 직접 작성 필요

* system.gc(); 쓰레기 수집기 실행 요청

* 문자열 분리(StringTokenizer)

  * String의 split()메소드 이용
  * java.util.StringTokenizer 클래스 이용

* 포장 클래스: 기본 타입을 객체화

  * 박싱(기본 타입 값=>포장 객체), 언박싱(포장 객체->기본 타입 값)

  * 기본 타입의 값을 이용: `기본타입명+Value()메소드` 사용

    

# 12. 멀티 스레드

* 프로세스: 실행 중인 하나의 프로그램
  * 하나의 프로그램은 여러개의 프로세스로 실행될수 있음
* 멀티 태스킹: 두가지 이상의 작업을 동시에 처리 하는것
  * 멀티 프로세스: 독립적으로 프로그래을 실행하고 여러 가지 작업 처리
  * 멀티 스레드: 한 개의 프로그램을 길행하고 내부적으로 여러가지 작업 처리
* 메인(main) 스레드: 모든 자바 프로그램은 main() 메소드를 실행하며 시작
* 우선순위
  * 동시성: 하나의 코어에서 멀티 스레드가 번갈아 가면서 실행
  * 병렬성: 멀티 코어에세 개별 스레드 동시에 실행

## 12.1 스레드 생성 방법

* 작업 스레드 생성 방법

  * Thread 클래스로 부터 직접 생성
    * Runnable을 매개값으로 갖는 생성자 호출

  > Theread thread = new Thread(new Runnable() {
  >
  > public void run() {
  >
  > }
  >
  > });
  >
  > Thread thread= new Thread(() ->{}); => 람다식

  

  * Thread 하위 클래스로 부터 생성
    * Thread 클래스 상속 후 run 메소드 제정의해 스레드가 실행할 코드 작성

  > public class WorkerThread extends Thread{
  >
  > @ovverride
  >
  > public void run(){}
  >
  > }

  > Thread thread = new THread() {
  >
  > public void run(){}
  >
  > };



## 12.2 동기화 메소그 및 동기화 블록

동기화? 다른 스레드 공유 하지 못하도록 잠금 장치

* 하나의 스레드만 실행 가능
* 동기화 메소드, 블록이 실행 중일 경우 다른 모든 동기화 영역도 잠금 상태임



# 13. 제네릭

* 컴파일 시 강력한 타입 체크 가능 => 미리 명시

  * 타입변화 제거 가능

* 제네릭 타입 => 클래스 선언 시 타입 파라메타 사용

  * 타입을 파라미터로 가지는 클래스와 인터페이스
  * 타입 파라미터

* 제네릭 메소드

  * 매개변수 타압과 리턴타입으로 타입 파라미터를 갖는 메소드

* 와일드카드 타입

  * <?> : 모든  클래스나 인터페이스 타입 가능
  * <? extends 상위타입>: 상위타입+하위타입
  * <? super 하위타입>:하위타입+상위타입

  

# 14. 람다식

람다식? 익명 함수를 생성하기 위한 식=> 함수 지향식 프로그램 형식

> (매개변수) -> {실행식};

* 람다식 => 매개 변수를 가진 코드 블록 => 익명 구현 객체

* 함수적 인터페이스:@FunctionInterface
  * 추상 메소드가 2개 이상 되면 컴파일 오류 발생





