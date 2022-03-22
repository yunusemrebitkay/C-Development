# Relation Ship Between Functions And Pointers
- C programlamada, adresleri işlevlere argüman olarak iletmek de mümkündür.
- Bu adresleri fonksiyon tanımında kabul etmek için işaretçiler kullanabiliriz. Bunun nedeni, işaretçilerin adresleri depolamak için kullanılmasıdır.

------------
## Example 1 - Pass Addresses to Functions

```c
#include <stdio.h>

void swapNumbers(int *num1,int *num2);

int main() {
    int num1 = 12, num2 = 235;

    int* ptr;

    swapNumbers(&num1,&num2);

    printf("Number 1 => %d \n",num1);
    printf("Number 2 => %d \n",num2);

    return 0;
}

void swapNumbers(int* num1,int* num2){
    int temp;
    temp = *num1;
    *num1 = *num2;
    *num2 = temp;
}
```

### Output

```c
Number 1 => 235
Number 2 => 12
```

------------
## Example 2 - Passing Pointers to Functions

```c
#include <stdio.h>

void addOne(int* ptr);

int main() {
    int* p, i =15;
    p = &i;
    addOne(p);

    printf("%d",*p);

    return 0;
}

void addOne(int* ptr){
   (*ptr)++; // adding 1 to *ptr
}
```

### Output

```c
16
```