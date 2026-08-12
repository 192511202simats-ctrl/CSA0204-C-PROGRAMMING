**1. Write a C program to input marks (0–100) of a student and display the grade using the given conditions**

- A: 90–100
- B: 80–89
- C: 70–79
- D: 60–69
- F: Below 60

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int marks;

    printf("Enter marks: ");
    scanf("%d", &marks);

    if(marks >= 90 && marks <= 100)
        printf("Grade = A");
    else if(marks >= 80)
        printf("Grade = B");
    else if(marks >= 70)
        printf("Grade = C");
    else if(marks >= 60)
        printf("Grade = D");
    else if(marks >= 0)
        printf("Grade = F");
    else
        printf("Invalid marks");

    return 0;
}
```

**Sample Output:**

```text
Enter marks: 85
Grade = B
```

---

**2. Write a C program to input three integers and determine the largest number using nested if-else statements**

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int a, b, c, largest;

    printf("Enter three integers: ");
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

    printf("Largest number = %d", largest);

    return 0;
}
```

**Sample Output:**

```text
Enter three integers: 25 45 30
Largest number = 45
```

---

**3. Write a C program to print the following pattern**

```text
*****
****
***
**
*
```

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int i, j;

    for(i = 5; i >= 1; i--)
    {
        for(j = 1; j <= i; j++)
        {
            printf("*");
        }

        printf("\n");
    }

    return 0;
}
```

**Sample Output:**

```text
*****
****
***
**
*
```

---

**4. Write a C program to input two integers start and end and print all prime numbers between them using nested loops and appropriate control statements**

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int start, end, i, j, flag;

    printf("Enter start and end: ");
    scanf("%d %d", &start, &end);

    printf("Prime numbers between %d and %d:\n", start, end);

    for(i = start; i <= end; i++)
    {
        if(i < 2)
            continue;

        flag = 1;

        for(j = 2; j <= i / 2; j++)
        {
            if(i % j == 0)
            {
                flag = 0;
                break;
            }
        }

        if(flag == 1)
            printf("%d ", i);
    }

    return 0;
}
```

**Sample Output:**

```text
Enter start and end: 10 30
Prime numbers between 10 and 30:
11 13 17 19 23 29
```
