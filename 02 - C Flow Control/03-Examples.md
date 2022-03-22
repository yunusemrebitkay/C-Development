# Examples

### Example 1 - Bir sayının çift mi yoksa tek mi olduğunu kontrol edin

```c
#include <stdio.h>

int main() {
    int irNumber;

    printf("Please enter a number: ");
    scanf("%d",&irNumber);

    if (irNumber % 2 == 0){
        printf("The number %d you entered is even integer.",irNumber);
    }else{
        printf("The number %d you entered is odd integer.",irNumber);
    }

    return 0;
}
```

#### Output

```c
Please enter a number:25
The number 5 you entered is odd integer.
```

------------

### Example 2 - Bir karakterin sesli mi yoksa ünsüz mü olduğunu kontrol edin

```c
#include <stdio.h>

int main() {
    char myChar;
    int lowercase_vowels, uppercase_vowels;

    printf("Enter an alphabet chracter:");
    scanf("%c",&myChar);

    lowercase_vowels = (myChar == 'a' || myChar == 'e' || myChar == 'i'|| myChar == 'o' || myChar == "u");

    uppercase_vowels = (myChar == 'A' || myChar == 'E' || myChar == 'I'|| myChar == 'O' || myChar == "U");

    if (lowercase_vowels || uppercase_vowels){
        printf("%c is a vowel.", myChar);
    }else{
        printf("%c is a constant.", myChar);
    }
    return 0;
}
```

#### Output

```c
Enter an alphabet chracter:e
e is a vowel.
```

------------

### Example 3 - Üç sayı arasından en büyük sayıyı bulun

```c
#include <stdio.h>

int main() {
    int irNumber1 = 65, irNumber2 = 25, irNumber3 = 45;

    if(irNumber1>irNumber2 && irNumber1>irNumber3){
        printf("The first number is the largest number!");
    }else if (irNumber2>irNumber1 && irNumber2>irNumber3){
        printf("The second number is the largest number!");
    }else{
        printf("The third number is the largest number!");
    }
    return 0;
}
```

#### Output

```c
The first number is the largest number!
```

------------

### Example 4 - İkinci dereceden bir denklemin tüm köklerini bulun

```c
#include <stdio.h>
#include <math.h>

int main() {
    double discriminant,x,x1,x2,a,b,c,realPart,imagPart;

    printf("Please enter A value:");
    scanf("%lf",&a);

    printf("Please enter B value:");
    scanf("%lf",&b);

    printf("Please enter C value:");
    scanf("%lf",&c);

    discriminant = (b * b) - 4 * a * c;

    if (discriminant > 0 ){
        x1 = (-b + sqrt(discriminant)) / (2 * a);
        x2 = (-b - sqrt(discriminant)) / (2 * a);
        printf("The first root of this equation is: %lf and the second root is: %lf",x1,x2);
    } else if (discriminant == 0){
        x1 = x2 = -b / (2*a);
        printf("x1 = x2 = %lf",x1);
    } else{
        realPart = -b / (2 * a);
        imagPart = sqrt(-discriminant) / (2*a);
        printf("root1 = %.2lf+%.2lfi and root2 = %.2f-%.2fi", realPart, imagPart, realPart, imagPart);
    }

    return 0;
}
```

#### Output

```c
Please enter A value:5
Please enter B value:6
Please enter C value:7
root1 = -0.60+1.02i and root2 = -0.60-1.02i
```

------------

### Example 5 - Girilen Yılın Artık Yıl olup olmadığını kontrol edin

```c
#include <stdio.h>

int main() {
    int year;

    printf("Please enter the year: ");
    scanf("%d",&year);

    if ( year % 400 == 0){
        printf("%d is a leap year.", year);
    } else if (year % 100 == 0){
        printf("%d isn't a leap year.", year);
    } else if (year % 4 == 0){
        printf("%d is a leap year.", year);
    } else{
        printf("%d isn't a leap year.", year);
    }
    return 0;
}
```

#### Output

```c
Please enter the year: 2004
2004 is a leap year.
```

------------

### Example 6 - Bir Sayının Pozitif, Negatif veya Sıfır olup olmadığını kontrol edin.

```c
#include <stdio.h>

int main() {
    int irNumber;

    printf("Please enter a value : ");
    scanf("%d",&irNumber);

    if(irNumber == 0){
        printf("The number %d is equal to zero.",irNumber);
    }else if(irNumber > 0){
        printf("The number %d is greater than zero.",irNumber);
    }else{
        printf("The number %d is less than zero.",irNumber);
    }

    return 0;
}
```

#### Output

```c
Please enter a value : 25
The number 25 is greater than zero.
```

------------

### Example 7 - Bir karakterin alfabe olup olmadığını kontrol edin

