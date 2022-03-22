# Functions

- if C programlamasında ifadenin sözdizimi şöyledir:

```c
if (test expression)
{
   // code
}
```

------------

### Example 1 - If

```c
#include <stdio.h>

int main() {
    int irNumber;

    printf("Please enter a number: ");
    scanf("%d",&irNumber);

    if (irNumber < 0){
        printf("The number %d you entered is less than 0.",irNumber);
    }

    return 0;
}
```

#### Output

```c
Please enter a number: -5
The number -5 you entered is less than 0.
```

------------

### Example 1 - f ... Else

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
Please enter a number: 25
The number 25 you entered is odd integer.
```

------------

### Example 1 - If ... Else If ... Else

```c
#include <stdio.h>

int main() {
    int irFirstNum,irSecondNum;

    printf("Please enter first number then second number: ");
    scanf("%d%d",&irFirstNum,&irSecondNum);

    if (irFirstNum == irSecondNum){
        printf("The two numbers you entered are equal.");
    }else if (irFirstNum > irSecondNum) {
        printf("The first value you enter is greater than the second value.");
    }else{
        printf("The second value you enter is greater than the first value.");
    }

    return 0;
}
```

#### Output

```c
Please enter first number then second number: 15
25
The second value you enter is greater than the first value.
```
