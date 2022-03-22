# Array And Function
- Dizi öğelerini bir işleve geçirmek, bir işleve değişkenleri aktarmakla benzerdir .

------------
## Example 1: Pass Individual Array Elements
- Dizinin bir elemanını bir işleve geçirmek için, argüman olarak elemanın dizi indexi iletilir.

```c
#include <stdio.h>

void display(int firstAge,int secondAge);

int main() {
    int ageArray[] = {2,4,8,12};
    display(ageArray[0],ageArray[1]);
    return 0;
}

void display(int firstAge,int secondAge){
    printf("First age = %d \n",firstAge);
    printf("Second age = %d \n",secondAge);
}
```

### Output

```c
First age = 2
Second age = 4
```

------------
## Example 2: Pass Arrays to Functions
- Dizinin tamamını bir işleve geçirmek için, argüman olarak yalnızca dizinin adı iletilir.

```c
#include <stdio.h>

int calculateSum(int array[]);

int main() {
    int ageArray[] = {2,4,8,12,16,23},result;
    result = calculateSum(ageArray);

    printf("Result = %d",result);
    return 0;
}

int calculateSum(int array[]){
    int sum = 0;

    for(int i=0; i<6; ++i){
        sum += array[i];
    }

    return sum;
}
```

### Output

```c
Result = 65
```

------------
## Example 3: Pass two-dimensional arrays
- Çok boyutlu dizileri bir işleve geçirmek için, işleve yalnızca dizinin adı iletilir (tek boyutlu dizilere benzer şekilde).

```c
#include <stdio.h>

void display(int array[2][2]);

int main() {
    int ageArray[2][2] = {{2,6},{45,23}},result;
    display(ageArray);

    return 0;
}

void display(int array[2][2]){
    for(int i=0; i<2; ++i){
        for(int j=0; j<2; ++j){
                printf("[%d][%d] = %d \n",i,j,array[i][j]);
        }
    }
}
```

### Output

```c
[0][0] = 2
[0][1] = 6
[1][0] = 45
[1][1] = 23
```

- **Not:** C programlamada dizileri işlevlere geçirebilirsiniz, ancak işlevlerden dizileri döndüremezsiniz.
