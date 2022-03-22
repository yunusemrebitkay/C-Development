# Arrays

- Dizi, birden çok değer depolayabilen bir değişkendir. Örneğin, 100 tamsayı saklamak istiyorsanız, bunun için bir dizi oluşturabilirsiniz.

```c
int data[100];
```


------------
## Bir dizi nasıl bildirilir?

```c
dataType diziAdı[diziSize];
```

------------
## Dizi Öğelerine Erişim

- Bir dizinin elemanlarına indekslerle erişebilirsiniz.

- Bir dizi bildirdiğinizi varsayalım işaret yukarıdaki gibi. İlk eleman işaret[0], ikinci unsur işaret[1] ve bunun gibi.

------------
## Birkaç önemli not :

- Dizilerin ilk indeksi 1 değil 0'dır
- Başlangıç adresinin 2120d mark[0] olduğunu varsayalım . Ardından, adresi 2124d olacaktır . Benzer şekilde, adresi 2128d olacaktır vb. Bunun nedeni, a'nın boyutunun 4 bayt olmasıdır.

## Bir dizi nasıl başlatılır?

```c
int arrayNumbers[10] = {0,1,2,3,4,5,6,7,8,9,10};
```

- Aşağıda boyutu belirtmedik. Ancak, biz onu 5 elemanla başlattığımız için derleyici boyutunun 5 olduğunu biliyor.

```c
int arrayNumbers[] = {0,1,2,3,4,5,6,7,8,9,10};
```

------------
## Dizi öğelerinin Değerini Değiştir

```c
#include <stdio.h>

int main() {
    int arrayNumbers[] = {0,1,2,3,4,5,6,7,8,9,10};
    arrayNumbers[2] = 25;
    arrayNumbers[7] = -3;

    printf("Third element of the array: %d\n", arrayNumbers[2]);
    printf("8th element of the array: %d\n", arrayNumbers[7]);

    return 0;
}
```

### Output

```c
Third element of the array: 25
8th element of the array: -3
```

------------
## Giriş ve Çıkış Dizi Elemanları

- Kullanıcıdan girdiyi nasıl alıp bir dizi öğesinde saklayabileceğiniz aşağıda açıklanmıştır.

```c
#include <stdio.h>

int main() {
    int arrayNumbers[] = {0,1,2,3,4,5,6,7,8,9,10};

    printf("Please enter new third element value: ");
    scanf("%d", &arrayNumbers[2]);

    printf("Please enter new 8th element value: ");
    scanf("%d", &arrayNumbers[7]);

    printf("Third element of the array: %d\n", arrayNumbers[2]);
    printf("8th element of the array: %d\n", arrayNumbers[7]);

    return 0;
}
```

### Output

```c
Please enter new third element value: 25
Please enter new 8th element value: 53
Third element of the array: 25
8th element of the array: 53
```

------------
## Example 1 - Array Input/Output

```c
#include <stdio.h>

int main() {
    int arrayNumbers[5];

    for(int i=0; i<5; ++i){
        printf("Please enter %d. value: ",i);
        scanf("%d",&arrayNumbers[i]);
    }

    for(int i=0; i<5; ++i){
        printf("%d\n",arrayNumbers[i]);
    }

    return 0;
}
```

### Output

```c
Please enter 0. value: 52
Please enter 1. value: 32
Please enter 2. value: 54
Please enter 3. value: 532
Please enter 4. value: 2
52
32
54
532
2
```

------------
## Example 2 - Calculate Average

```c
#include <stdio.h>

int main() {
    int arrayNumbers[10],n, total=0, average;

    printf("Please enter the n value: ");
    scanf("%d",&n);

    for(int i=0; i<n; ++i){
        printf("Please enter %d. value: ",i);
        scanf("%d",&arrayNumbers[i]);
        total +=arrayNumbers[i];
    }

    average = total / n;
    printf("Average = %d",average);

    return 0;
}
```

### Output

```c
Please enter the n value: 3
Please enter 0. value: 10
Please enter 1. value: 15
Please enter 2. value: 20
Average = 15
```
