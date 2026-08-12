**1. Smart Waste Recycling Plant System**

A recycling plant processes 5,000 kg of waste every day.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    float recycled, remaining, percentage;
    int day, maintenance, failure;

    printf("Enter recycled waste in kg: ");
    scanf("%f", &recycled);

    remaining = 5000 - recycled;
    percentage = (recycled / 5000) * 100;

    printf("Recycled Waste = %.2f kg\n", recycled);
    printf("Remaining Waste = %.2f kg\n", remaining);
    printf("Recycled Percentage = %.2f%%\n", percentage);

    if(percentage >= 90)
        printf("Plant Efficiency = Excellent\n");
    else if(percentage >= 75)
        printf("Plant Efficiency = Good\n");
    else if(percentage >= 50)
        printf("Plant Efficiency = Average\n");
    else
        printf("Plant Efficiency = Poor\n");

    printf("\nProcessing for 30 days:\n");

    for(day = 1; day <= 30; day++)
    {
        printf("\nDay %d\n", day);

        printf("Is it a maintenance day? (1-Yes / 0-No): ");
        scanf("%d", &maintenance);

        if(maintenance == 1)
        {
            printf("Maintenance day - Processing skipped.\n");
            continue;
        }

        printf("Did the processing machine fail? (1-Yes / 0-No): ");
        scanf("%d", &failure);

        if(failure == 1)
        {
            printf("Machine failure - Processing stopped.\n");
            break;
        }

        printf("Waste processing completed successfully.\n");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter recycled waste in kg: 4500
Recycled Waste = 4500.00 kg
Remaining Waste = 500.00 kg
Recycled Percentage = 90.00%
Plant Efficiency = Excellent

Processing for 30 days:

Day 1
Is it a maintenance day? (1-Yes / 0-No): 0
Did the processing machine fail? (1-Yes / 0-No): 0
Waste processing completed successfully.

Day 2
Is it a maintenance day? (1-Yes / 0-No): 1
Maintenance day - Processing skipped.

Day 3
Is it a maintenance day? (1-Yes / 0-No): 0
Did the processing machine fail? (1-Yes / 0-No): 1
Machine failure - Processing stopped.
```

---

**2. IT Company Project Performance Evaluation (2025–2026)**

An IT company completed 20 software projects. Each project is evaluated based on Quality Score and Delivery Delay.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int i, quality, delay;
    int cancelled, stop;
    int totalQuality = 0;
    int onTimeProjects = 0;
    float averageQuality, deliveryPercentage;

    printf("Enter quality score and delay for 20 projects.\n");

    for(i = 1; i <= 20; i++)
    {
        printf("\nProject %d\n", i);

        printf("Is the project cancelled? (1-Yes / 0-No): ");
        scanf("%d", &cancelled);

        if(cancelled == 1)
        {
            printf("Project cancelled - Evaluation skipped.\n");
            continue;
        }

        printf("Enter quality score: ");
        scanf("%d", &quality);

        printf("Enter delivery delay in days: ");
        scanf("%d", &delay);

        totalQuality += quality;

        if(delay <= 5)
            onTimeProjects++;

        if(quality >= 90 && delay <= 2)
            printf("Performance = Excellent\n");
        else if(quality >= 75 && quality <= 89 && delay <= 5)
            printf("Performance = Good\n");
        else if(quality >= 60 && quality <= 74)
            printf("Performance = Average\n");
        else
            printf("Performance = Needs Improvement\n");

        printf("Should management stop the evaluation? (1-Yes / 0-No): ");
        scanf("%d", &stop);

        if(stop == 1)
        {
            printf("Management stopped the evaluation.\n");
            break;
        }
    }

    averageQuality = totalQuality / 20.0;
    deliveryPercentage = (onTimeProjects / 20.0) * 100;

    printf("\nAverage Quality Score = %.2f\n", averageQuality);
    printf("Delivery Percentage = %.2f%%\n", deliveryPercentage);

    return 0;
}
```

**Sample Output:**

```text
Enter quality score and delay for 20 projects.

Project 1
Is the project cancelled? (1-Yes / 0-No): 0
Enter quality score: 95
Enter delivery delay in days: 2
Performance = Excellent
Should management stop the evaluation? (1-Yes / 0-No): 0

Project 2
Is the project cancelled? (1-Yes / 0-No): 0
Enter quality score: 82
Enter delivery delay in days: 4
Performance = Good
Should management stop the evaluation? (1-Yes / 0-No): 1
Management stopped the evaluation.

Average Quality Score = 8.85
Delivery Percentage = 10.00%
```

---

**3. Semiconductor Chip Manufacturing System**

A semiconductor company manufactures 10,000 chips per day.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int defective, accepted;
    float defectPercentage;
    int day, maintenance, breakdown;

    printf("Enter number of defective chips: ");
    scanf("%d", &defective);

    accepted = 10000 - defective;
    defectPercentage = (defective / 10000.0) * 100;

    printf("Defective Chips = %d\n", defective);
    printf("Accepted Chips = %d\n", accepted);
    printf("Defect Percentage = %.2f%%\n", defectPercentage);

    if(defectPercentage < 1)
        printf("Quality Grade = A\n");
    else if(defectPercentage <= 3)
        printf("Quality Grade = B\n");
    else if(defectPercentage <= 5)
        printf("Quality Grade = C\n");
    else
        printf("Batch Status = Reject Batch\n");

    printf("\nProduction processing for 30 days:\n");

    for(day = 1; day <= 30; day++)
    {
        printf("\nDay %d\n", day);

        printf("Is it a maintenance day? (1-Yes / 0-No): ");
        scanf("%d", &maintenance);

        if(maintenance == 1)
        {
            printf("Maintenance day - Production skipped.\n");
            continue;
        }

        printf("Did machine breakdown occur? (1-Yes / 0-No): ");
        scanf("%d", &breakdown);

        if(breakdown == 1)
        {
            printf("Machine breakdown - Production stopped.\n");
            break;
        }

        printf("10,000 chips produced successfully.\n");
    }

    return 0;
}
```

**Sample Output:**

```text
Enter number of defective chips: 200
Defective Chips = 200
Accepted Chips = 9800
Defect Percentage = 2.00%
Quality Grade = B

