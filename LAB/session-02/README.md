**6. Swap Two Numbers**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a, b, temp;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    temp = a;
    a = b;
    b = temp;

    printf("After swapping:\n");
    printf("a = %d\n", a);
    printf("b = %d", b);

    return 0;
}
```

**Sample Output:**

```text
Enter two numbers: 10 20
After swapping:
a = 20
b = 10
```
**7. Find Sum, Difference and Quotient**

**C Program:**

```c
#include <stdio.h>

int main()
{
    float a, b;

    printf("Enter two numbers: ");
    scanf("%f %f", &a, &b);

    printf("Sum = %.2f\n", a + b);
    printf("Difference = %.2f\n", a - b);
    printf("Quotient = %.2f", a / b);

    return 0;
}
```

**Sample Output:**

```text
Enter two numbers: 20 5
Sum = 25.00
Difference = 15.00
Quotient = 4.00
```
**8. Convert Celsius to Fahrenheit**

**C Program:**

```c
#include <stdio.h>

int main()
{
    float c, f;

    printf("Enter temperature in Celsius: ");
    scanf("%f", &c);

    f = (c * 9 / 5) + 32;

    printf("Temperature in Fahrenheit = %.2f", f);

    return 0;
}
```

**Sample Output:**

```text
Enter temperature in Celsius: 25
Temperature in Fahrenheit = 77.00
```
**9. Find Area and Perimeter**

**C Program:**

```c
#include <stdio.h>

int main()
{
    float l, b, area, perimeter;

    printf("Enter length and breadth: ");
    scanf("%f %f", &l, &b);

    area = l * b;
    perimeter = 2 * (l + b);

    printf("Area = %.2f\n", area);
    printf("Perimeter = %.2f", perimeter);

    return 0;
}
```

**Sample Output:**

```text
Enter length and breadth: 10 5
Area = 50.00
Perimeter = 30.00
```
**10. Check Even or Odd**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    if(n % 2 == 0)
        printf("Even number");
    else
        printf("Odd number");

    return 0;
}
```

**Sample Output:**

```text
Enter a number: 24
Even number
```
