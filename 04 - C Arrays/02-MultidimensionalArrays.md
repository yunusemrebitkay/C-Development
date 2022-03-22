# Multidimensional Arrays
- C programlamada çok boyutlu dizi oluşturabilirsiniz.

```c
float array[3][4];
```

- Burada,x iki boyutlu (2d) bir dizidir. Dizi 12 eleman tutabilir. Diziyi 3 satırlı ve her satırda 4 sütunlu bir tablo olarak düşünebilirsiniz.

|   | Column 1  | Column 2  |  Column 3 | Column 4  |
| :------------: | :------------: | :------------: | :------------: | :------------: |
|  Row 1 |  x[0][0] |  x[0][1]  |  x[0][2]  |  x[0][3]  |
|  Row 2 |  x[1][0] |  x[1][1]  |  x[1][2]  |  x[1][3]  |
|  Row 3 |  x[2][0] |  x[2][1]  |  x[2][2]  |  x[2][3]  |


- Benzer şekilde, üç boyutlu (3d) bir dizi bildirebilirsiniz. Örneğin,

```c
int 3d[2][3][4];

```

------------
## Çok boyutlu bir diziyi başlatma
- İki boyutlu ve üç boyutlu dizileri şu şekilde başlatabilirsiniz:

### 2 boyutlu bir dizinin başlatılması

```c
#include <stdio.h>

int main() {
    int x[2][3] = {{1,2,3},{4,5,6}};
    int y[][3] = {{1,2,3},{4,5,6}};
    int z[2][3] = {1,2,3,4,5,6};

    return 0;
}
```

### 3 boyutlu bir dizinin başlatılması

```c
#include <stdio.h>

int main() {
    int x[2][3][4] = {{
        {1,2,3,4},{5,6,7,8},{9,10,11,12},{13,14,15,16},
        {17,18,19,20},{21,22,23,24},{25,26,27,28}}};

    return 0;
}
```

------------
### Example 1 - İki boyutlu dizinin değerlerini saklayıp yazdırın

```c
#include <stdio.h>

const int city = 3;
const int week = 5;

int main() {
    int temp[city][week];

    for(int i=0; i<city; ++i){
        for(int j=0; j<week; ++j){
            printf("City %d and week %d: ",i+1,j+1);
            scanf("%d",&temp[i][j]);
        }
    }

    for(int i=0; i<city; ++i){
        for(int j=0; j<week; ++j){
            printf("City %d and week %d = %d\n ",i+1,j+1,temp[i][j]);
        }
    }

    return 0;
}
```

#### Output

```c
City 1 and week 1: 25
City 1 and week 2: 32
City 1 and week 3: 54
City 1 and week 4: 32
City 1 and week 5: 43
City 2 and week 1: 32
City 2 and week 2: 4
City 2 and week 3: 32
City 2 and week 4: 54
City 2 and week 5: 43
City 3 and week 1: 12
City 3 and week 2: 3
City 3 and week 3: 5
City 3 and week 4: 4
City 3 and week 5: 2
City 1 and week 1 = 25
 City 1 and week 2 = 32
 City 1 and week 3 = 54
 City 1 and week 4 = 32
 City 1 and week 5 = 43
 City 2 and week 1 = 32
 City 2 and week 2 = 4
 City 2 and week 3 = 32
 City 2 and week 4 = 54
 City 2 and week 5 = 43
 City 3 and week 1 = 12
 City 3 and week 2 = 3
 City 3 and week 3 = 5
 City 3 and week 4 = 4
 City 3 and week 5 = 2
```

------------
### Example 2 - İki matriksi toplayın

```c
#include <stdio.h>

const int city = 3;
const int week = 5;

int main() {
    int x[2][2], y[2][2], result[2][2];

    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
            printf("Enter [%d][%d] value of x array: ",i,j);
            scanf("%d",&x[i][j]);
        }
    }

    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
            printf("Enter [%d][%d] value of y array: ",i,j);
            scanf("%d",&y[i][j]);
        }
    }

    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
            result[i][j] = x[i][j] + y[i][j];
        }
    }

    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
            printf("[%d][%d] = %d \n", i,j,result[i][j]);
        }
    }

    return 0;
}
```

#### Output

```c
Enter [0][0] value of x array: 15
Enter [0][1] value of x array: 25
Enter [1][0] value of x array: 20
Enter [1][1] value of x array: 3
Enter [0][0] value of y array: 4
Enter [0][1] value of y array: 532
Enter [1][0] value of y array: 43
Enter [1][1] value of y array: 43
[0][0] = 19
[0][1] = 557
[1][0] = 63
[1][1] = 46
```

------------
### Example 3 - Three-dimensional array

```c
#include <stdio.h>

int main() {
    int x[2][2][2];

    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
            for(int k=0; k<2; ++k){
                printf("Enter [%d][%d][%d] value of x array: ",i,j,k);
                scanf("%d",&x[i][j][k]);
            }
        }
    }
    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
            for(int k=0; k<2; ++k){
                printf("[%d][%d][%d] = %d \n",i,j,k,x[i][j][k]);
            }
        }
    }
    return 0;
}
```

#### Output

```c
Enter [0][0][0] value of x array: 15
Enter [0][0][1] value of x array: 20
Enter [0][1][0] value of x array: 25
Enter [0][1][1] value of x array: 30
Enter [1][0][0] value of x array: 35
Enter [1][0][1] value of x array: 40
Enter [1][1][0] value of x array: 45
Enter [1][1][1] value of x array: 50
[0][0][0] = 15
[0][0][1] = 20
[0][1][0] = 25
[0][1][1] = 30
[1][0][0] = 35
[1][0][1] = 40
[1][1][0] = 45
[1][1][1] = 50
```
