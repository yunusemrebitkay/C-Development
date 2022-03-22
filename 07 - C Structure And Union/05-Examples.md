# Examples

------------
## Example 1 - Struct kullanan bir öğrencinin bilgilerini saklayın

```c
#include <stdio.h>

struct student{
    char name[50];
    int id;
    float grade;
};

int main(){
    struct student s1;

    printf("Please enter the student's name: ");
    scanf("%s",&s1.name);

    printf("Please enter the student's id: ");
    scanf("%d",&s1.id);

    printf("Please enter the student's grade: ");
    scanf("%f",&s1.grade);

    printf("Display informations: \n");
    printf("Student's name => %s \n",s1.name);
    printf("Student's id => %d \n",s1.id);
    printf("Student's grade => %f \n",s1.grade);

    return 0;
}
```

### Output

```c
Please enter the student's name: emre
Please enter the student's id: 2
Please enter the student's grade: 4
Display informations:
Student's name => emre
Student's id => 2
Student's grade => 4.00
```

------------
## Example 2 - İki mesafe ekleyin (inç-feet cinsinden)

```c
#include <stdio.h>

struct Distance{
    int feet;
    float inch;
};

int main(){
    struct Distance d1,d2,result;

    printf("Please enter first distance: \n");
    printf("Please enter first distance's feet: ");
    scanf("%d",&d1.feet);

    printf("Please enter first distance's inch: ");
    scanf("%f",&d1.inch);

    printf("Please enter second distance: \n");
    printf("Please enter second distance's feet: ");
    scanf("%d",&d2.feet);

    printf("Please enter second distance's inch: ");
    scanf("%f",&d2.inch);

    result.feet = d1.feet + d2.feet;
    result.inch = d1.inch + d2.inch;

    while(result.inch>12.0){
        result.inch = result.inch - 12.0;
        ++result.feet;
    }

    printf("Sum of distances => %d\' -%1.f\"",result.feet,result.inch);

    return 0;
}
```

### Output

```c
Please enter first distance:
Please enter first distance's feet: 2
Please enter first distance's inch: 3
Please enter second distance:
Please enter second distance's feet: 4
Please enter second distance's inch: 5
Sum of distances => 6' -8"
```

------------
## Example 3 - Struct ile iki karmaşık sayı ekleyin

```c
#include <stdio.h>

typedef struct complex{
    float real;
    float imag;
} complex;

complex add(complex c1,complex c2);

int main(){
    struct complex c1,c2,result;

    printf("Please enter first complex: \n");
    printf("Please enter first complex's real: ");
    scanf("%f",&c1.real);

    printf("Please enter first complex's imag: ");
    scanf("%f",&c1.imag);

    printf("Please enter second complex: \n");
    printf("Please enter second complex's real: ");
    scanf("%f",&c2.real);

    printf("Please enter second complex's imag: ");
    scanf("%f",&c2.imag);

    result = add(c1,c2);
    printf("Sum of complex => real: %1.f imag: %1.fi",result.real,result.imag);

    return 0;
}

complex add(complex c1,complex c2){
    complex temp;
    temp.real = c1.real + c2.real;
    temp.imag = c1.imag + c2.imag;

    return(temp);
}
```

### Output

```c
Please enter first complex:
Please enter first complex's real: 2
Please enter first complex's imag: 3
Please enter second complex:
Please enter second complex's real: 4
Please enter second complex's imag: 2
Sum of complex => real: 6 imag: 5i
```

------------
## Example 4 - İki zaman dilimi arasındaki farkı hesaplayın

```c
#include <stdio.h>

struct time{
    int seconds;
    int minutes;
    int hours;
};

void calculateTime(struct time s1,struct time s2, struct time *diff);

int main(){

    struct time startTime, stopTime,diff;

    printf("Please enter first time: \n");
    printf("Please enter first time's seconds: ");
    scanf("%d",&startTime.seconds);

    printf("Please enter first time's minutes: ");
    scanf("%d",&startTime.minutes);

    printf("Please enter first time's hours: ");
    scanf("%d",&startTime.hours);

    printf("Please enter second time: \n");
    printf("Please enter second time's seconds: ");
    scanf("%d",&stopTime.seconds);

    printf("Please enter second time's minutes: ");
    scanf("%d",&stopTime.minutes);

    printf("Please enter second time's hours: ");
    scanf("%d",&stopTime.hours);

    calculateTime(startTime,stopTime,&diff);

    printf("Start time => %d:%d:%d \n",startTime.hours,startTime.minutes,startTime.seconds);
    printf("Stop time => %d:%d:%d \n",stopTime.hours,stopTime.minutes,stopTime.seconds);
    printf("Difference time => %d:%d:%d \n",diff.hours,diff.minutes,diff.seconds);
    return 0;
}

void calculateTime(struct time start,struct time finish, struct time *diff){
    while(finish.seconds > start.seconds){
        --start.minutes;
        start.seconds += 60;
    }

    diff -> seconds = start.seconds - finish.seconds;

    while(finish.minutes > start.minutes){
        --start.hours;
        start.minutes += 60;
    }
    diff -> minutes = start.minutes - finish.minutes;
    diff -> hours = start.hours - finish.hours;
}
```

### Output

```c
Please enter first time:
Please enter first time's seconds: 25
Please enter first time's minutes: 30
Please enter first time's hours: 50
Please enter second time:
Please enter second time's seconds: 23
Please enter second time's minutes: 54
Please enter second time's hours: 32
Start time => 50:30:25
Stop time => 32:54:23
Difference time => 17:36:2
```

------------
## Example 5 - Structları kullanan 10 öğrencinin bilgilerini saklayın

```c
#include <stdio.h>

struct student{
    char name[50];
    int id;
    float grade;
}s[10];

int main(){
    struct student s1;

    for(int i=0; i<10; ++i){
        printf("Please enter the %d.student's name: ",i);
        scanf("%s",&s[i].name);

        printf("Please enter the %d.student's id: ",i);
        scanf("%d",&s[i].id);

        printf("Please enter the %d.student's grade: ",i);
        scanf("%f",&s[i].grade);
    }

    printf("Display informations: \n");
    for(int i=0; i<10; ++i){
        printf("%d.Student's name => %s \n",s[i].name);
        printf("%d.Student's id => %d \n",s[i].id);
        printf("%d.Student's grade => %f \n",s[i].grade);
    }

    return 0;
}
```

### Output

```c
Please enter the 0.student's name: ali
Please enter the 0.student's id: 5
Please enter the 0.student's grade: 3
Please enter the 1.student's name: emre
Please enter the 1.student's id: 2
Please enter the 1.student's grade: 4
Please enter the 2.student's name: mehmet
Please enter the 2.student's id: 6
Please enter the 2.student's grade: 3
Please enter the 3.student's name:
.
.
.
```

