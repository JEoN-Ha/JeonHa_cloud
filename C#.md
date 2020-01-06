# C# 기초 문법

### 	1. Literal

> 코드에서 123, true, "ABC"와 같이 값을 직접 쓰는 데이터

```c#
123    // int
12.3   //double 
"A"    //string
'a'    //char
true   //bool
```

### 	2. 형변환

> to자료형() 함수 이용 또는 강제캐스팅 변경방식

```c#
a = (int)b; //강제캐스팅 변경
int c = Convert.ToInt32(a); //to자료형()
```

### 	3. Nullable Type

```c#
// Nullable 타입
int? i = null;
i = 101;
            
bool? b = null;

//int? 를 int로 할당 (.Value 속성 사용)
Nullable<int> j = null;
j = 10;
int k = j.Value; 
```

---

	### 	4. 배열

> 자료형[] 배열이름 = new 자료형 [배열크기];
>
> 자료형[ , ] = new 자료형 [ , ];
>
> 자료형 [ ] [ ] = new 자료형 [ ] [ ]; 

- 동적 배열

```c#
IList 변수이름 = new ArrayList();	
변수이름.Add(object 값);
```

### 	5. 매소드

```c#
[접근제한자] [반환 타입] 메소드 이름 (파라미터){	
      ........	
      return 반환 타입	
}
```

- ref : 클래스의 포인터를 참조
- out : 값을 내보냄

```c#
using System;	
using System.Collections.Generic;	
using System.Linq;	
using System.Text;	
 	
namespace blog_5__20120906	
{	
    class Program	
    {	
        static void Main(string[] args)	
        {	
            new Program();	
        }	
        public Program() 	
        {	
            int a = 5;	
            int b = 10;	
            // ex_method 메소드 호출	
            int ret = ex_method(ref a);	
            // ex_method 의 return 값 = 50	
            Console.WriteLine("ex_method 의 return 값 = {0}", ret);	
            // Program a 값 = 500	
            Console.WriteLine("Program a 값 = {0}", a);	
            // Program a 값 = 10	
            Console.WriteLine("Program b 값 = {0}", b);	
 	
            // ex_method2 메소드 호출	
            ex_method2(out b);	
            // Program b 값 = 123	
            Console.WriteLine("Program b 값 = {0}" , b);	
 	
            Console.WriteLine("Press any key");	
            Console.ReadLine();	
        }	
        /*	
            ex_method 메소드	
            a에 5의 값을 넣으면 예상되는 값은 a는 500, 반환되는 값은 50입니다.	
        */	
        private int ex_method(ref int a) 	
        {	
            int b = a;	
            b *= 10;	
            a *= 100;	
            return b;	
        }	
        /*	
            ex_method2 메소드	
            파라미터로 a의 값을 내보냅니다.	
        */	
        private void ex_method2(out int a) 	
        {	
            a = 123;	
        }	
    }	
}
```



### 	6. 문자열

- 한번 문자열이 설정되면 변경 불가 (Immutable Type)

> 예를 들어, 문자열 변수 s 가 있을 때, s = "C#"; 이라고 한 후 다시 s = "F#"; 이라고 실행하면, .NET 시스템은 새로운 string 객체를 생성하여 "F#"이라는 데이타로 초기화 한 후 이를 변수명 s 에 할당한다. 즉, 변수 s 는 내부적으로는 전혀 다른 메모리를 갖는 객체를 가리키는 것이다.

```c#
// 문자열을 문자배열로 변환
string str = "Hello";
char[] charArray = str.ToCharArray();

for (int i = 0; i < charArray.Length; i++)
{
    Console.WriteLine(charArray[i]);
}

// 문자배열을 문자열로 변환
char[] charArray2 = { 'A', 'B', 'C', 'D' };
s = new string(charArray2);
```



### 	7. enum (열거형)

> 열거형 상수(constant)를 표현하기 위한 것으로 이를 이용하면 **상수 숫자들을 보다 의미있는 단어들로 표현**할 수 있어서 프로그램을 읽기 쉽게 해준다.
>
> enum문은 **클래스 안이나 네임스페이스 내에서만 선언**될 수 있다. 즉, 메서드 안이나 속성 안에서는 선언되지 않는다.
>
> 숫자형 타입과 호환이 가능하다.



### 	8. ?? 연산자

- ?? 왼쪽 피연산자 값이 NULL인 경우 ?? 오른쪽 의 피연산자 값을 리턴하고, 아닌 경우 왼쪽 피연산자 값을 리턴한다. 
- ?? 왼쪽 피연산자가 NULL이 허용되는 데이터 타입 경우에만 사용 가능

---

### 	9. yield

> 호출자(Caller)에게 컬렉션 데이타를 하나씩 리턴할 때 사용한다. 흔히 Enumerator(Iterator)라고 불리우는 이러한 기능은 집합적인 데이타셋으로부터 데이타를 하나씩 호출자에게 보내주는 역할을 한다.

- yield return : 컬렉션 데이터를 하나씩 리턴하는데 사용
- yield break : 리턴을 중지하고 lteration 루프를 빠져 나올 때 사용



### 	10. 예외 처리

```c#
try
{
   // 실행하고자 하는 문장들
   DoSomething();
}
catch (Exception ex)
{
   // 에러 처리/로깅 등
   Log(ex);
   throw; //예외를 던짐
}
```

- try-catch-finally

```c#
try
{
   //실행 문장들
}
catch (ArgumentException ex)
{
   // Argument 예외처리
}
catch (AccessViolationException ex)
{
   // AccessViolation 예외처리
}
finally
{
   // 마지막에 반드시 실행하는 문장들
}
```



