# Relation Ship Between Arrays And Pointers

- Bir dizi, sıralı bir veri bloğudur. Dizi elemanlarının adreslerini yazdıran bir program yazalım.

```c
#include <stdio.h>

int main() {

    int x[5];

    for(int i=0; i<4; ++i){
        printf("&x [%d] = %p \n",i,&x[i]);
    }

    printf("Address of array => %p", x);
    return 0;
}
```

### Output

```c
&x [0] = 0x7ffcc34ace80
&x [1] = 0x7ffcc34ace84
&x [2] = 0x7ffcc34ace88
&x [3] = 0x7ffcc34ace8c
Address of array => 0x7ffcc34ace80
```

- Dikkat edin, adresi &x[0] ve x aynı. Çünkü *x dizinin ilk elemanına işaret eder.
- &x[1] = x + 1 <=> x[1] = *(x+1)
- &x[2] = x + 2 <=> x[2] = *(x+2)
- Temel olarak &x[i] = x + i <=> x[i] = *(x+i)

------------
## Example 1: Pointers and Arrays

```c
#include <stdio.h>

int main() {

    int x[5],total = 0;

    for(int i=0; i<4; ++i){
        printf("Please enter %d. value: ",i);

        // Equal to scanf("%d", &x[i]);
        scanf("%d", x +i );

        total += *(x+i);
    }

    printf("Sum of array => %d", total);

    return 0;
}
```

### Output

```c
Please enter 0. value: 25
Please enter 1. value: 43
Please enter 2. value: 32
Please enter 3. value: 54
Sum of array => 154
```

- Çoğu bağlamda, dizi adları işaretçilere dönüşür. Basit bir deyişle, dizi adları işaretçilere dönüştürülür. Dizilerin öğelerine erişmek için işaretçileri kullanabilmenizin nedeni budur. Ancak, işaretçilerin ve dizilerin aynı olmadığını unutmamalısınız .


------------
## Example 2: Arrays and Pointers

```c
#include <stdio.h>

int main() {

    int x[5] = {2,3,4,6,7};
    int* ptr;

    ptr = &x[2]; // The address of the third element of the array is assigned

    printf("*ptr => %d \n", *ptr);
    printf("*(ptr+1 => %d \n", *(ptr+1));
    printf("*(ptr-1) => %d \n", *(ptr-1));

    return 0;
}
```
### Output

```c
*ptr => 4
*(ptr+1 => 6
*(ptr-1) => 3
```

