**16. Find Biggest Among Three Numbers**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a, b, c, big;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    big = a;

    if(b > big)
        big = b;

    if(c > big)
        big = c;

    printf("Biggest number = %d", big);

    return 0;
}
```

**Sample Output:**

```text
Enter three numbers: 25 45 30
Biggest number = 45
```
**17. Check Armstrong Number**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, temp, rem, sum = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    temp = n;

    while(temp != 0)
    {
        rem = temp % 10;
        sum += rem * rem * rem;
        temp /= 10;
    }

    if(sum == n)
        printf("Armstrong number");
    else
        printf("Not an Armstrong number");

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 153
Armstrong number
```
**18. Find Sum of Digits**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, sum = 0, rem;

    printf("Enter a number: ");
    scanf("%d", &n);

    while(n != 0)
    {
        rem = n % 10;
        sum += rem;
        n /= 10;
    }

    printf("Sum of digits = %d", sum);

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 12345
Sum of digits = 15
```
**19. Calculate Electricity Bill**

**C Program:**

```c
#include <stdio.h>

int main()
{
    float units, bill;

    printf("Enter units consumed: ");
    scanf("%f", &units);

    if(units > 800)
        bill = units * 4;
    else if(units > 400)
        bill = units * 3;
    else if(units > 200)
        bill = units * 2.50;
    else if(units >= 100)
        bill = units * 1.50;
    else
        bill = units * 1;

    printf("Electricity Bill = Rs. %.2f", bill);

    return 0;
}
```

**Sample Output:**

```text
Enter units consumed: 500
Electricity Bill = Rs. 1500.00
```
**20. Sum of Even Terms in Fibonacci Series**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i, a = 0, b = 1, c, sum = 0;

    printf("Enter number of terms: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++)
    {
        if(a % 2 == 0)
            sum += a;

        c = a + b;
        a = b;
        b = c;
    }

    printf("Sum of even terms = %d", sum);

    return 0;
}
```

**Sample Output:**

```text
Enter number of terms: 10
Sum of even terms = 44
```
