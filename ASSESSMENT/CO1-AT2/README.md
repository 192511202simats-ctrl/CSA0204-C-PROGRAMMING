**1. Largest of Three Numbers**

Write a C program to find the largest among three numbers using if-else statements.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int a, b, c, largest;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if(a > b)
    {
        if(a > c)
            largest = a;
        else
            largest = c;
    }
    else
    {
        if(b > c)
            largest = b;
        else
            largest = c;
    }

    printf("Largest = %d", largest);

    return 0;
}
```

**Sample Output:**

```text
Enter three numbers: 15 28 10
Largest = 28
```

---

**2. Print Multiplication Table**

Write a C program to display the multiplication table of a given number up to 5 using a for loop.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int n, i;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= 5; i++)
    {
        printf("%d x %d = %d\n", n, i, n * i);
    }

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
```

---

**3. Armstrong Number**

Write a C program to check whether a given 3-digit number is an Armstrong number using do-while loop and if statements.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int n, temp, rem, sum = 0;

    printf("Enter a 3-digit number: ");
    scanf("%d", &n);

    temp = n;

    do
    {
        rem = temp % 10;
        sum = sum + (rem * rem * rem);
        temp = temp / 10;
    }
    while(temp != 0);

    if(sum == n)
        printf("%d is an Armstrong number", n);
    else
        printf("%d is not an Armstrong number", n);

    return 0;
}
```

**Sample Output:**

```text
Enter a 3-digit number: 153
153 is an Armstrong number
```

---

**4. Menu-Driven Calculator**

Write a C program to perform Addition, Subtraction, Multiplication, and Division using the switch statement.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int choice;
    float a, b, result;

    printf("Enter two numbers: ");
    scanf("%f %f", &a, &b);

    printf("\nMenu\n");
    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");

    printf("Enter your choice: ");
    scanf("%d", &choice);

    switch(choice)
    {
        case 1:
            result = a + b;
            printf("Addition = %.2f", result);
            break;

        case 2:
            result = a - b;
            printf("Subtraction = %.2f", result);
            break;

        case 3:
            result = a * b;
            printf("Multiplication = %.2f", result);
            break;

        case 4:
            if(b != 0)
            {
                result = a / b;
                printf("Division = %.2f", result);
            }
            else
            {
                printf("Division by zero is not possible");
            }
            break;

        default:
            printf("Invalid choice");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter two numbers: 20 5

Menu
1. Addition
2. Subtraction
3. Multiplication
4. Division
Enter your choice: 3
Multiplication = 100.00
```
