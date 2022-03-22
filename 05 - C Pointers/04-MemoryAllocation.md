# Dynamic Memory Allocation

- Bildiğiniz gibi dizi, sabit sayıda değerden oluşan bir koleksiyondur. Bir dizinin boyutu bildirildiğinde, onu değiştiremezsiniz.

- Bazen bildirdiğiniz dizinin boyutu yetersiz olabilir. Bu sorunu çözmek için, çalışma zamanı sırasında manuel olarak bellek ayırabilirsiniz. Bu, C programlamada dinamik bellek ayırma olarak bilinir.

------------
## Malloc()
- "Malloc" adı, bellek ayırma anlamına gelir. Malloc(), belirtilen bayt sayısına sahip bir bellek bloğunu rezerve eder.
- Ve herhangi bir biçimdeki işaretçilere dönüştürülebilen bir işaretçi döndürür .

### malloc() sözdizimi

```c
ptr = (castType*) malloc(size);
```

#### Example

```c
ptr = (int*) malloc(100 * sizeof(int));
```
- Yukarıdaki ifade de bellekte 400 byte yer ayırılır. Çünkü int 4 byte yer kaplar.
- Ve, ptr işaretçisi bellekte ayrılan ilk byte'ın yerini tutar. "Null" bellek tahsis edilmezse, ifade bir işaretçi ile sonuçlanır.

------------
## Calloc()
- "Calloc" adı, bitişik tahsis anlamına gelir.
- İşlevi, belleği ayırır ve tüm bitleri sıfırdan başlatır.

### calloc() sözdizimi

```c
ptr = (castType*) calloc(size);
```

#### Example

```c
ptr = (int*) calloc(25, sizeof(int));
```
- Yukaridaki ifade de, int türünde 25 öğe için bellekte bitişik yer ayırır.

------------
## Free()
- Calloc ve Malloc ile kendi başlarına serbest bırakılmayan dinamik olarak ayrılmış belleği serbest bırakmak için kullanılır.

### free() sözdizimi

```c
free(ptr);
```

- Bu ifade ile gösterilen bellekte ayrılan alan serbetst bırakılır.

------------
### Example - Malloc() and Free()

```c
#include <stdio.h>
#include <stdlib.h>


int main() {
    int n ,*ptr,total=0;

    printf("Please enter the n value: ");
    scanf("%d", &n);

    ptr = (int*) malloc(n * sizeof(int));

    if (ptr == NULL){
        printf("Error! memory not allocated!");
        exit(0);
    }

    for(int i=0; i<n; ++i){
        printf("Please enter %d. element= ",i);
        scanf("%d",ptr+i);

        total += *(ptr+i);
    }

    printf("Total => %d",total);

    free(ptr);
    return 0;
}
```

------------
### Example - Calloc() and Free()

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n ,*ptr,total=0;

    printf("Please enter the n value: ");
    scanf("%d", &n);

    ptr = (int*) calloc(n, sizeof(int));

    if (ptr == NULL){
        printf("Error! memory not allocated!");
        exit(0);
    }

    for(int i=0; i<n; ++i){
        printf("Please enter %d. element= ",i);
        scanf("%d",ptr+i);

        total += *(ptr+i);
    }

    printf("Total => %d",total);

    free(ptr);
    return 0;
}
```

------------
## Realloc()
- Dinamik olarak ayrılan bellek yetersiz veya gerekenden fazlaysa, realloc()işlevi kullanarak önceden ayrılmış belleğin boyutunu değiştirebilirsiniz.

### realloc() sözdizimi

```c
ptr = realloc(ptr,x);
```

#### Example

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n1,n2 ,*ptr,total=0;

    printf("Please enter the size (n1) value: ");
    scanf("%d", &n1);

    ptr = (int*) malloc(n1 * sizeof(int));

    printf("Addresses of previously allocated memory: \n");
    for(int i=0; i<n1; ++i){
        printf("%pc \n",ptr+i);
    }

    printf("Please enter the new size (n2) value: ");
    scanf("%d", &n2);

    ptr = realloc(ptr,n2 * sizeof(int));

    printf("Addresses of previously newly allocated memory: \n ");
    for(int i=0; i<n2; ++i){
       printf("%pc \n",ptr+i);
    }

    free(ptr);
    return 0;
}
```

#### Output

```c
Please enter the size (n1) value: 2

Addresses of previously allocated memory:
01-) 0x55698ff6dac0c
02-) 0x55698ff6dac4c

Please enter the new size (n2) value: 4

Addresses of previously newly allocated memory:
01-) 0x55698ff6dac0c
02-) 0x55698ff6dac4c
03-) 0x55698ff6dac8c
04-) 0x55698ff6daccc

```
