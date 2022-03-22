# Storage Class
- C programlamadaki her değişkenin iki özelliği vardır: tip ve depolama sınıfı.
- Tür, bir değişkenin veri türünü ifade eder. Ve depolama sınıfı, bir değişkenin kapsamını, görünürlüğünü ve ömrünü belirler.

- 4 tür depolama sınıfı vardır:
- 1-) otomatik
- 2-) harici
- 3-) static
- 4-) register

------------
## Local Variable
- Bir blok içinde bildirilen değişkenler, otomatik veya yerel değişkenlerdir. Yerel değişkenler yalnızca bildirildiği bloğun içinde bulunur.

```c
#include <stdio.h>

int main() {
    for(int i=0; i<10; ++i){
        printf("C Programming Language \n");
    }

    // Error: i is not declared at this point-
    printf("%d",i);
    return 0;
}
```

------------
## Global Variable
- Tüm fonksiyonların dışında bildirilen değişkenler, harici veya global değişkenler olarak bilinir. Program içindeki herhangi bir fonksiyondan erişilebilirler.

```c
#include <stdio.h>

void display();
int n = 5; // Define Global Variable

int main() {
    ++n;
    display();
    return 0;
}

void display(){
    ++n;
    printf("%d",n);
}
```

### Output
```c
7
```

------------
## Register Variable
- Anahtar registerkelime, kayıt değişkenlerini bildirmek için kullanılır. Kayıt değişkenlerinin yerel değişkenlerden daha hızlı olması gerekiyordu.

- Bununla birlikte, modern derleyiciler kod optimizasyonunda çok iyidir ve kayıt değişkenlerini kullanmanın programınızı daha hızlı hale getirmesi gibi nadir bir şans vardır.

- Verilen uygulama için kodu nasıl optimize edeceğinizi bildiğiniz gömülü sistemler üzerinde çalışmıyorsanız, kayıt değişkenlerinin kullanımı yoktur.

------------

## Static Variable
- Statik bir değişkenin değeri programın sonuna kadar devam eder.

```c
#include <stdio.h>

void display();

int main() {
    display();
    display();
    display();
    display();

    return 0;
}

void display(){
    static int num = 2;
    num += 4;
    printf("%d \n",num);
}
```

### Output

```c
6
10
14
18
```

