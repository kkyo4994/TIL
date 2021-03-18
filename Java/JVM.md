### JVM

- 자바 가상 머신?



#### JDK와 JRE

JDK = JRE + 개발 도구 

- 자바 프로그램 개발하고 실행하기 위해 반드시 설치

JRE = JVM  + 표준 클래스 라이브러리(API) : 자바 런타임 인바이러먼트(환경)

- 자바 프로그램을 실행만 할 경우 설치 



프로젝트 생성 ㅡ> 자바 프로그램 코딩(*.Java) [javac.exe로 컴파일]ㅡ> 바이트 코드 생성(*.class) [JVM-java.exe로 실행]ㅡ> 기계어 ㅡ> 실행



### 단축키

| Ctrl + Shift + o | 자동으로 import 문 추가                            |
| ---------------- | -------------------------------------------------- |
| Ctrl + space Bar | 주어진 단어나 문장으로 시작하는 메서드나 변수 표시 |
| Ctrl + /         | 주석 처리, 해제                                    |
| Ctrl + Shift + F | 코드의 내용을 보기 좋게 포맷팅(들여쓰기)           |



#### 화면에 데이터 출력

- printIn() : ()내부의 내용을 출력한 후 행을 바꾼다
- print() : ()내부의 내용을 축력만 하고 행은 바꾸지 않는다
- printf() : 포멧(%d)을 지정해서 출력한다



#### 키보드로 데이터 입력

- 프로그램의 첫 행에 다음을 추가해 Scanner 클래스의 경로 이름을 컴파일러에 알린다 

  : import java.util.Scanner;

- 키보드로 데이터를 입력받으려고  System.in 객체와 연결된 Scanner 객체를 생성한다

  : Scanner in = new Scanner(System.in);

- Scanner 클래스가 제공하는 다양한 메소드를 이용해 키보드로 데이터를 입력 받는다

  : int x = in.nextInt(); // 정수를 읽어 변수 x에 대입한다 





```java

public class A {
	public static void main(String[] args) {
		System.out.println("asdk");
	}
}

```

```java
import java.util.Scanner;

public class A {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		
		String str = scan.nextLine();
		
		System.out.println(str);
	}
}
```



#### 변수

: 하나의 값을 저장할 수 있는 메모리 공간



헝가리안

파스칼 (첫번째대문자)

스네이크 (_사용)

카멜(낙타)



#### 자바의 데이터 타입 

- 기초 타입(정수, 문자, 실수, 논리)과 참조 타입 (배열, 열거, 클래스, 인터페이스)



자바 타입 변환

- 종류
  - 자동(묵시적) 타입 변환 : Promotion
  - 강제(명시적) 타입 변환 : Casting



#### 연산자 종류

'+' ㅡ> 두 문자열을 연결

'instanceof' ㅡ> 값의 비교

##### 쇼트서킷

조건식1 && 조건식2  ㅡ> 조건식1이 false이면 무조건 false가 된다.

조건식1 || 조건식2  ㅡ>  조건식1이 ture이면 무조건 ture가 된다.



### 메모리 영역(Runtime Data Area)

* 메소드 영역

* 힙 영역

* 스레드 영역

  : 각 스레드 별로 JVM 스택 존재(여러가지 있)

  

#### JVM 스텍

[스레드 별로 JVM 스택 생성]

- 메소드 호출 시마다 각각의 스택 **프레임**(그 메소드만을 위한 공간)이 생성
  - 메소드 호출할 때마다 Frame을 스택에 추가(push)
- 메소드 수행이 끝나면 프레임 별로 삭제한다
  - 메소드 종료하면 Frame 제거(pop)

> 프레임 : 메소드의 매개변수, 지역변수, 리턴 값 밎 연산시 일어나는 값들을 임시로 저장한다



#### Method Area(메소드 영역)

[JVM이 시작할 때 생성되고 모든 스레드가 공유하는 영역]

* 클래스가 로딩될 때, 클래스의 분석된 내용이 메소드 영역에 생성된다
* Runtime Constant Pool별도의 관리 영역도 존재하는데 



#### Heap(힙영역)

[JVM 시작할 때 생성]

* new 연산자로 생성된 객체나 배열을 저장하는 가상 메모리 공간
* 사용되지 않는 객체는 자동 제거



1. Java(명령어) ExampleClass

2. JVM구동 -  되면 메소드 영역과 힘 영역이 생성

3. ExampleClass 클래스 로딩

4. main 스레드 생성

5. main() 메소드 호출 - main 프레임이 생성(스택형과 같은 구조)

6. public static void main(String[]args){

   int sum = 0;

   if(sum==-){

   int v2 = 10;

   int v3 = 20;

   sum = add(v2, v3);

   }

   }

   public static int add(int a, int b){

   ​	return a+b;

   }



#### 배열 선언

* 타입[] 변수; ㅡ> int[] intArray; (자바에서는 대부분 이런 식으로)
* 타입 변수[]; ㅡ> int intArray[];

* 배열 변수 = 참조 변수
  * EX) 타입[] 변수 = null; <ㅡ 참조할 배열 객체가 없는 경우 





#### 값 목록으로 배열 생성

* 데이터타입[] 변수 = {값0, 값1, 값2, ...};
* String[] names = {"홍길동", "김지수", "김민수"};



### New 연산자로 배열 생성

* 타입[] 변수 = new 타입[길이];

* 타입[] 변수 = null;

  변수 = new 타입[길이];

* new 연산자로 배열을 처음 생성할 경우

  ㅡ> 배열은 자동적으로 기본값으로 초기화된다



#### 배열길이

* 배열변수.length;

  (배열의 길이를 얻으려면 배열 객체의 length 필드를 읽으면 된다)

* length 필드는 읽기 전용 필드이므로 값을 바꿀 수가 없다



### 객체를 참조하는 배열