```c
#include <stdio.h>

int main() {
    char myChar;

    printf("Please enter the alphabet:");
    scanf("%c",&myChar);

    if (isalpha(myChar)){
        printf("%c is an alphabet",myChar);
    }else{
        printf("%c isn't an alphabet",myChar);
    }

    return 0;
}
```

#### Output

```c
Please enter the alphabet:4
4 isn't an alphabet
```

------------

### Example 8 - Doğal sayıların toplamını bulun

```c
#include <stdio.h>

int main() {

    int total = 0, n;
    printf("Please enter the n value: ");
    scanf("%d",&n);

    for (int i = 0; i<=n; ++i){
        total += i;
    }

    printf("Total = %d", total);

    return 0;
}
```

#### Output

```c
Please enter the n value: 10
Total = 55
```

------------

### Example 9 - Bir sayının faktöriyelini bulun

```c
#include <stdio.h>

int main() {
    int n,total=1;

    printf("Please enter the n value: ");
    scanf("%d",&n);

    for (int i = 1; i<=n; ++i){
        total *= i;
    }

    printf("Factorial result: %d",total);
    return 0;
}
```

#### Output

```c
Please enter the n value: 5
Factorial result: 120
```

------------

### Example 10 - Çarpım tablosu oluştur

```c
#include <stdio.h>

int main() {
    int n,total=1;

    printf("Please enter the n value: ");
    scanf("%d",&n);

    for (int i = 1; i<=n; ++i){
        printf("%d * %d = %d \n",n,i,n*i);
    }

    return 0;
}
```

#### Output

```c
Please enter the n value: 10
10 * 1 = 10
10 * 2 = 20
10 * 3 = 30
10 * 4 = 40
10 * 5 = 50
10 * 6 = 60
10 * 7 = 70
10 * 8 = 80
10 * 9 = 90
10 * 10 = 100
```

------------

### Example 11 - Fibonacci serisini göster

```c
#include <stdio.h>

int main() {
    int n,total=1;
    int f1 = 0, f2 =1;
    int nextTerm = f1 + f2;

    printf("Please enter the n value: ");
    scanf("%d",&n);

    printf("Fibonacci series: f1 = %d and f2 = %d \n",f1,f2);

    for(int i = 3; i<=n; ++i){
        printf("%d, ",nextTerm);
        f1 = f2;
        f2 = nextTerm;
        nextTerm = f1 + f2;
    }

    return 0;
}
```

#### Output

```c
Please enter the n value: 15
Fibonacci series: f1 = 0 and f2 = 1
1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377,
```

------------

### Example 12 - İki sayının HCF'sini bulun

```c
#include <stdio.h>

int main() {
    int first,second,gcd;

    printf("Please enter the first number: ");
    scanf("%d",&first);

    printf("Please enter the second number: ");
    scanf("%d",&second);

    for(int i=1; i<= first && i<=second; ++i){
        if (first % i == 0  && second % i == 0){
            gcd = i;
        }
    }

    printf("G.C.D of %d and %d is %d",first,second,gcd);

    return 0;
}
```

#### Output

```c
Please enter the first number: 15
Please enter the second number: 25
G.C.D of 15 and 25 is 5
```

------------

### Example 13 - İki sayının LCM'sini bulun

```c
#include <stdio.h>

int main() {
    int first,second,gcd,lcm;

    printf("Please enter the first number: ");
    scanf("%d",&first);

    printf("Please enter the second number: ");
    scanf("%d",&second);

    for(int i=1; i<= first && i<=second; ++i){
        if (first % i == 0  && second % i == 0){
            gcd = i;
        }
    }
    lcm = (first * second)/gcd;
    printf("LCM of %d and %d is %d",first,second,lcm);

    return 0;
}
```

#### Output

```c
Please enter the first number: 25
Please enter the second number: 53
LCM of 25 and 53 is 1325
```

------------

### Example 14 - Bir tamsayının basamak sayısını bulun

```c
#include <stdio.h>

int main() {
    int irNumber, count = 0;

    printf("Please enter a number: ");
    scanf("%d",&irNumber);

    do{
        irNumber /= 10;
        ++count;
    }while(irNumber!=0);

    printf("Number of digits: %d",count);
    return 0;
}
```

#### Output

```c
Please enter a number: 53231
Number of digits: 5
```

------------

### Example 15 - Bir sayıyı ters çevirin

```c
#include <stdio.h>

int main() {
    int irNum, reverseNum =0 , remainder;

    printf("Please enter the n value: ");
    scanf("%d",&irNum);

    while(irNum !=0){
        remainder = irNum % 10;
        reverseNum = reverseNum * 10 + remainder;
        irNum/= 10;
    }
    printf("Reversed number: %d",reverseNum);
    return 0;
}
```

#### Output

