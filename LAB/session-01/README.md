**1. Find Sum of n Natural Numbers**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i, sum = 0;

    printf("Enter n: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
        sum += i;

    printf("Sum = %d", sum);

    return 0;
}
```

**Sample Output:**

```text
Enter n: 10
Sum = 55
```
**2. Calculate Simple Interest**

**C Program:**

```c
#include <stdio.h>

int main()
{
    float p, r, t, si;

    printf("Enter principal, rate and time: ");
    scanf("%f %f %f", &p, &r, &t);

    si = (p * r * t) / 100;

    printf("Simple Interest = %.2f", si);

    return 0;
}
```

**Sample Output:**

```text
Enter principal, rate and time: 10000 5 2
Simple Interest = 1000.00
```
**3. Print Multiplication Table**

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
Enter a number: 5
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```
**4. Find n Even Numbers**

C Program:

```c
#include <stdio.h>

int main()
{
    int n, i;

    printf("Enter n: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
        printf("%d ", 2 * i);

    return 0;
}
```

**Sample Output:**

```text
Enter n: 5
2 4 6 8 10
```
**5. Find Factorial of Given Number**

C Program:

```c
#include <stdio.h>

int main()
{
    int n, i;
    long long fact = 1;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
        fact *= i;

    printf("Factorial = %lld", fact);

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 5
Factorial = 120
```
