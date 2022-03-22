# Structure

- C programlamada, bir yapı (veya yapı), tek bir ad altında bir değişkenler topluluğudur (farklı türlerde olabilir).

------------
## Structure sözdizimi

```c
struct structureName {
  dataType member1;
  dataType member2;
  ...
};
```

------------
### Example

```c
struct student{
    char studentName[50];
    int studentID;
    float studentGradeAv;
};
```

------------
## Yapı Değişkenleri oluştur

- Bir struct tür bildirildiğinde, depolama veya bellek tahsis edilmez. Belirli bir yapı tipinin hafızasını tahsis etmek ve onunla çalışmak için değişkenler yaratmamız gerekir.

```c
#include <stdio.h>

struct student{
    // code
};

int main() {
    struct student student1,student2,name[30];
    return 0;
}
```

- Struct Değişken oluşturmanın başka bir yolu şudur:

```c
struct student{
    // code
},student1,student2,name[30];
```

------------
## Bir Yapının Üyelerine Erişim

- Bir yapının üyelerine erişmek için kullanılan iki tür operatör vardır.
- Operator 1 .(dot) - Üye Operatörü
- Operator 2 -> - Yapı İşaretçisi Operatörü

------------
### Example 1 - C++ Structs

```c
#include <stdio.h>
#include <string.h>

struct student{
    char studentName[50];
    int studentID;
    float studentGradeAv;
}student1; // We create a struct with student1 variable

int main() {
    strcpy(student1.studentName, "Yunus Emre Bitkay");

    student1.studentID = 02;
    student1.studentGradeAv = 4.0;

    printf("Student name: %s \n",student1.studentName);
    printf("Student ID: %d \n",student1.studentID);
    printf("Student grade average: %f \n",student1.studentGradeAv);
    return 0;
}
```

#### Output

```c
Student name: Yunus Emre Bitkay
Student ID: 2
Student grade average: 4.000000
```

------------
## Keyword typedef

- Typedef veri türleri için bir takma ad oluşturmak için anahtar kelimeyi kullanırız . Değişkenleri bildirme sözdizimini basitleştirmek için yapılarla yaygın olarak kullanılır.

- Örneğin, aşağıdaki koda bakalım:

```c
struct student{
    char studentName[50];
    int studentID;
    float studentGradeAv;
};

int main(){
    struct student d1,d2;
}
```

- Typedef basitleştirilmiş bir sözdizimi ile eşdeğer bir kod yazmak için kullanabiliriz :

```c
#include <stdio.h>

typedef struct student{
    char studentName[50];
    int studentID;
    float studentGradeAv;
}students;

int main() {
    struct students d1,d2;
    return 0;
}
```

------------
### Example 2 - C++ Typedef

```c
#include <stdio.h>
#include <string.h>

typedef struct student{
    char studentName[50];
    int studentID;
    float studentGradeAv;
}students;

int main() {
    students s1;

    strcpy(s1.studentName,"Emre Bitkay");
    s1.studentID = 05;
    s1.studentGradeAv = 4;

    printf("Student name: %s \n",s1.studentName);
    printf("Student ID: %d \n",s1.studentID);
    printf("Student grade average: %.2f \n",s1.studentGradeAv);
    return 0;
}
```

### Output

```c
Student name: Emre Bitkay
Student ID: 5
Student grade average: 4.00

```

------------
## Nested Structures

- C programlamada bir yapı içinde yapılar oluşturabilirsiniz. Örneğin,

```c
struct complex{
    int imag;
    float real;
};

struct number{
    struct complex comp;
    int integers;
}num1,num2;

```

- Şu şekilde nesne oluşturabiliriz

```c
num2.comp.imag = 25;
```

------------
### Example 3 - Nested Structures

```c
#include <stdio.h>

struct complex{
    int imag;
    float real;
};

struct number{
    struct complex comp;
    int integers;
}num1,num2;

int main(){

    num1.comp.imag = 14;
    num1.comp.real = 5.2;
    num1.integers = 16;

    printf("Imag of num1 => %d \n",num1.comp.imag);
    printf("Real of num1 => %f \n",num1.comp.real);
    printf("Integer of num1 => %d \n",num1.integers);
    return 0;
}
```

#### Output

```c
Imag of num1 => 14
Real of num1 => 5.200000
Integer of num1 => 16
```

