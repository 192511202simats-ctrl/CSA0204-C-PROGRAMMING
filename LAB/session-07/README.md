**31. Find String Length Without Built-in Function**

**C Program:**

```c
#include <stdio.h>

int main()
{
    char str[100];
    int i = 0;

    printf("Enter a string: ");
    scanf(" %[^\n]", str);

    while(str[i] != '\0')
        i++;

    printf("Number of characters = %d", i);

    return 0;
}
```

**Sample Output:**

```text
Enter a string: Hello World
Number of characters = 11
```
**32. Arrange Names in Alphabetical Order**

**C Program:**

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char name[10][50], temp[50];
    int n, i, j;

    printf("Enter number of names: ");
    scanf("%d", &n);

    printf("Enter names:\n");

    for(i = 0; i < n; i++)
        scanf("%s", name[i]);

    for(i = 0; i < n - 1; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if(strcmp(name[i], name[j]) > 0)
            {
                strcpy(temp, name[i]);
                strcpy(name[i], name[j]);
                strcpy(name[j], temp);
            }
        }
    }

    printf("Alphabetical order:\n");

    for(i = 0; i < n; i++)
        printf("%s\n", name[i]);

    return 0;
}
```

**Sample Output:**

```text
Enter number of names: 4
Ravi
Arun
Kumar
Bala
Alphabetical order:
Arun
Bala
Kumar
Ravi
```
**33. Check Palindrome or Not**

**C Program:**

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int i, len, flag = 0;

    printf("Enter a string: ");
    scanf("%s", str);

    len = strlen(str);

    for(i = 0; i < len / 2; i++)
    {
        if(str[i] != str[len - i - 1])
        {
            flag = 1;
            break;
        }
    }

    if(flag == 0)
        printf("Palindrome");
    else
        printf("Not a palindrome");

    return 0;
}
```

**Sample Output:**

```text
Enter a string: madam
Palindrome
```
**34. Count Vowels, Consonants and Special Characters**

**C Program:**

```c
#include <stdio.h>

int main()
{
    char str[200];
    int i, vowels = 0, consonants = 0, special = 0;

    printf("Enter a string: ");
    scanf(" %[^\n]", str);

    for(i = 0; str[i] != '\0'; i++)
    {
        if((str[i] >= 'a' && str[i] <= 'z') ||
           (str[i] >= 'A' && str[i] <= 'Z'))
        {
            if(str[i] == 'a' || str[i] == 'e' ||
               str[i] == 'i' || str[i] == 'o' ||
               str[i] == 'u' || str[i] == 'A' ||
               str[i] == 'E' || str[i] == 'I' ||
               str[i] == 'O' || str[i] == 'U')
                vowels++;
            else
                consonants++;
        }
        else if(str[i] != ' ')
        {
            special++;
        }
    }

    printf("Vowels = %d\n", vowels);
    printf("Consonants = %d\n", consonants);
    printf("Special characters = %d", special);

    return 0;
}
```

**Sample Output:**

```text
Enter a string: Hello@123
Vowels = 2
Consonants = 3
Special characters = 4
```
**35. Convert Lowercase to Uppercase Without Built-in Function**

**C Program:**

```c
#include <stdio.h>

int main()
{
    char str[100];
    int i;

    printf("Enter a string: ");
    scanf(" %[^\n]", str);

    for(i = 0; str[i] != '\0'; i++)
    {
        if(str[i] >= 'a' && str[i] <= 'z')
            str[i] = str[i] - 32;
    }

    printf("Uppercase string = %s", str);

    return 0;
}
```

**Sample Output:**

```text
Enter a string: hello world
Uppercase string = HELLO WORLD
```
