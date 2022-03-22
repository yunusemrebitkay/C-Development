# C Input Output (I/O)

- C programlamada, printf()ana çıkış işlevlerinden biridir. İşlev, formatlanmış çıktıyı ekrana gönderir.

```c
#include <stdio.h>

int main() {
    printf("Hello world!");
    return 0;
}
```

------------

## Veri Tipleri Çıkışı

### Integer

- %d ile yazdırılır.

```c
#include <stdio.h>
int main()
{
    int irNumber = 25;
    printf("Number = %d", irNumber);
    return 0;
}
```

##### Output

```c
Number = 25
```

------------

### Float and Double

- Float %f ile Double ise %lf ile yazdırılır.

```c
#include <stdio.h>
int main()
{
    float flNumber = 15.2323;
    double dbNumber = 26.32312;

    printf("Float Number = %.2f \n", flNumber);
    printf("Double Number = %.2lf \n", dbNumber);

    return 0;
}
```

##### Output

```c
Float Number = 15.23
Double Number = 26.32
```

------------

### Char

- %c ile yazdırılır.

```c
#include <stdio.h>
int main() {
    char myChar = 'L';
    printf("Char is %c",myChar);
    return 0;
}
```

##### Output

```c
Char is L
```

------------

## Veri Tipleri Girişi

### Integer

```c
#include <stdio.h>

int main() {
    int irNumber;
    printf("Please enter the integer number: ");
    scanf("%d", &irNumber);
    printf("The value you entered: %d",irNumber);
    return 0;
}
```

##### Output

```c
Please enter the integer number: 15
The value you entered: 15
```

---------------

### Float and Double

```c
#include <stdio.h>

int main() {
    float flNumber;
    double dbNumber;

    printf("Please enter the float number: ");
    scanf("%f", &flNumber);

    printf("Please enter the double number: ");
    scanf("%lf", &dbNumber);

    printf("The value you entered: %.2f \n",flNumber);
    printf("The value you entered: %.2lf \n",dbNumber);

    return 0;
}
```

##### Output

```c
Please enter the float number: 15.32
Please enter the double number: 23.46
The value you entered: 15.32
The value you entered: 23.46
```

------------

### Char

```c
#include <stdio.h>

int main() {
    char myChar;

    printf("Please enter the character: ");
    scanf("%c", &myChar);

    printf("The value you entered: %c", myChar);
    return 0;
}
```

##### Output

```c
Please enter the character: l
The value you entered: l
```

------------

### ASCII Değeri

- Karakteri görüntülemek için kullanırsak %d, ASCII değeri yazdırılır.

```c
#include <stdio.h>
int main() {
    char myChar;

    printf("Please enter the character: ");
    scanf("%c", &myChar);

    printf("The value you entered: %c \n", myChar);
    printf("The value you entered with ASCII: %d \n", myChar);

    return 0;
}
```

##### Output

```c
Please enter the character: l
The value you entered: l
The value you entered with ASCII: 108
```

------------

### G/Ç Çoklu Değerleri

- Kullanıcıdan birden çok girdi alabiliriz.

```c
#include <stdio.h>

int main() {

    int irNumber;
    float flNumber;

    printf("Please enter first the integer value then float value: ");
    scanf("%d%f",&irNumber,&flNumber);

    printf("You entered integer value: %d and float value: %.2f",irNumber,flNumber);

    return 0;
}
```

##### Output

```c
Please enter first the integer value then float value: 25
17.5
You entered integer value: 25 and float value: 17.50
```
