# Day2

#### 1. 비교 연산자

- == : 같다

- != : 같지 않다

- ? : 조건부 연산자, 조건식이 참이면 : 앞의 값을 반환, 거짓이면 : 뒤의 값을 반환

  ```c
  #include <stdio.h>
  
  int main(void){
      int a=1;
      int b=0;
      printf("%s\n", a==b?"같음":"다름");
      printf("%s\n", a!=b?"다름":"같음");
      
      return 0;
  }
  ```

#### 2. 논리 연산자

- && : AND, 양쪽 모두 참일 때 참

- || : OR, 양쪽 중 한쪽만 참이라도 참

- ! : NOT, 참과 거짓을 뒤집음

  거짓(False) : 0, 참(True) : 0이 아닌 값, 주로 1을 사용

#### 3. 불 자료형

```c
#include <stdbool.h>
#include <stdio.h>

int main(void){
    bool a=true;
    bool b=false;
    
    return 0;
}
```

#### 4. 연산자 우선순위

| 우선순위 | 연산자                                  | 설명                                                         | 결합 법칙(방향) |
| -------- | --------------------------------------- | ------------------------------------------------------------ | --------------- |
| 1        | x++ x-- ( ) [ ] . -> (자료형){값}       | 증가 연산자(뒤, 후위) 감소 연산자(뒤, 후위) 함수 호출 배열 첨자 구조체/공용체 멤버 접근 포인터로 구조체/공용체 멤버 접근 복합 리터럴 | →               |
| 2        | ++x --x +x -x ! ~ (자료형) *x &x sizeof | 증가 연산자(앞, 전위) 감소 연산자(앞, 전위) 단항 덧셈(양의 부호) 단항 뺄셈(음의 부호) 논리 NOT 비트 NOT 자료형 캐스팅(자료형 변환) 포인터 x 역참조 x의 주소 자료형의 크기 | ←               |
| 3        | * / %                                   | 곱셈 나눗셈 나머지                                           | →               |
| 4        | + -                                     | 덧셈 뺄셈                                                    | →               |
| 5        | << >>                                   | 비트를 왼쪽으로 시프트 비트를 오른쪽으로 시프트              | →               |
| 6        | < <= > >=                               | 작음 작거나 같음 큼 크거나 같음                              | →               |
| 7        | == !=                                   | 같음 다름                                                    | →               |
| 8        | &                                       | 비트 AND                                                     | →               |
| 9        | ^                                       | 비트 XOR                                                     | →               |
| 10       | \|                                      | 비트 OR                                                      | →               |
| 11       | &&                                      | 논리 AND                                                     | →               |
| 12       | \|\|                                    | 논리 OR                                                      | →               |
| 13       | ? :                                     | 삼항 연산자                                                  | ←               |
| 14       | = += -= *= /= %= <<= >>= &= ^= \|=      | 할당 덧셈 후 할당 뺄셈 후 할당 곱셈 후 할당 나눗셈 후 할당 나머지 연산 후 할당 비트를 왼쪽으로 시프트한 후 할당 비트를 오른쪽으로 시프트한 후 할당 비트 AND 연산 후 할당 비트 XOR 연산 후 할당 비트 OR 연산 후 할당 | ←               |
| 15       | ,                                       | 쉼표(콤마) 연산자                                            | →               |

#### 5. 조건문

1. if-else문

   ```c
   #include<stdio.h>
   
   int main(void){
       bool a=true;
       bool b=false;
       
       if (a==true){
           printf("참");
       }
       else{
           printf("거짓");
       }
       
       if (a&&b){
           printf("둘 다 참");
       }
       else if (a||b){
           printf("둘 중 하나는 참");
       }
       else{
           printf("둘 다 거짓");
       }
       
       return 0;
   }
   ```

2. switch-case문

   ```c
   #include<stdio.h>
   
   int main(void){
   	int a;
       
       printf("1~5중에 아무거나 입력하세용 : ");
       scanf("%d", &a);
       
       //switch문에서 판별할 수 있는 변수는 정수자료형만!
       switch(a){
           case 1 :
               printf("1이지롱\n");
               //break;
           case 2:
               printf("2이지롱\n");
               //break;
           case 3:
               printf("3이지롱\n");
               //break;
           case 4:
               printf("4이지롱\n");
               //break;
           case 5:
               printf("5이지롱\n");
               //break;
           default :
               printf("잘못 입력했지롱\n");
               //break;
       }    
       return 0;
   }
   ```

   ```c
   #include <stdio.h>
   
   int main(void)
   {
       char a;
   
       scanf("%c", &a);
   
       switch (a)
       {
       case 'a':    // 문자 a일 때
           printf("a입니다.\n");
           break;
       case 'b':    // 문자 b일 때
           printf("b입니다.\n");
           break;
       default:    // 아무 case에도 해당되지 않을 때
           printf("default\n");
           break;
       }
   
       return 0;
   }
   ```

   