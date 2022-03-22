# Examples

## Example 1 - İşaretçiler kullanarak bir dizinin öğelerine erişme

```c
#include <stdio.h>

int main() {
    int numbers[5];

    for(int i=0; i<5; ++i){
        printf("Please enter %d. value: ",i);
        scanf("%d", numbers + i);
    }

    for(int i=0; i<5; ++i){
        printf("%d. value => %d \n",i,*(numbers + i));
    }

    return 0;
}
```

### Output

```c
Please enter 0. value: 32
Please enter 1. value: 43
Please enter 2. value: 32
Please enter 3. value: 54
Please enter 4. value: 3
0. value => 32
1. value => 43
2. value => 32
3. value => 54
4. value => 3
```

------------
## Example 2 - Numaraları referansa göre aramayı kullanarak döngüsel sırayla değiştirin

```c
#include <stdio.h>

void changeRef(int* n1, int* n2, int* n3);

int main() {
    int x,y,z;
    printf("Please enter x value: ");
    scanf("%d",&x);

    printf("Please enter y value: ");
    scanf("%d", &y);

    printf("Please enter z value: ");
    scanf("%d", &z);

    printf("Before changing the numbers \n");
    printf("X => %d, Y => %d, Z => %d \n ",x,y,z);

    changeRef(&x,&y,&z);

    printf("After changing the numbers \n");
    printf("X => %d, Y => %d, Z => %d \n",x,y,z);

    return 0;
}

void changeRef(int* n1, int* n2, int* n3){
    int temp;
    temp = *n1;
    *n2 = *n1;
    *n1 = *n3;
    *n3 = temp;
}
```

### Output

```c
Please enter x value: 32
Please enter y value: 54
Please enter z value: 43
Before changing the numbers
X => 32, Y => 54, Z => 43
 After changing the numbers
X => 43, Y => 32, Z => 32
```

------------
## Example 3 - Find the largest number (Dynamic memory allocation is used)

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    double* dataPtr;

    printf("Please enter the n value: ");
    scanf("%d",&n);

    dataPtr = (double *)calloc(n,sizeof(double));

    if(dataPtr == NULL){
        printf("Error, memory not allocated!");
        exit(0);
    }

    for(int i=0; i<n; ++i){
        printf("Enter %d.value:",i);
        scanf("%lf",dataPtr+i);
    }

    for(int i=1; i<n; ++i){
        if (*dataPtr < *(dataPtr+i)){
            *dataPtr = *(dataPtr+i);
        }
    }

    printf("Largest number of array => %.2lf", *dataPtr);
    free(dataPtr);

    return 0;
}
```

### Output

```c
Please enter the n value: 3
Enter 0.value:32
Enter 1.value:43
Enter 2.value:54
Largest number of array => 54.00
```
