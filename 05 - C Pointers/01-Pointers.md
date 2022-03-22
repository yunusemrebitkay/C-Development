# Pointers

## Adress

- Bir değişkeniniz varsa programınızda &var ile size hafızadaki adresini verecektir.

```c
#include <stdio.h>

int main() {
    int x,y;

    printf("x adress = %d \n",&x);
    printf("x adress = %d \n",&y);

    return 0;
}
```

------------

## Pointers

- İşaretçiler değerler yerine adresleri depolamak için kullanılan özel değişkenlerdir.

### İşaretçi Sözdizimi

```c
int* p;
int *p1;
int * p2;
```

- Burada sadece p1'i işaretçi seçtik.

```c
int* p1,c;
```

------------
### İşaretçilere adres atama

```c
#include <stdio.h>

int main() {
    int* x,y;
    y = 10;
    x = &y;

    return 0;
}
```

------------
### İşaretçilerle İşaret Edilen Şeyin Değerini Alın

```c
#include <stdio.h>

int main() {
    int* x,y;
    y = 10;
    x = &y;
    printf("%d",*x); // Output 10

    return 0;
}
```
#### Output

```c
10
```

------------
### İşaretçilerin Gösterdiği Değeri Değiştirme

```c
#include <stdio.h>

int main() {
    int* x,y;
    y = 10;
    x = &y;
    y = 15;

    printf("y = %d \n",y);
    printf("*x = %d",*x);

    return 0;
}
```

#### Output

```c
y = 15
*x = 15
```

------------
### Example: Working of Pointers

```c
#include <stdio.h>

int main() {
    int *pX, x;

    x = 25;
    printf("Address of x => %d \n",&x);
    printf("Value of x => %d \n",x);

    pX = &x;
    printf("Address of pX => %d \n",pX);
    printf("Content of pX => %d \n",*pX);

    x = 35;
    printf("Address of pX => %d \n",pX);
    printf("Content of pX => %d \n",*pX);

    *pX = 15;
    printf("Address of x => %d \n",&x);
    printf("Value of x => %d \n",x);

    return 0;
}
```

#### Output

```c
Address of x => -405443076
Value of x => 25
Address of pX => -405443076
Content of pX => 25
Address of pX => -405443076
Content of pX => 35
Address of x => -405443076
Value of x => 15
```

------------
## Explanation of the program

### 1 - int \*pc, c;

- Burada bir işaretçi "pc" ve normal bir değişken olan "c" var. Her iki tür de int'den oluşur.
- İkiside daha başlatılmadı. Bu yüzden işaretçi "pc" adres olmaz veya rastgele bir adresi işaret eder. C değişkenin bir adresi var ancak değeri rastgele değersiz bir değerdir.

<img src="https://i.hizliresim.com/ihtynmy.png" width="150" height="150">

------------

### 2 - c = 25

- C değişkenine 25 atadık. 25 değeri değişkenin hafıza konumunda saklanır.

<img src="https://i.hizliresim.com/fbgkpue.png" width="150" height="150">

------------

### 3 - pc = &c

- C değişkenin adresini pc değişkenine atadık.

<img src="https://i.hizliresim.com/fcdjvx4.png" width="150" height="150">

------------

### 4 - c = 64

- C değişkenine 64 atadık.

<img src="https://i.hizliresim.com/dcuijmi.png" width="150" height="150">

------------

### 5 - \*pc = 12

- İşaretçi tarafından gösterilen bellek konumundaki değeri değiştirir.

<img src="https://i.hizliresim.com/kaiuvch.png" width="150" height="150">

------------

### Common mistakes when working with pointers

```c
int c, *pc;

// pc bir adres fakat c değil!
pc = c; // Error

// &c bir adres fakat *pc değil!
*pc = &c; // Error

// İkiside adres!
pc = &c; // Not an error

// İkiside değer!
*pc = c;
```

