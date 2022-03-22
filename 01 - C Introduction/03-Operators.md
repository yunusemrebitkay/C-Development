# Operators

## Arithmetic Operators

| Operator | Meaning of Operator |
| :------: | :-----------------: |
|    +     |      Addition       |
|    -     |     Subtraction     |
|    \*    |   Multiplication    |
|    /     |      Division       |
|    %     |   Modulo division   |

------------

## Increment and Decrement Operators

```c
#include <stdio.h>

int main() {
    int x = 15, y = 25;
    float z = 18.7, r = 23.32;

    printf("++x => %d \n", ++x); // ++x => 16
    printf("--y => %d \n", --y); // --y => 24
    printf("++z => %.2f \n", ++z); // ++z => 19.700001
    printf("--r => %.2f \n", --r); // --r => 22.320000

    return 0;
}
```

### Output

```c
++x => 16
--y => 24
++z => 19.70
--r => 22.32
```

------------

## Assignment Operators

| Operator |  Same as  | Example |
| :------: | :-------: | :-----: |
|    =     |   x = y   |  x = y  |
|    +=    |  x = x+y  | x += y  |
|    -=    |  x = x-y  | x -= y  |
|   \*=    | x = x\*y  | x \*= y |
|    /=    |  x = x/y  | x /= y  |
|    %=    | x = x % y | x %= y  |

------------

## Comparison Operators

| Operator |   Meaning of Operator    |         Example          |
| :------: | :----------------------: | :----------------------: |
|    ==    |         Equal to         | 8 == 5 is evaluated to 0 |
|    >     |       Greater than       | 8 > 5 is evaluated to 1  |
|    <     |        Less than         | 8 < 5 is evaluated to 0  |
|    !=    |       Not equal to       | 8 != 5 is evaluated to 1 |
|    >=    | Greater than or equal to | 8 >= 5 is evaluated to 1 |
|    <=    |  Less than or equal to   | 8 <= 5 is evaluated to 0 |

## Logical Operators

| Operator | Meaning of Operator |          Example           |
| :------: | :-----------------: | :------------------------: |
|    &&    |     Logical And     | if ((x == 5) && (y == 3 )) |
|    II    |     Logical Or      | if ((x == 5) II (y == 3 )) |
|    !     |     Logical Not     |        if !(x == 5)        |

## Bitwise Operators

| Operator | Meaning of Operator |
| :------: | :-----------------: |
|    &     |     Bitwise AND     |
|    I     |     Bitwise OR      |
|    ^     |     Bitwise NOR     |
|    ~     | Bitwise Complement  |
|    <<    |     Shift Left      |
|    >>    |     Shift Right     |

------------

## Comma Operator

- Virgül operatörleri, ilgili ifadeleri birbirine bağlamak için kullanılır.

```c
int a,c = 5,d;
```
