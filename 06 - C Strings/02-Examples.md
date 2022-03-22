# Examples

## Example 1 - Bir stringdeki bir karakterin sıklığını bulun

```c
#include <stdio.h>

int main() {
    char str[1000],ch;
    int count = 0;

    printf("Please enter the string: ");
    fgets(str,sizeof(str),stdin);

    printf("Please enter the character you want to find: ");
    scanf("%c",&ch);

    for(int i=0; str[i] != '\0'; ++i){
        if(ch == str[i]){
            ++count;
        }
    }

    printf("Frequency of %c => %d",ch,count);

    return 0;
}
```

### Output

```c
Please enter the string: hello my friend
Please enter the character you want to find: e
Frequency of e => 2
```

------------
## Example 2 - Ünlülerin, ünsüzlerin, rakamların ve beyaz boşlukların sayısını bulun

```c
#include <stdio.h>

int main() {
    char str[1000];
    int digitCount=0, vowelsCount=0, constantCount=0;

    printf("Please enter the string: ");
    fgets(str,sizeof(str),stdin);

    for(int i=0; str[i] != '\n'; ++i){
        str[i] = tolower(str[i]);

        if(str[i] == 'a' || str[i] == 'e' || str[i] == 'i' || 
        str[i] == 'o'|| str[i] == 'u'){
            ++vowelsCount;
        }
        else if (isalpha(str[i])){
            ++constantCount;
        }
        else if (isdigit(str[i])){
            ++digitCount;
        }
    }

    printf("Count of vowels in the string you entered: => %d \n",vowelsCount);
    printf("Count of constants in the string you entered: => %d \n",constantCount);
    printf("Count of numbers in the string you entered: => %d \n",digitCount);

    return 0;
}
```

### Output

```c
Please enter the string: alfa emre
Count of vowels in the string you entered: => 4
Count of constants in the string you entered: => 4
Count of numbers in the string you entered: => 0
```

------------
## Example 3 - Özyinelemeyi kullanarak bir stringi tersine çevirme

```c
#include <stdio.h>

void recursion();

int main() {
    printf("Please enter the string: ");
    recursion();
    return 0;
}

void recursion(){
    char c;
    scanf("%c",&c);
    if(c != '\n'){
        recursion();
        printf("%c \n",c);
    }
}
```

### Output

```c
Please enter the string: emre alfa
a
f
l
a

e
r
m
e
```

------------
## Example 4 - Bir stringin uzunluğunu bulun

```c
#include <stdio.h>

int main() {
    char text[30];

    printf("Please enter the string: ");
    scanf("%c",&text);

    printf("Length of the string you entered: %d", strlen(text));
    return 0;
}
```

### Output

```c
Please enter the string: selamlar
Length of the string you entered: 6
```

------------
## Example 5 - İki stringi birleştirin

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

------------
## Example 6 - Bir stringi kopyalayın

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
## Example 7 - Harfler hariç bir stringdeki tüm karakterleri kaldırın

```c
#include <stdio.h>

int main() {
    char text[30],newText[30];

    printf("Please enter the string: ");
    fgets(text,sizeof(text),stdin);

    for(int i=0; i<strlen(text); ++i){
        if (isalpha(text[i])){
            newText[i] = text[i];
        }
    }

    printf("Cleaned string: %s",newText);
    return 0;
}
```

### Output

```c
Please enter the string: selam a231 eads
Cleaned string: selama
```
