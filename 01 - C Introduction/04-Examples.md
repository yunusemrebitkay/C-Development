# Examples

### Example 1 - Bir cümle yazdırın

```c
#include <stdio.h>

int main() {
    printf("Hello world!");
    return 0;
}
```

#### Output

```c
Hello world!
```

---------------

### Example 2 - Kullanıcıdan aldığınız integer değeri yazdırın

```c
#include <stdio.h>

int main() {
    int irNumber;

    printf("Please enter a value: ");
    scanf("%d",&irNumber);

    printf("You entered is %d", irNumber);
    return 0;
}
```

#### Output

```c
Please enter a value: 15
You entered is 15
```

------------

#### Example 3 - Kullanıcıdan aldığınız iki değeri toplayın

```c
#include <stdio.h>

int main() {
    int firstNumber,secondNumber;

    printf("Please enter the first number: ");
    scanf("%d",&firstNumber);

    printf("Please enter the second number: ");
    scanf("%d",&secondNumber);

    printf("The sum of the numbers you entered: %d", firstNumber + secondNumber);
    return 0;
}
```

#### Output

```c
Please enter the first number: 15
Please enter the second number: 25
The sum of the numbers you entered: 40
```

------------

### Example 4 - İki float sayıyı çarpın

```c
#include <stdio.h>

int main() {
    float flFirstNumber,flSecondNumber;

    printf("Please enter the first float number: ");
    scanf("%f",&flFirstNumber);

    printf("Please enter the second float number: ");
    scanf("%f",&flSecondNumber);

    float result = flFirstNumber * flSecondNumber;
    printf("Multiplying the numbers you entered:: %.2f",result);
    return 0;
}
```

#### Output

```c
Please enter the first float number: 15.23
Please enter the second float number: 53.2
Multiplying the numbers you entered: 810.24
```

------------

### Example 5 - Kullanıcı tarafından girilen bir karakterin ASCII değerini bulun

```c
#include <stdio.h>

int main() {
    char myChar;

    printf("Please enter the character: ");
    scanf("%c", &myChar);

    printf("ASCII equivalent of the character you entered: %d",myChar);
    return 0;
}
```

#### Output

```c
Please enter the character: e
ASCII equivalent of the character you entered: 101
```

------------

##### Example 6 - İki Tam Sayının bölümünü ve kalanını bulun

```c
#include <stdio.h>

int main() {
    int num1,num2;

    printf("Please enter first value then second value: ");
    scanf("%d%d",&num1,&num2);

    printf("Division of numbers: %d and remainder: %d", num1 / num2, num1 % num2 );
    return 0;
}
```

#### Output

```c
Please enter first value then second value: 15
25
Division of numbers: 0 and remainder: 15
```

------------

##### Example 7 - int, float, double ve char boyutunu bulun

```c
#include <stdio.h>

int main() {
    int irNumber = 10;
    float flNumber = 15.42;
    double dbNumber = 27.321;
    char myChar = 'L';

    printf("Size of integer= %d \n", sizeof(irNumber));
    printf("Size of float= %d \n", sizeof(flNumber));
    printf("Size of double= %d \n", sizeof(dbNumber));
    printf("Size of char= %d \n", sizeof(myChar));

    return 0;
}
```

#### Output

```c
Size of integer= 4
Size of float= 4
Size of double= 8
Size of char= 1
```

------------

### Example 8 - İki sayıyı değiştir

```c
#include <stdio.h>

int main() {
    int newNumber, irNumber1 = 25, irNumber2 = 74;

    newNumber = irNumber1;
    irNumber1 = irNumber2;
    irNumber2 = newNumber;

    printf("Number 1 = %d, number 2 = %d",irNumber1,irNumber2);

    return 0;
}
```

#### Output

```c
Number 1 = 74, number 2 = 25
```
