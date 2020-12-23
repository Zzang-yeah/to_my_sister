# Day1

#### 1. 헤더파일

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>
```

#### 2. 자료형

1bit : 컴퓨터 데이터 단위, 컴퓨터에서 사용하는 가장 작은 정보 단위, 0과 1->2가지의 경우를 나타낼 수 있음

1Byte=8bit->2^8의 경우를 나타낼 수 있음

![image-20201223121413601](C:\Users\cat78\AppData\Roaming\Typora\typora-user-images\image-20201223121413601.png)

```c
#include <stdio.h>

int main(void){
	char a='a';
    int b=14;
    double c=3.141592;
    float d=3.14;
    //%? 서식 지정자
    //%5d -> 5칸 남는 곳은 공백으로 채우기
    //%05d -> 5칸 남는 곳은 공백이 아닌 0으로 채우기
    printf("%c", a);
    printf("%d", b);
    printf("%lf", c);
    printf("%f", d);
    
    return 0;
}
```

자료형의 범위보다 작으면 언더 플로우, 크면 오버플로우 발생

**!문자 자료형!**

문자 자체를 저장하는 것X문자에 해당하는 정수값을 저장(아스키코드)

알파벳은 1바이트, 한글은 2바이트

문자 입력받을때 주의사항 : https://codingfun.tistory.com/124

#### 3. 상수

상수 : 변하지 않는 값

```c
const double pi=3.14159265;

//pi=3.1415; 상수에 값을 재할당하면 에러!
```

#### 4. 입출력

```python
#include <stdio.h>

int main(void){
    int a;
    char b;
    double c;
            
    printf("문자를 하나 입력하세요 : ");
    scanf("%c", &b);
    printf("정수를 입력하세요 : ");
    scanf("%d", &a);
	printf("실수를 입력하세요 : ");
    scanf("%lf", &c);
    
    printf("정수 : %d 문자 : %c 실수 : %lf", a,b,c);
    
    return 0;
}
```

#### 5. 연산

1. 덧셈, 뺄셈

   ```c
   #include <stdio.h>
   
   int main(void){
       int a=5;
       int b=4;
       int sum, sub;
       sum=a+b;
       sub=a-b;
       printf("덧셈 : %d, 뺄셈 : %d", sum, sub);
       
   	return 0;
   }
   ```

   ```c
   //단항연산자
   #include <stdio.h>
   
   int main(void){
       int a=0;
       int b=0;
       int c=0;
   	printf("%d %d", a++, ++b);
       printf("%d %d", a, b);
       
       c+=1;	//c=c+1;와 같은 의미
       printf("%d", c);
       c-=1;	//c=c-1;과 같은 의미
       printf("%d", c);
       
       return 0;
   }
   ```

2. 곱셈, 나눗셈, 나머지

   ```c
   #include<stdio.h>
   
   int main(void){
       int a=4;
       int b=2;
       int c=1;
       int multi, div, mod;
       
       //곱셈
       multi=a*b;
       div=a/b;
       mod=a%b;
       printf("곱셈 : %d, 나눗셈 : %d, 나머지 : %d", multi, div, mod);
       
       //곱셈나눗셈나머지도 단항연산자 똑같이 쓰면 됨
       c*=a;	//c=c*a;
       printf("%d", c);
       c/=b;	//c=c/b;
       printf("%d", c);
       c%=b;	//c=c%b;
       printf("%d",c);
   
       return 0;
   }
   ```

   

