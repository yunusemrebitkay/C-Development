# Variables and Constants

- Depolama alanını belirtmek için her değişkene benzersiz bir ad ( tanımlayıcı ) verilmelidir. Değişken adları, yalnızca bir bellek konumunun sembolik temsilidir.

------------

## 1. Const

- Değeri değiştirilemeyecek bir değişken tanımlamak istiyorsanız constanahtar kelimeyi kullanabilirsiniz. Burada,PIsembolik bir sabittir; değeri değiştirilemez.

```c
const double PI = 3.14;
PI = 2.9; // Error
```

------------

## 2. Integer

- %d ile yazdırılır. 2 veya 4 byte bellekte yer kaplar.
- Tam sayılar, hem sıfır, hem pozitif hem de negatif değerlere sahip olabilen ancak ondalık değeri olmayan tam sayılardır.

```c
int id, age;
id = 15;
age = 25;
```

------------

## 3.Float and Double

- Float %f ile double ise %lf ile yazdırılır. Float 4 byte double ise 8 byte bellekte yer kaplar.
- Float ve double gerçek sayıları tutmak için kullanılır.

```c
float flNum = 15.432;
double dbNum = 23.512323;
```

------------

## 4.Char

- %c ile yazdırılır. 1 byte bellekte yer kaplar.
- Karakter tipi değişkenleri bildirmek için kullanılır.

```c
char myChar = 'E';
```

------------

## 5.Long and Short

- Büyük bir sayı kullanmanız gerekiyorsa, long kullanır. Küçük sayı için ise short kullanılır.

```c
short shDoorNumber = 5;
long lnSchoolId = 19500001;
```

------------

## 6. Unsigned Numbers

- Sadece pozitif sayıların saklanmasına izin verir.

```c
// invalid code: unsigned int cannot hold negative integers
unsigned int x = -35;
```

---

## Learning variable size with sizeof()

```c
#include <stdio.h>

int main() {
    short x;
    long y;
    long long z;
    long double r;

    printf("Size of short => %d bytes \n",sizeof(x)); // Size of short => 2 bytes
    printf("Size of long => %d bytes \n",sizeof(y)); // Size of long => 8 bytes
    printf("Size of long long => %d bytes \n",sizeof(z)); // Size of long long => 8 bytes
    printf("Size of long double => %d bytes \n",sizeof(r)); // Size of long double => 16 bytes

    return 0;
}
```
