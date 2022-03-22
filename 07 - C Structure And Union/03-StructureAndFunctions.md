# Structure and Function

- Yerleşik türlerin değişkenlerine benzer şekilde, yapı değişkenlerini bir işleve de iletebilirsiniz.

------------
## Fonksiyonlara yapıları geçirme

- Yapıları bir işleve şu şekilde geçirebilirsiniz

```c
#include <stdio.h>

struct student{
    char name[50];
    int id;
    float grade;
};

void display(struct student s);

int main(){
    struct student s1;

    printf("Enter the student's name: ");
    scanf("%s",&s1.name);

    printf("Enter the student's id: ");
    scanf("%d",&s1.id);

    printf("Enter the student's grade: ");
    scanf("%f",&s1.grade);

    display(s1);
    return 0;
}

void display(struct student s){
    printf("Student's name => %s \n",s.name);
    printf("Student's id => %d \n", s.id);
    printf("Student's grade => %f \n", s.grade);
}
```

### Output

```c
Enter the student's name: emre
Enter the student's id: 2
Enter the student's grade: 4
Student's name => emre
Student's id => 2
Student's grade => 4.000000
```

------------
## Bir işlevden yapıyı döndür

- Bir işlevden yapıyı şu şekilde döndürebilirsiniz:

```c
#include <stdio.h>

struct student{
    char name[50];
    int id;
    float grade;
};

struct student getInformation();

int main(){
    struct student s;

    s = getInformation();
    printf("Student's name => %s \n",s.name);
    printf("Student's id => %d \n", s.id);
    printf("Student's grade => %f \n", s.grade);
    return 0;
}

struct student getInformation(){
    struct student s1;

    printf("Enter the student's name: ");
    scanf("%s",&s1.name);

    printf("Enter the student's id: ");
    scanf("%d",&s1.id);

    printf("Enter the student's grade: ");
    scanf("%f",&s1.grade);

    return s1;
}
```

### Output

```c
Enter the student's name: Emre
Enter the student's id: 2
Enter the student's grade: 3
Student's name => Emre
Student's id => 2
Student's grade => 3.000000
```

------------
## Referansa göre yapı geçme

- Yapıları referansa göre de iletebilirsiniz

```c
#include <stdio.h>

typedef struct Complex{
    float real;
    float imag;
}complex;

void addNumbers(complex c1,complex c2,complex *result);

int main(){
    complex c1,c2,result;

    printf("Please enter for first number: \n");
    printf("Enter the first number's real value: ");
    scanf("%f",&c1.real);
    printf("Enter the first number's imag value: ");
    scanf("%f",&c1.imag);

    printf("Please enter for second number: \n");
    printf("Enter the second number's real value: ");
    scanf("%f",&c2.real);
    printf("Enter the second number's imag value: ");
    scanf("%f",&c2.imag);

    addNumbers(c1,c2,&result);

    printf("Result.real => %.2f \n",result.real);
    printf("Result.imag => %.2f \n",result.imag);

    return 0;
}

void addNumbers(complex c1,complex c2,complex *resultPtr){
    resultPtr->real = c1.real + c2.real;
    resultPtr->imag = c1.imag + c2.imag;
}
```

### Output

```c
Please enter for first number:
Enter the first number's real value: 25
Enter the first number's imag value: 32
Please enter for second number:
Enter the second number's real value: 53
Enter the second number's imag value: 23
Result.real => 78.00
Result.imag => 55.00
```