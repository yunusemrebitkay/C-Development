# Unions

- Yapılar, tüm üyelerini depolamak için yeterli alan ayırırken, birlikler bir seferde yalnızca bir üye değeri tutabilir .

------------
## Union nasıl tanımlanır?

```c
union truck{
    char name[50];
    int price;
};
```

------------
## Union değişkenleri nasıl oluşturulur?

- Birleşim tanımlandığında, kullanıcı tanımlı bir tür oluşturur. Ancak, bellek tahsis edilmez. Belirli bir birleşim türü için bellek ayırmak ve onunla çalışmak için değişkenler oluşturmamız gerekir.

```c
union truck{
    char name[50];
    int price;
};

int main(){
    union truck truck1,truck2,*truckPtr;
}
```

- Birleşim değişkenleri oluşturmanın başka bir yolu şudur:

```c
union truck{
    char name[50];
    int price;
}truck1,truck2,*truckPtr;

```

------------
## Bir union üyelerine erişim

- .(dot) operatörü bir union'un üyelerine erişmek için kullanırız.
- İşaretçi değişkenlere ulaşmak için -> operatörünü kullanırız.

------------
## Union ve Struct arasındaki farklar

```c
union unionStudent{
    char name[50];
    int id;
    float grade;
}unStudent;

struct structStudent{
    char name[50];
    int id;
    float grade;
}stStudent;

int main(){
    printf("Size of union => %d \n",sizeof(unStudent));
    printf("Size of struct => %d \n",sizeof(stStudent));
    return 0;
}
```

### Output

```c
Size of union => 52
Size of struct => 60

```

- name[52] = 52 byte / id = 4 byte / grade = 4 byte Total
- Unionda 52 çünkü her zaman en büyük öğesinin değerini alıp bellekte yer kaplar.
- Structa ise tamamının boyutunda bellekte yer kaplar.


------------
## Union öğelerine nasıl erişilir?

```c
#include <stdio.h>

union student{
    int id;
    float grade;
}st;

int main(){
    st.grade = 4;
    st.id = 15; // When we grade is assigned a value, grade will no longer hold 4

    printf("Student's id => %d \n",st.id);
    printf("Student's grade => %.2f \n",st.grade);
    return 0;
}
```

### Output

```c
Student's id => 15
Student's grade => 0.00
```
