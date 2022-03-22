# Structs and Pointers

## Pointers to struct

- Yapılara işaretçileri şu şekilde oluşturabiliriz

```c
struct structName{
    member1,
    member2,
    .
    .
    .
};

int main(){
    struct structName *ptr, Emre;
}
```

------------
## Example 1 - Access members using Pointer

- İşaretçiler kullanarak bir yapının üyelerine erişmek için -> operatörü kullanırız.

```c
#include <stdio.h>

struct student{
    char name[50];
    int id;
    float grade;
};

int main(){
    struct student *studentPtr, student1;
    studentPtr =  &student1;

    printf("Enter the student's name: ");
    scanf("%s",&studentPtr -> name);

    printf("Enter the student's id: ");
    scanf("%d",&studentPtr -> id);

    printf("Enter the student's grade: ");
    scanf("%f",&studentPtr -> grade);

    printf("Display student information: \n");
    printf("Student's name => %s \n", studentPtr -> name);
    printf("Student's id => %d \n", studentPtr -> id);
    printf("Student's grade => %f \n", studentPtr -> grade);
    return 0;
}
```

### Output

```c
Enter the student's name: Emre
Enter the student's id: 5
Enter the student's grade: 4

Display student information:
Student's name => Emre
Student's id => 5
Student's grade => 4.000000

```

------------
## Dynamic memory allocation of structs

- Bazen, bildirdiğiniz yapı değişkenlerinin sayısı yetersiz olabilir. Çalışma zamanı sırasında bellek ayırmanız gerekebilir.

```c
#include <stdio.h>
#include <stdlib.h>

struct student{
    char name[50];
    int id;
    float grade;
};

int main(){
    struct student *studentPtr;
    int n;

    printf("Please enter number of student: ");
    scanf("%d",&n);

    studentPtr = (struct student *) malloc(n*sizeof(struct student));

    for(int i=0; i<n; ++i){
        printf("Enter the student's name: ");
        scanf("%s",&(studentPtr+i) -> name);

        printf("Enter the student's id: ");
        scanf("%d",&(studentPtr+i) -> id);

        printf("Enter the student's grade: ");
        scanf("%f",&(studentPtr+i) -> grade);
    }

    printf("Display student information: \n");
    for(int i=0; i<n; ++i){
        printf("Student's name => %s \n", (studentPtr+i) -> name);
        printf("Student's id => %d \n", (studentPtr+i) -> id);
        printf("Student's grade => %f \n", (studentPtr+i) -> grade);
        printf("\n");
    }

    return 0;
}
```

### Output

```c
Please enter number of student: 2
Enter the student's name: ali
Enter the student's id: 03
Enter the student's grade: 3
Enter the student's name: emre
Enter the student's id: 1
Enter the student's grade: 4
Display student information:
Student's name => ali
Student's id => 3
Student's grade => 3.000000

Student's name => emre
Student's id => 1
Student's grade => 4.000000
```
