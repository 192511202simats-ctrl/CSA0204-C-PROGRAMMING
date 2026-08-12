**26. Find Duplicate Elements in Array**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[100], n, i, j;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements:\n");

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    printf("Duplicate elements:\n");

    for(i = 0; i < n; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if(a[i] == a[j])
            {
                printf("%d ", a[i]);
                break;
            }
        }
    }

    return 0;
}
```

**Sample Output:**

```text
Enter number of elements: 6
10 20 30 20 40 10
Duplicate elements:
10 20
```
**27. Addition of Two Matrices**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[10][10], b[10][10], c[10][10];
    int r, col, i, j;

    printf("Enter rows and columns: ");
    scanf("%d %d", &r, &col);

    printf("Enter first matrix:\n");

    for(i = 0; i < r; i++)
        for(j = 0; j < col; j++)
            scanf("%d", &a[i][j]);

    printf("Enter second matrix:\n");

    for(i = 0; i < r; i++)
        for(j = 0; j < col; j++)
            scanf("%d", &b[i][j]);

    for(i = 0; i < r; i++)
        for(j = 0; j < col; j++)
            c[i][j] = a[i][j] + b[i][j];

    printf("Result:\n");

    for(i = 0; i < r; i++)
    {
        for(j = 0; j < col; j++)
            printf("%d ", c[i][j]);

        printf("\n");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter rows and columns: 2 2
Enter first matrix:
1 2
3 4
Enter second matrix:
5 6
7 8
Result:
6 8
10 12
```
**28. Matrix Multiplication**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[10][10], b[10][10], c[10][10];
    int r1, c1, r2, c2, i, j, k;

    printf("Enter rows and columns of first matrix: ");
    scanf("%d %d", &r1, &c1);

    printf("Enter rows and columns of second matrix: ");
    scanf("%d %d", &r2, &c2);

    if(c1 != r2)
    {
        printf("Matrix multiplication not possible");
        return 0;
    }

    printf("Enter first matrix:\n");

    for(i = 0; i < r1; i++)
        for(j = 0; j < c1; j++)
            scanf("%d", &a[i][j]);

    printf("Enter second matrix:\n");

    for(i = 0; i < r2; i++)
        for(j = 0; j < c2; j++)
            scanf("%d", &b[i][j]);

    for(i = 0; i < r1; i++)
    {
        for(j = 0; j < c2; j++)
        {
            c[i][j] = 0;

            for(k = 0; k < c1; k++)
                c[i][j] += a[i][k] * b[k][j];
        }
    }

    printf("Result:\n");

    for(i = 0; i < r1; i++)
    {
        for(j = 0; j < c2; j++)
            printf("%d ", c[i][j]);

        printf("\n");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter rows and columns of first matrix: 2 2
Enter rows and columns of second matrix: 2 2
Enter first matrix:
1 2
3 4
Enter second matrix:
5 6
7 8
Result:
19 22
43 50
```
**29. Find Transpose of Matrix**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[10][10], r, c, i, j;

    printf("Enter rows and columns: ");
    scanf("%d %d", &r, &c);

    printf("Enter matrix:\n");

    for(i = 0; i < r; i++)
        for(j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    printf("Transpose:\n");

    for(i = 0; i < c; i++)
    {
        for(j = 0; j < r; j++)
            printf("%d ", a[j][i]);

        printf("\n");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter rows and columns: 2 3
Enter matrix:
1 2 3
4 5 6
Transpose:
1 4
2 5
3 6
```
**30. Find Sum of Diagonal Elements**

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a[10][10], n, i, j, sum = 0;

    printf("Enter size of matrix: ");
    scanf("%d", &n);

    printf("Enter matrix:\n");

    for(i = 0; i < n; i++)
        for(j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    for(i = 0; i < n; i++)
        sum += a[i][i];

    printf("Sum of diagonal elements = %d", sum);

    return 0;
}
```

**Sample Output:**

```text
Enter size of matrix: 3
Enter matrix:
1 2 3
4 5 6
7 8 9
Sum of diagonal elements = 15
```
