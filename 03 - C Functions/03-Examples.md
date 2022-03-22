# Examples

### Example 1 - Özyinelemeyi Kullanarak Bir Cümleyi Ters Çevirme

```c
#include <stdio.h>

void reverseSentence();

int main() {
    printf("Please enter the chracter value: ");
    reverseSentence();
    return 0;
}

void reverseSentence(){
    char myChar;
    scanf("%c", &myChar);

    if (myChar != '\n'){
        reverseSentence();
        printf("%c",myChar);
    }
}
```

#### Output

```c
Please enter the character value: alfa matik
kitam afla
```

------------
### Example 2 - Özyinelemeyi Kullanarak Bir Sayının Faktöriyelini Bulun

```c
#include <stdio.h>

int multNumbers(int n);

int main() {
    int number;
    printf("Please enter the number: ");
    scanf("%d",&number);
    printf("%d! factorial => %d",number,multNumbers(number));
    return 0;
}

int multNumbers(int n){
    if (n >=1){
        return n * multNumbers(n-1);
    }else{
        return 1;
    }
}
```

#### Output

```c
Please enter the number: 5
5! factorial => 120
```

------------
### Example 3 - Özyinelemeyi kullanarak üslü sayıyı hesaplayın

```c
#include <stdio.h>

int power(int base,int exp);

int main() {
    int base,exp;
    printf("Please enter the base: ");
    scanf("%d",&base);

    printf("Please enter the exp: ");
    scanf("%d",&exp);

    printf("Calculated power value of the numbers %d and %d: => %d",base,exp,power(base,exp));
    return 0;
}

int power(int base,int exp){
    if (exp != 0){
        return (base * power(base, exp-1));
    }else{
        return 1;
    }
}
```

#### Output

```c
Please enter the base: 4
Please enter the exp: 4
Calculated power value of the numbers 4 and 4: => 256
```

------------
### Example 4 - Fonksiyonu Kullanarak Aralıklar Arasındaki Asal Sayıları Görüntüleme

```c
#include <stdio.h>

int checkPrime(int n);

int main() {
    int start,finish,blFlag;
    printf("Please enter the start value: ");
    scanf("%d",&start);

    printf("Please enter the finish value: ");
    scanf("%d",&finish);

    printf("Printing prime numbers between numbers %d and %d => ",start,finish);
    for(int i= start +1; i < finish; ++i){
        blFlag = checkPrime(i);

        if (blFlag == 1){
            printf("%d ",i);
        }
    }

    return 0;
}

int checkPrime(int n){
    int  blFlag = 1;

    for (int i=2; i<= n/2; ++i){
        if ( n % i == 0){
            blFlag = 0;
            break;
        }
    }

    return blFlag;
}
```

#### Output

```c
Please enter the start value: 10
Please enter the finish value: 100
Printing prime numbers between numbers 10 and 100 => 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97
```

------------
### Example 5 - Sekizli Sayıyı Ondalık Sayıya Dönüştür ve tam tersi

```c
#include <stdio.h>
#include <math.h>

int convertDecimalToOctal(int decimalValue);

int main() {
    int decimalNum;
    printf("Please enter the decimal value: ");
    scanf("%d",&decimalNum);

    printf("%d in decimal = %d in octal",decimalNum,convertDecimalToOctal(decimalNum));

    return 0;
}

int convertDecimalToOctal(int decimalValue){
    int octalNumber = 0, i = 1;

    while(decimalValue != 0){
        octalNumber += (decimalValue%8)*i;
        decimalValue /= 8;
        i *=10;
    }
    return octalNumber;
}
```

#### Output

```c
Please enter the decimal value: 1321532
1321532 in decimal = 5025074 in octal
```