Production processing for 30 days:

Day 1
Is it a maintenance day? (1-Yes / 0-No): 0
Did machine breakdown occur? (1-Yes / 0-No): 0
10,000 chips produced successfully.

Day 2
Is it a maintenance day? (1-Yes / 0-No): 1
Maintenance day - Production skipped.

Day 3
Is it a maintenance day? (1-Yes / 0-No): 0
Did machine breakdown occur? (1-Yes / 0-No): 1
Machine breakdown - Production stopped.
```

---

**4. Cloud Storage Subscription Management (2026)**

A cloud company offers Basic – 100 GB, Standard – 500 GB and Enterprise – 2 TB storage plans. Extra storage costs ₹4 per GB.

**C-Program:**

```c
#include <stdio.h>

int main()
{
    int customers;
    int i, plan, active;
    float capacity, used, remaining, extra, extraCharge, usagePercentage;

    printf("Enter number of customers: ");
    scanf("%d", &customers);

    for(i = 1; i <= customers; i++)
    {
        printf("\nCustomer %d\n", i);

        printf("Is the account active? (1-Yes / 0-No): ");
        scanf("%d", &active);

        if(active == 0)
        {
            printf("Inactive account - Customer skipped.\n");
            continue;
        }

        printf("Select plan:\n");
        printf("1. Basic - 100 GB\n");
        printf("2. Standard - 500 GB\n");
        printf("3. Enterprise - 2000 GB\n");
        printf("Enter plan: ");
        scanf("%d", &plan);

        if(plan == 1)
            capacity = 100;
        else if(plan == 2)
            capacity = 500;
        else if(plan == 3)
            capacity = 2000;
        else
        {
            printf("Invalid plan.\n");
            continue;
        }

        printf("Enter used storage in GB: ");
        scanf("%f", &used);

        remaining = capacity - used;
        usagePercentage = (used / capacity) * 100;

        if(used > capacity)
        {
            extra = used - capacity;
            extraCharge = extra * 4;
            remaining = 0;

            printf("Extra Storage = %.2f GB\n", extra);
            printf("Extra Charge = Rs. %.2f\n", extraCharge);
            printf("Storage Status = Storage Limit Exceeded\n");
        }
        else
        {
            extraCharge = 0;

            printf("Remaining Storage = %.2f GB\n", remaining);
            printf("Extra Charge = Rs. %.2f\n", extraCharge);

            if(usagePercentage > 95)
                printf("Storage Status = Warning: Storage usage is above 95%%\n");
            else
                printf("Storage Status = Normal\n");
        }

        if(i == customers)
        {
            printf("Server storage is full. Processing stopped.\n");
            break;
        }
    }

    return 0;
}
```

**Sample Output:**

```text
Enter number of customers: 3

Customer 1
Is the account active? (1-Yes / 0-No): 1
Select plan:
1. Basic - 100 GB
2. Standard - 500 GB
3. Enterprise - 2000 GB
Enter plan: 2
Enter used storage in GB: 480
Remaining Storage = 20.00 GB
Extra Charge = Rs. 0.00
Storage Status = Warning: Storage usage is above 95%

Customer 2
Is the account active? (1-Yes / 0-No): 0
Inactive account - Customer skipped.

Customer 3
Is the account active? (1-Yes / 0-No): 1
Select plan:
1. Basic - 100 GB
2. Standard - 500 GB
3. Enterprise - 2000 GB
Enter plan: 1
Enter used storage in GB: 120
Extra Storage = 20.00 GB
Extra Charge = Rs. 80.00
Storage Status = Storage Limit Exceeded
Server storage is full. Processing stopped.
```