```c
Please enter the n value: 125323
Reversed number: 323521
```

------------

### Example 16 - Bir sayının palindrom olup olmadığını kontrol edin

```c
#include <stdio.h>
int main() {
    int irNum, reverseNum =0 , remainder, tempNum;

    printf("Please enter the n value: ");
    scanf("%d",&irNum);
    tempNum = irNum;

    while(tempNum !=0){
        remainder = tempNum % 10;
        reverseNum = reverseNum * 10 + remainder;
        tempNum/= 10;
    }

    if (irNum == reverseNum){
        printf("%d is a palindrome number.",irNum);
    }else{
        printf("%d isn't a palindrome number.",irNum);
    }
    return 0;
}
```

#### Output

```c
Please enter the n value: 1001
1001 is a palindrome number.
```

------------

### Example 17 - Bir tamsayının asal olup olmadığını kontrol edin

```c
#include <stdio.h>

int main() {
    int irNum,blFlag = 0;

    printf("Please enter the number: ");
    scanf("%d",&irNum);

    if (irNum == 0 || irNum == 1){
        blFlag = 1;
    }

    for(int i=2; i<=irNum/2; ++i ){
        if (irNum % i == 0){
            blFlag = 1;
            break;
        }
    }

    if (blFlag == 0){
        printf("%i is a prime number.",irNum);
    }else{
        printf("%i is not a prime number.",irNum);
    }

    return 0;
}
```

#### Output

```c
Please enter the number: 47
47 is a prime number.
```

------------

### Example 18 - İki aralık arasındaki asal sayıları göster

```c
#include <stdio.h>

int main() {
    int irStartNum, irFinishNum,blFlag;

    printf("Type the initial value: ");
    scanf("%d",&irStartNum);

    printf("Type the ending value: ");
    scanf("%d",&irFinishNum);

    while(irStartNum < irFinishNum){
        blFlag = 0;

        if (irStartNum <= 1){
            ++irStartNum;
            continue;
        }

        for (int i=2; i<= irStartNum /2; ++i){
            if (irStartNum % 2 == 0){
                blFlag = 1;
                break;
            }
        }

        if (blFlag == 0){
            printf("%d ",irStartNum);
        }
        ++irStartNum;
    }

    return 0;
}
```

#### Output

```c
Type the initial value: 10
Type the ending value: 30
11 13 15 17 19 21 23 25 27 29
```

------------

### Example 19 - Armstrong numarasını kontrol edin

```c
// Online C compiler to run C program online
#include <stdio.h>

int main() {
    int irNumber,tempNumber,remainder,result=0;

    printf("Please enter the number: ");
    scanf("%d",&irNumber);

    tempNumber= irNumber;
    while(tempNumber != 0){
        remainder = tempNumber %10;
        result += remainder * remainder * remainder;
        tempNumber /= 10;
    }

    if (result == irNumber){
        printf("%d is an Armstrong number.",irNumber);
    }else{
        printf("%d is not an Armstrong number.",irNumber);
    }

    return 0;
}
```

#### Output

```c
Please enter the number: 371
371 is an Armstrong number.
```

------------

### Example 20 - Bir sayının çarpanlarını görüntüleme

```c
#include <stdio.h>

int main() {
    int irNumber;
    printf("Please enter the number: ");
    scanf("%d",&irNumber);

    for(int i =1; i<=irNumber; ++i){
        if (irNumber % i == 0){
            printf("%d \n",i);
        }
    }
    return 0;
}
```

#### Output

```c
Please enter the number: 532
1
2
4
7
14
19
28
38
76
133
266
532
```

------------

### Example 21 - Basit bir hesap makinesi oluşturun

```c
#include <stdio.h>

int main() {
    char myChar;
    int irFirstNum, irSecondNum, result;

    printf("Please choose a operator, your options are +,-,*,/,% : ");
    scanf("%c", &myChar);

    printf("Please enter first value then second value: ");
    scanf("%d%d",&irFirstNum,&irSecondNum);

    switch(myChar){
        case '+':
            result = irFirstNum + irSecondNum;
            break;
        case '-':
            result = irFirstNum - irSecondNum;
            break;
        case '*':
            result = irFirstNum * irSecondNum;
            break;
        case '/':
            result = irFirstNum / irSecondNum;
            break;
        case '%':
            result = irFirstNum % irSecondNum;
            break;
        default:
            break;
    }

    printf("The result of the operation with the first number: %d and the second number: %d you entered and the operator %c you selected: %d",irFirstNum,irSecondNum,myChar,result);

    return 0;
}
```

#### Output

```c
Please choose a operator, your options are +,-,*,/,% : *
Please enter first value then second value: 10
15
The result of the operation with the first number: 10 and the second number: 15 you entered and the operator * you selected: 150
```
