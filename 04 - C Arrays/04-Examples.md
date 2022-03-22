# Examples

## Example 1 - Dizi elemanlarının ortalamasını hesaplayın

```c
#include <stdio.h>

int main() {
    int numbers[5],total=0, average;

    for(int i=0; i<5; ++i){
        printf("Please enter the %d.value: ",i);
        scanf("%d", &numbers[i]);
        total += numbers[i];
    }

    average = total / 5;
    printf("Average => %d",average);

    return 0;
}
```

### Output

```c
Please enter the 0.value: 25
Please enter the 1.value: 32
Please enter the 2.value: 54
Please enter the 3.value: 32
Please enter the 4.value: 43
Average => 37
```

------------
## Example 2 - Bir dizinin en büyük öğesini bulun

```c
#include <stdio.h>

int main() {
    int numbers[5],largestNumber;

    for(int i=0; i<5; ++i){
        printf("Please enter the %d.value: ",i);
        scanf("%d", &numbers[i]);
    }

    largestNumber = numbers[0];
    for(int i=0; i<5; ++i){
        if(largestNumber < numbers[i]){
            largestNumber = numbers[i];
        }
    }

    printf("Largest number => %d",largestNumber);

    return 0;
}
```

### Output

```c
Please enter the 0.value: 150
Please enter the 1.value: 23
Please enter the 2.value: 543
Please enter the 3.value: 32
Please enter the 4.value: 1
Largest number => 543
```

------------
## Example 3 - İki diziyi çarpın ve toplayın

```c
#include <stdio.h>

int main() {
    int x[5],y[5],resultSum[5],resultMult[5];

    for(int i=0; i<5; ++i){
        printf("Please enter the %d.value of x array: ",i);
        scanf("%d", &x[i]);
    }

    for(int i=0; i<5; ++i){
        printf("Please enter the %d.value of y array: ",i);
        scanf("%d", &y[i]);
    }

    for(int i=0; i<5; ++i){
        resultSum[i] = x[i] + y[i];
        resultMult[i] = x[i] * y[i];
    }

     for(int i=0; i<5; ++i){
        printf("The %d.element of the result array of the addition operation: %d \n",i,resultSum[i]);
        printf("The %d.element of the result array of the addition operation: %d \n",i,resultMult[i]);
    }

    return 0;
}
```

### Output

```c
Please enter the 0.value of x array: 25
Please enter the 1.value of x array: 22
Please enter the 2.value of x array: 14
Please enter the 3.value of x array: 10
Please enter the 4.value of x array: 58
Please enter the 0.value of y array: 65
Please enter the 1.value of y array: 24
Please enter the 2.value of y array: 57
Please enter the 3.value of y array: 14
Please enter the 4.value of y array: 11
The 0.element of the result array of the addition operation: 90
The 0.element of the result array of the addition operation: 1625
The 1.element of the result array of the addition operation: 46
The 1.element of the result array of the addition operation: 528
The 2.element of the result array of the addition operation: 71
The 2.element of the result array of the addition operation: 798
The 3.element of the result array of the addition operation: 24
The 3.element of the result array of the addition operation: 140
The 4.element of the result array of the addition operation: 69
The 4.element of the result array of the addition operation: 638
```

------------
## Example 4 - Matriksi ters çevirin

```c
#include <stdio.h>

int main() {
    int numbers[10][10], transpose[10][10],c,r;

    printf("Please enter row value: ");
    scanf("%d",&r);

    printf("Please enter column value: ");
    scanf("%d",&c);


    for(int i=0; i<r; ++i){
        for(int j=0; j<c; ++j){
            printf("Please enter [%d][%d].value: ",i,j);
            scanf("%d",&numbers[i][j]);
        }
    }

    printf("Let's print the elements before transpod operation. \n");

    for(int i=0; i<2; ++i){
        for(int j=0; j<3; ++j){
            printf("[%d][%d].value of array: %d \n",i,j,numbers[i][j]);

            if(j == c-1){
                printf("\n");
            }
        }
    }

    for(int i=0; i<r; ++i){
        for(int j=0; j<c; ++j){
            transpose[j][i] = numbers[i][j];
        }
    }

    printf("Let's print the elements after transpod operation. \n");
    for(int i=0; i<c; ++i){
        for(int j=0; j<r; ++j){
            printf("[%d][%d].value of array: %d \n",i,j,transpose[i][j]);

            if(j == r-1){
                printf("\n");
            }
        }
    }

    return 0;
}
```

### Output

```c
Please enter row value: 2
Please enter column value: 3
Please enter [0][0].value: 23
Please enter [0][1].value: 32
Please enter [0][2].value: 43
Please enter [1][0].value: 54
Please enter [1][1].value: 32
Please enter [1][2].value: 54
Let's print the elements before transpod operation.
[0][0].value of array: 23
[0][1].value of array: 32
[0][2].value of array: 43

[1][0].value of array: 54
[1][1].value of array: 32
[1][2].value of array: 54

Let's print the elements after transpod operation.
[0][0].value of array: 23
[0][1].value of array: 54

[1][0].value of array: 32
[1][1].value of array: 32

[2][0].value of array: 43
[2][1].value of array: 54
```

