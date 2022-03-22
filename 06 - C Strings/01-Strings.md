# Strings

- C programlamada string, boş karakterle sonlandırılan bir karakter dizisidir.

```c
char c[] = "Hello World";
```

------------

## String dizileri nasıl başlatılır?

```c
char c[] = "alfa";
char c[50] = "alfa";
char c[] = {'a','l','f','a','\0'};
char c[5] = {'a','l','f','a','\0'};
```

------------

## Stringlere değer nasıl atanır?

```c
char c[100];
c = "Hello world!";
```

------------

## Kullanıcıdan string input nasıl alınır?

```c
#include <stdio.h>

int main() {

    char c[10];

    printf("Please enter string value: ");
    scanf("%s",&c);

    printf("The string value => %s",c);
    return 0;
}
```

### Output

```c
Please enter string value: Hello
```

------------

## Bir metin satırı nasıl okunur?

- Fgets() ile.bir string satırını okuyabiliriz.
- Puts() ile bir stringi görüntüleyebiliriz.

```c
#include <stdio.h>

int main() {
    char name[100];

    printf("Please enter the name: ");
    fgets(name,sizeof(name),stdin); // Similiar to scanf

    printf("The name => %s",name);
    puts(name);

    return 0;
}
```

### Output

```c
Please enter the name: emre
The name => emre
emre
```

------------

## Stringlerden fonksiyonlara nasıl geçilir?

```c
#include <stdio.h>
void displayString(char str[]);

int main() {
    char name[100];

    printf("Please enter the name: ");
    fgets(name,sizeof(name),stdin); // Similiar to scanf

    displayString(name);

    return 0;
}

void displayString(char str[]){
    puts(str);
}
```

### Output

```c
Please enter the name: emre
emre
```

------------
## Stringler ve Pointerlar

- Dizilere benzer şekilde, dize adları işaretçilere "çürür". Bu nedenle, dizenin öğelerini değiştirmek için işaretçiler kullanabilirsiniz.

```c
#include <stdio.h>

int main() {
    char name[] = "Lucifer Morningstar";

    printf("%c \n",*name); // Output L
    printf("%c \n",*(name+1)); // Output U
    printf("%c \n",*(name+5)); // Output E

    char *namePtr;
    namePtr = name;

    printf("%c \n",*namePtr); // Output L
    printf("%c \n",*(namePtr+1)); // Output U
    printf("%c \n",*(namePtr+5)); // Output E

    return 0;
}
```

### Output

```c
L
u
e
L
u
e
```

------------

## Strlen()

- Bir stringin uzunluğunu hesaplar

```c
#include <stdio.h>

int main() {
    char name[] = "Lucifer Morningstar";

    int stringLen = strlen(name);
    printf("Length of name string => %d",stringLen);

    return 0;
}
```

### Output

```c
Length of name string => 19
```

------------

## Strcpy()

- Bir stringi diğerine kopyalar

```c
#include <stdio.h>
#include <string.h>

int main() {
    char name[] = "Lucifer Morningstar";
    char copyName[100];

    strcpy(copyName,name);
    printf("Copied string: => %s",copyName);

    return 0;
}
```

### Output

```c
Copied string: => Lucifer Morningstar
```

------------

## Strcmp()

- İki stringi karşılaştırır

| Return Value |                                  Remarks                                  |
| :----------: | :-----------------------------------------------------------------------: |
|      0       |                           if strings are equal                            |
|      >0      | if the first non-matching char in str1 is greater (in ASCII) than of str2 |
|      <0      |  if the first non-matching char in str1 is lower (in ASCII) than of str2  |

```c
#include <stdio.h>
#include <string.h>

int main() {
    char strFirst[] = "emre";
    char strSecond[] = "emRe";
    char strThird[] = "emre";
    int result;

    result = strcmp(strFirst,strSecond);
    printf("strcmp(strFirst,strSecond) => %d \n",result);

    result = strcmp(strFirst,strThird);
    printf("strcmp(strFirst,strThird) => %d \n",result);

    return 0;
}
```

### Output

```c
strcmp(strFirst,strSecond) => 32 
strcmp(strFirst,strThird) => 0
```

------------

## Strcat()

- İki stringi birleştirir

```c
#include <stdio.h>
#include <string.h>

int main() {
    char firstName[100] = "Lucifer ";
    char lastName[] = "Morningstar";

    strcat(firstName,lastName);

    puts(firstName);
    puts(lastName);

    return 0;
}
```

### Output

```c
Lucifer Morningstar
Morningstar
```
