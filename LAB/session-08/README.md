**36. Student Structure and Result**

**C Program:**

```c
#include <stdio.h>

struct Student
{
    int regno;
    char name[50];
    char department[50];
    int mark[5];
    int total;
    float average;
};

int main()
{
    struct Student s[5];
    int i, j;

    for(i = 0; i < 5; i++)
    {
        printf("\nEnter details of student %d\n", i + 1);

        printf("Register No: ");
        scanf("%d", &s[i].regno);

        printf("Name: ");
        scanf("%s", s[i].name);

        printf("Department: ");
        scanf("%s", s[i].department);

        s[i].total = 0;

        printf("Enter 5 subject marks:\n");

        for(j = 0; j < 5; j++)
        {
            scanf("%d", &s[i].mark[j]);
            s[i].total += s[i].mark[j];
        }

        s[i].average = s[i].total / 5.0;
    }

    printf("\n----- STUDENT RESULT -----\n");

    for(i = 0; i < 5; i++)
    {
        printf("\nRegister No: %d", s[i].regno);
        printf("\nName: %s", s[i].name);
        printf("\nDepartment: %s", s[i].department);
        printf("\nTotal = %d", s[i].total);
        printf("\nAverage = %.2f", s[i].average);

        if(s[i].average >= 50)
            printf("\nResult: PASS\n");
        else
            printf("\nResult: FAIL\n");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter details of student 1
Register No: 101
Name: Arun
Department: CSE
Enter 5 subject marks:
80 75 90 85 70

----- STUDENT RESULT -----

Register No: 101
Name: Arun
Department: CSE
Total = 400
Average = 80.00
Result: PASS
```
