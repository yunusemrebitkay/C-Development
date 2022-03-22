# Loops

## For Loop

- for Döngünün sözdizimi şöyledir:

```c
for (initializationStatement; testExpression; updateStatement)
{
    // statements inside the body of loop
}
```

### For Loop Example

```c
#include <stdio.h>

int main() {

    for(int i = 0; i <= 10; ++i){
        printf("i = %d \n",i);
    }

    return 0;
}
```

#### Output

```c
i = 0
i = 1
i = 2
i = 3
i = 4
i = 5
i = 6
i = 7
i = 8
i = 9
i = 10
```

------------

## Switch Loop

- Switch Döngünün sözdizimi şöyledir:

```c
switch (expression)
{
    case constant1:
      // statements
      break;

    case constant2:
      // statements
      break;
    .
    .
    .
    default:
      // default statements
}
```

### Switch Loop Example

```c
#include <stdio.h>

int main() {
    char myChar;
    int irNumber1 = 15, irNumber2 = 25, result;

    printf("Please choose a operator, your options are +,-,*,/,% : ");
    scanf("%c", &myChar);

    switch(myChar){
        case '+':
            result = irNumber1 + irNumber2;
            break;
        case '-':
            result = irNumber1 - irNumber2;
            break;
        case '*':
            result = irNumber1 * irNumber2;
            break;
        case '/':
            result = irNumber1 / irNumber2;
            break;
        case '%':
            result = irNumber1 % irNumber2;
            break;
        default:
            break;
    }

    printf("The result of the operation with the operator you entered: %d",result);

    return 0;
}
```

#### Output

```c
Please choose a operator, your options are +,-,*,/,% : *
The result of the operation with the operator you entered: 375
```

------------

## While Loop

- while Döngünün sözdizimi şöyledir:

```c
while (testExpression) {
  // the body of the loop
}
```

### While Loop Example

```c
#include <stdio.h>

int main() {
    int i=1;

    while(i <= 15){
        printf("i = %d \n",i);
        ++i;
    }

    return 0;
}
```

#### Output

```c
i = 1
i = 2
i = 3
i = 4
i = 5
i = 6
i = 7
i = 8
i = 9
i = 10
i = 11
i = 12
i = 13
i = 14
i = 15
```

------------

## Do ... While Loop

- do...while Döngünün sözdizimi şöyledir:

```c
do {
  // the body of the loop
}
while (testExpression);
```

### Do ... While Loop Example

```c
#include <stdio.h>

int main() {
    double dbNumber, dbSum = 0;

    do{
        printf("Enter a number: ");
        scanf("%lf", &dbNumber);
        dbSum += dbNumber;
    }while( dbNumber != 0.0);

    printf("Sum = %.2lf",dbSum);

    return 0;
}
```

#### Output

```c
Enter a number: 25
Enter a number: 23
Enter a number: 42
Enter a number: 643
Enter a number: 32
Enter a number: 0.0
Sum = 765.00
```

------------

## Break Command

- Break ifadesi, karşılaştığı anda döngüyü hemen sonlandırır.

```c
#include <stdio.h>

int main() {
    double dbNumber, dbSum = 0;

    for (int i = 1; i <= 10; ++i){
        printf("Enter a number: ");
        scanf("%lf", &dbNumber);

        if (dbNumber < 0.0){
            break;
        }

        dbSum += dbNumber;
    }

    printf("Sum = %.2lf",dbSum);

    return 0;
}
```

#### Output

```c
Enter a number: 25
Enter a number: 23
Enter a number: 3254
Enter a number: 323
Enter a number: -5
Sum = 3625.00
```

------------

## Continue Command

- Continue ifadesi , döngünün geçerli yinelemesini atlar ve bir sonraki yinelemeyle devam eder.

```c
#include <stdio.h>

int main() {
    double dbNumber, dbSum = 0;

    for (int i = 1; i <= 10; ++i){
        printf("Enter a number: ");
        scanf("%lf", &dbNumber);

        if (dbNumber < 0.0){
            continue;
        }

        dbSum += dbNumber;
    }

    printf("Sum = %.2lf",dbSum);

    return 0;
}
```

#### Output

```c
Enter a number: 15
Enter a number: 25
Enter a number: 32
Enter a number: -5
Enter a number: 32
Enter a number: 42
Enter a number:
```

------------

## Goto Statement

- Goto ifadesi , programın kontrolünü belirtilen yere aktarmamızı sağlar.

```c
goto label;
... .. ...
... .. ...
label:
statement;
```

### Goto Statement Example

```c
#include <stdio.h>

int main() {
    const int maxInput = 6;
    int i;
    double dbNumber,dbAverage,dbSum = 0.0;

    for(i = 1; i < maxInput; ++i){
        printf("Please enter a number:");
        scanf("%lf",&dbNumber);

        if (dbNumber < 0.0){
            goto jump;
        }

        dbSum += dbNumber;
    }

    jump:
        dbAverage = dbSum / i-1;
        printf("Sum = %.2f \n", dbSum);
        printf("Average = %.2f \n", dbAverage);

    return 0;
}
```

#### Output

```c
Please enter a number:43
Please enter a number:32
Please enter a number:54
Please enter a number:65
Please enter a number:0.0
Sum = 194.00
Average = 31.33
```
