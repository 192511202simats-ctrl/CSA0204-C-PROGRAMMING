**21. Find Biggest of n Numbers**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int n, i, num, big;

    printf("Enter n: ");
    scanf("%d", &n);

    printf("Enter number 1: ");
    scanf("%d", &big);

    for(i = 2; i <= n; i++)
    {
        printf("Enter number %d: ", i);
        scanf("%d", &num);

        if(num > big)
            big = num;
    }

    printf("Biggest number = %d", big);

    return 0;
}
```

**Sample Output:**

```text
Enter n: 5
Enter number 1: 10
Enter number 2: 45
Enter number 3: 20
Enter number 4: 67
Enter number 5: 30
Biggest number = 67
```
**22. Count Positive and Negative Numbers in Array**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[100], n, i;
    int positive = 0, negative = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements:\n");

    for(i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);

        if(a[i] > 0)
            positive++;
        else if(a[i] < 0)
            negative++;
    }

    printf("Positive numbers = %d\n", positive);
    printf("Negative numbers = %d", negative);

    return 0;
}
```

**Sample Output:**

```text
Enter number of elements: 5
Enter elements:
10
-5
20
-8
7
Positive numbers = 3
Negative numbers = 2
```
**23. Sum and Average of Array Elements**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[100], n, i, sum = 0;
    float average;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements:\n");

    for(i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    average = (float)sum / n;

    printf("Sum = %d\n", sum);
    printf("Average = %.2f", average);

    return 0;
}
```

**Sample Output:**

```text
Enter number of elements: 5
10 20 30 40 50
Sum = 150
Average = 30.00
```
**24. Search an Element in Array**

C Program:

```c
#include <stdio.h>

int main()
{
    int a[100], n, i, search, found = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements:\n");

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    printf("Enter element to search: ");
    scanf("%d", &search);

    for(i = 0; i < n; i++)
    {
        if(a[i] == search)
        {
            found = 1;
            break;
        }
    }

    if(found)
        printf("Element found at position %d", i + 1);
    else
        printf("Element not found");

    return 0;
}
```

**Sample Output:**

```text
Enter number of elements: 5
10 20 30 40 50
Enter element to search: 30
Element found at position 3
```
**25. Sort Elements in Increasing Order**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[100], n, i, j, temp;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements:\n");

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    for(i = 0; i < n - 1; i++)
    {
        for(j = 0; j < n - i - 1; j++)
        {
            if(a[j] > a[j + 1])
            {
                temp = a[j];
                a[j] = a[j + 1];
                a[j + 1] = temp;
            }
        }
    }

    printf("Ascending order:\n");

    for(i = 0; i < n; i++)
        printf("%d ", a[i]);

    return 0;
}
```

**Sample Output:**

```text
Enter number of elements: 5
50 20 40 10 30
Ascending order:
10 20 30 40 50
```
