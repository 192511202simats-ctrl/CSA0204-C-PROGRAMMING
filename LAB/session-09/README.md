**37. Define a Structure Student and Display the Details of the Student**

**C-Program:**

```c
#include <stdio.h>

struct Student
{
    int rollno;
    char name[50];
    float marks;
};

int main()
{
    struct Student s;

    printf("Enter Roll Number: ");
    scanf("%d", &s.rollno);

    printf("Enter Name: ");
    scanf("%s", s.name);

    printf("Enter Marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Details\n");
    printf("Roll Number = %d\n", s.rollno);
    printf("Name = %s\n", s.name);
    printf("Marks = %.2f", s.marks);

    return 0;
}
```

**Sample Output:**

```text
Enter Roll Number: 101
Enter Name: Arun
Enter Marks: 85

Student Details
Roll Number = 101
Name = Arun
Marks = 85.00
```

---

**38. Define a Structure Employee and Display the Details of Three Employees**

**C-Program:**

```c
#include <stdio.h>

struct Employee
{
    int id;
    char name[50];
    float salary;
};

int main()
{
    struct Employee e[3];
    int i;

    for(i = 0; i < 3; i++)
    {
        printf("\nEnter details of Employee %d\n", i + 1);

        printf("Employee ID: ");
        scanf("%d", &e[i].id);

        printf("Name: ");
        scanf("%s", e[i].name);

        printf("Salary: ");
        scanf("%f", &e[i].salary);
    }

    printf("\nEmployee Details\n");

    for(i = 0; i < 3; i++)
    {
        printf("\nEmployee %d\n", i + 1);
        printf("ID = %d\n", e[i].id);
        printf("Name = %s\n", e[i].name);
        printf("Salary = %.2f\n", e[i].salary);
    }

    return 0;
}
```

**Sample Output:**

```text
Enter details of Employee 1
Employee ID: 101
Name: Arun
Salary: 25000

Enter details of Employee 2
Employee ID: 102
Name: Bala
Salary: 30000

Enter details of Employee 3
Employee ID: 103
Name: Kumar
Salary: 28000

Employee Details

Employee 1
ID = 101
Name = Arun
Salary = 25000.00

Employee 2
ID = 102
Name = Bala
Salary = 30000.00

Employee 3
ID = 103
Name = Kumar
Salary = 28000.00
```

---

**39. Define a Structure Book and Display the Book Information Entered by the User**

**C-Program:**

```c
#include <stdio.h>

struct Book
{
    int id;
    char title[50];
    char author[50];
    float price;
};

int main()
{
    struct Book b;

    printf("Enter Book ID: ");
    scanf("%d", &b.id);

    printf("Enter Book Title: ");
    scanf("%s", b.title);

    printf("Enter Author Name: ");
    scanf("%s", b.author);

    printf("Enter Price: ");
    scanf("%f", &b.price);

    printf("\nBook Information\n");
    printf("Book ID = %d\n", b.id);
    printf("Title = %s\n", b.title);
    printf("Author = %s\n", b.author);
    printf("Price = %.2f", b.price);

    return 0;
}
```

**Sample Output:**

```text
Enter Book ID: 101
Enter Book Title: CProgramming
Enter Author Name: Dennis
Enter Price: 450

Book Information
Book ID = 101
Title = CProgramming
Author = Dennis
Price = 450.00
```

---

**40. Define a Structure Product and Calculate the Total Cost Using Quantity and Unit Price**

**C-Program:**

```c
#include <stdio.h>

struct Product
{
    int id;
    char name[50];
    int quantity;
    float unitprice;
    float totalcost;
};

int main()
{
    struct Product p;

    printf("Enter Product ID: ");
    scanf("%d", &p.id);

    printf("Enter Product Name: ");
    scanf("%s", p.name);

    printf("Enter Quantity: ");
    scanf("%d", &p.quantity);

    printf("Enter Unit Price: ");
    scanf("%f", &p.unitprice);

    p.totalcost = p.quantity * p.unitprice;

    printf("\nProduct Details\n");
    printf("Product ID = %d\n", p.id);
    printf("Product Name = %s\n", p.name);
    printf("Quantity = %d\n", p.quantity);
    printf("Unit Price = %.2f\n", p.unitprice);
    printf("Total Cost = %.2f", p.totalcost);

    return 0;
}
```

**Sample Output:**

```text
Enter Product ID: 101
Enter Product Name: Pen
Enter Quantity: 10
Enter Unit Price: 20

Product Details
Product ID = 101
Product Name = Pen
Quantity = 10
Unit Price = 20.00
Total Cost = 200.00
```

---

**41. Define a Structure Rectangle and Calculate Its Area and Perimeter**

**C-Program:**

```c
#include <stdio.h>

struct Rectangle
{
    float length;
    float breadth;
    float area;
    float perimeter;
};

int main()
{
    struct Rectangle r;

    printf("Enter Length: ");
    scanf("%f", &r.length);

    printf("Enter Breadth: ");
    scanf("%f", &r.breadth);

    r.area = r.length * r.breadth;
    r.perimeter = 2 * (r.length + r.breadth);

    printf("\nRectangle Details\n");
    printf("Length = %.2f\n", r.length);
    printf("Breadth = %.2f\n", r.breadth);
    printf("Area = %.2f\n", r.area);
    printf("Perimeter = %.2f", r.perimeter);

    return 0;
}
```

**Sample Output:**

```text
Enter Length: 10
Enter Breadth: 5

Rectangle Details
Length = 10.00
Breadth = 5.00
Area = 50.00
Perimeter = 30.00
```
