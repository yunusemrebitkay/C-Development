# Functions

- İşlev, belirli bir görevi gerçekleştiren bir kod bloğudur.

------------
## Fonksiyon türleri

- C programlamada iki tür fonksiyon vardır:

1.  Standart kitaplık işlevleri
2.  Kullanıcı tanımlı fonksiyonlar

------------
### Standart kitaplık işlevleri

- Standart kitaplık işlevleri, C programlamada yerleşik işlevlerdir.

------------
### Kullanıcı tanımlı fonksiyon

- Ayrıca ihtiyacınıza göre işlevler de oluşturabilirsiniz. Kullanıcı tarafından oluşturulan bu tür işlevler, kullanıcı tanımlı işlevler olarak bilinir.

------------
#### Example

```c
#include <stdio.h>
int addNumbers(int x,int y);

int main() {
    int num1,num2,sum;

    printf("Please enter first value: ");
    scanf("%d",&num1);

    printf("Please enter second value: ");
    scanf("%d",&num2);

    sum = addNumbers(num1,num2);
    printf("Sum => %d",sum);
    return 0;
}

int addNumbers(int x, int y){
    int result;
    result = x + y;
    return result;
}
```

#### Output

```c
Please enter first value: 15
Please enter second value: 25
Sum => 40
```

------------
## Fonksiyon prototipi

- Bir işlev prototipi, basitçe, işlevin adını, parametrelerini ve dönüş türünü belirten bir işlevin bildirimidir. Fonksiyon gövdesi içermez.

------------
### İşlev prototipinin sözdizimi

```c
dönüşTürü işlevAdı(tür1 bağımsız değişken1, tür2 bağımsız değişken2, ...);

```

------------
### Bir işlevi çağırmak

- Programın kontrolü, çağrılarak kullanıcı tanımlı fonksiyona aktarılır.

------------
### İşlev çağrısının sözdizimi

```c
fonksiyonAdı(argüman1, argüman2, ...);

```

### Return işlevi

- İşlevden döndürülen değer türü ile işlev prototipinde ve işlev tanımında belirtilen dönüş türü eşleşmelidir.

------------
## Fonksiyon Türleri

### Argüman Geçilmedi ve Dönüş Değeri Yok

```c
#include <stdio.h>
void greetPeople();

int main() {
    greetPeople();
    return 0;
}

void greetPeople(){
    printf("Hello world!");
}
```

#### Output

```c
Hello world!
```

------------
### Hiçbir Argüman Geçilmedi Ama Bir Değer Döndürüyor

```c
#include <stdio.h>
int getInput();

int main() {
    int irNumber;
    irNumber = getInput();
    printf("Your entered number is %d",irNumber);
    return 0;
}

int getInput(){
    int num;
    printf("Please enter the number: ");
    scanf("%d",&num);
    return num;
}
```

#### Output

```c
Please enter the number: 25
Your entered number is 25
```

------------
### Argüman Başarılı Ama Dönüş Değeri Yok

```c
#include <stdio.h>
int calculate(int x,int y);

int main() {
    int num1,num2;
    printf("Please enter the first number: ");
    scanf("%d",&num1);

    printf("Please enter the second number: ");
    scanf("%d",&num2);

    calculate(num1,num2);
    return 0;
}

int calculate(int x,int y){
    printf("Multiplying the numbers you entered: %d", x * y);
}
```

#### Output

```c
Please enter the first number: 15
Please enter the second number: 25
Multiplying the numbers you entered: 375
```

------------
### Argüman Geçti ve Bir Değer Döndürdü

```c
#include <stdio.h>
int calculate(int x,int y);

int main() {
    int num1,num2,result;
    printf("Please enter the first number: ");
    scanf("%d",&num1);

    printf("Please enter the second number: ");
    scanf("%d",&num2);

    result = calculate(num1,num2);
    printf("Adding the numbers you entered: %d", result);
    return 0;
}

int calculate(int x,int y){
   return x + y;
}
```

#### Output

```c
Please enter the first number: 25
Please enter the second number: 32
Adding the numbers you entered: 57
```

------------
### Hangi yaklaşım daha iyi?

- Peki, çözmeye çalıştığınız soruna bağlı. Bu durumda, bir argüman iletmek ve fonksiyondan bir değer döndürmek (örnek 4) daha iyidir.

------------
### Recursion

- Kendini çağıran bir işlev, özyinelemeli bir işlev olarak bilinir. Ve bu teknik özyineleme olarak bilinir.

------------
### Özyineleme nasıl çalışır?

```c
void recurse()
{
    ... .. ...
    recurse();
    ... .. ...
}

int main()
{
    ... .. ...
    recurse();
    ... .. ...
}
```

------------
### Özyinelemeyi Kullanan Doğal Sayıların Toplamı

```c
#include <stdio.h>
int sum(int x);

int main() {
    int num,result;
    printf("Please enter the number: ");
    scanf("%d",&num);

    result = sum(num);
    printf("Sum of natural numbers up to %d: %d", num,result);
    return 0;
}

int sum(int x){
   if (x != 0){
       return x + sum(x-1);
   }else{
       return x;
   }
}
```

#### Output

```c
Please enter the number: 15
Sum of natural numbers up to 15: 120
```

