**11. Reverse the Digits of Given Number**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, rev = 0, rem;

    printf("Enter a number: ");
    scanf("%d", &n);

    while(n != 0)
    {
        rem = n % 10;
        rev = rev * 10 + rem;
        n /= 10;
    }

    printf("Reverse = %d", rev);

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 12345
Reverse = 54321
```
**12. Check Prime Number**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i, flag = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    if(n <= 1)
        flag = 1;

    for(i = 2; i <= n / 2; i++)
    {
        if(n % i == 0)
        {
            flag = 1;
            break;
        }
    }

    if(flag == 0)
        printf("Prime number");
    else
        printf("Not a prime number");

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 17
Prime number
```
**13. Print Multiplication Table**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= 10; i++)
        printf("%d x %d = %d\n", n, i, n * i);

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 7
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```
**14. Print Fibonacci Series**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i, a = 0, b = 1, c;

    printf("Enter number of terms: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
    {
        printf("%d ", a);
        c = a + b;
        a = b;
        b = c;
    }

    return 0;
}
```

**Sample Output:**

```text
Enter number of terms: 7
0 1 1 2 3 5 8
```
**15. Find Sum of Even Numbers**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i, sum = 0;

    printf("Enter n: ");
    scanf("%d", &n);

    for(i = 2; i <= n; i += 2)
        sum += i;

    printf("Sum of even numbers = %d", sum);

    return 0;
}
```

**Sample Output:**

```text
Enter n: 10
Sum of even numbers = 30
```
