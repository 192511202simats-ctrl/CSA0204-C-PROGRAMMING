```
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>
#include <time.h>

/* Sensor data structure */
typedef struct {
    float vibration;
    float temperature;
    float pressure;
    float operatingTime;
} SensorData;

/* Machine structure */
typedef struct {
    int id;
    char name[50];
    int status;
    SensorData sensor;
} Machine;

/* Shared data */
Machine *machines;
int machineCount;

/* Threshold values */
float temperatureThreshold = 80.0;
float vibrationThreshold = 7.0;

/* Mutex for shared machine status */
pthread_mutex_t machineMutex;


/* Function prototypes */
void *collectSensorData(void *arg);
void analyzeMachine(Machine *machine);
void displayMachine(Machine *machine);
void saveHistoricalData(Machine *machine);
void analyzeHierarchy(int level, int maxLevel);
void generateEmergencyAlert(int machineId);


/* Random float generator */
float randomFloat(float min, float max)
{
    return min + ((float)rand() / RAND_MAX) * (max - min);
}


/* Thread function for sensor data collection */
void *collectSensorData(void *arg)
{
    int index = *(int *)arg;

    /* Dynamically updating machine data */
    machines[index].sensor.vibration = randomFloat(1.0, 10.0);
    machines[index].sensor.temperature = randomFloat(30.0, 100.0);
    machines[index].sensor.pressure = randomFloat(20.0, 80.0);
    machines[index].sensor.operatingTime += randomFloat(1.0, 5.0);

    /* Protect shared machine status */
    pthread_mutex_lock(&machineMutex);

    analyzeMachine(&machines[index]);

    pthread_mutex_unlock(&machineMutex);

    free(arg);

    return NULL;
}


/* Analyze machine using pointer */
void analyzeMachine(Machine *machine)
{
    if (machine->sensor.temperature > temperatureThreshold &&
        machine->sensor.vibration > vibrationThreshold)
    {
        machine->status = 2;

        printf("\n========================================\n");
        printf("   EMERGENCY MAINTENANCE ALERT\n");
        printf("========================================\n");
        printf("Machine ID : %d\n", machine->id);
        printf("Machine    : %s\n", machine->name);
        printf("Temperature: %.2f C\n", machine->sensor.temperature);
        printf("Vibration  : %.2f mm/s\n", machine->sensor.vibration);
        printf("STATUS     : CRITICAL\n");
        printf("========================================\n");

        generateEmergencyAlert(machine->id);
    }
    else if (machine->sensor.temperature > temperatureThreshold ||
             machine->sensor.vibration > vibrationThreshold)
    {
        machine->status = 1;

        printf("\nWarning: Machine %d requires inspection.\n",
               machine->id);
    }
    else
    {
        machine->status = 0;
    }

    /* Store historical data in file */
    saveHistoricalData(machine);
}


/* Save machine data to file */
void saveHistoricalData(Machine *machine)
{
    FILE *file = fopen("machine_history.txt", "a");

    if (file == NULL)
    {
        printf("Error opening history file.\n");
        return;
    }

    fprintf(file,
            "Machine %d | %s | Temp: %.2f | Vibration: %.2f | "
            "Pressure: %.2f | Operating Time: %.2f | Status: %d\n",
            machine->id,
            machine->name,
            machine->sensor.temperature,
            machine->sensor.vibration,
            machine->sensor.pressure,
            machine->sensor.operatingTime,
            machine->status);

    fclose(file);
}


/* Recursive hierarchy analysis */
void analyzeHierarchy(int level, int maxLevel)
{
    if (level > maxLevel)
    {
        return;
    }

    printf("Analyzing Machine/Sub-System Level %d\n", level);

    analyzeHierarchy(level + 1, maxLevel);
}


/* Display machine information */
void displayMachine(Machine *machine)
{
    printf("\nMachine ID       : %d\n", machine->id);
    printf("Machine Name     : %s\n", machine->name);
    printf("Temperature      : %.2f C\n",
           machine->sensor.temperature);
    printf("Vibration        : %.2f mm/s\n",
           machine->sensor.vibration);
    printf("Pressure         : %.2f\n",
           machine->sensor.pressure);
    printf("Operating Time   : %.2f hours\n",
           machine->sensor.operatingTime);

    if (machine->status == 0)
        printf("Status           : NORMAL\n");
    else if (machine->status == 1)
        printf("Status           : WARNING\n");
    else
        printf("Status           : CRITICAL\n");
}


/* IPC using pipe and fork */
void generateEmergencyAlert(int machineId)
{
    int pipefd[2];
    char message[100];

    pipe(pipefd);

    pid_t pid = fork();

    if (pid == 0)
    {
        /* Child process: Alert generation */
        close(pipefd[1]);

        read(pipefd[0],
             message,
             sizeof(message));

        printf("\n[ALERT MODULE] %s\n", message);

        close(pipefd[0]);

        exit(0);
    }
    else if (pid > 0)
    {
        /* Parent process: Sensor processing */
        close(pipefd[0]);

        sprintf(message,
                "Emergency maintenance required for Machine %d!",
                machineId);

        write(pipefd[1],
              message,
              strlen(message) + 1);

        close(pipefd[1]);

        wait(NULL);
    }
}


/* Main function */
int main(int argc, char *argv[])
{
    int i;

    /* Command-line arguments */
    if (argc >= 2)
    {
        temperatureThreshold = atof(argv[1]);
    }

    if (argc >= 3)
    {
        vibrationThreshold = atof(argv[2]);
    }

    printf("========================================\n");
    printf(" PREDICTIVE MAINTENANCE SYSTEM\n");
    printf("========================================\n");

    printf("Temperature Threshold: %.2f C\n",
           temperatureThreshold);

    printf("Vibration Threshold  : %.2f mm/s\n",
           vibrationThreshold);

    printf("\nEnter number of machines: ");
    scanf("%d", &machineCount);

    /* Dynamic memory allocation */
    machines = (Machine *)malloc(
        machineCount * sizeof(Machine)
    );

    if (machines == NULL)
    {
        printf("Memory allocation failed.\n");
        return 1;
    }

    /* Initialize machines */
    for (i = 0; i < machineCount; i++)
    {
        machines[i].id = i + 1;

        sprintf(machines[i].name,
                "Machine_%d",
                i + 1);

        machines[i].status = 0;

        machines[i].sensor.vibration = 0;
        machines[i].sensor.temperature = 0;
        machines[i].sensor.pressure = 0;
        machines[i].sensor.operatingTime = 0;
    }

    /* Initialize mutex */
    pthread_mutex_init(&machineMutex, NULL);

    srand(time(NULL));

    /* Recursion for machine hierarchy */
    printf("\n--- Machine Hierarchy Analysis ---\n");

    analyzeHierarchy(1, 3);

    /* Create threads */
    pthread_t *threads;

    threads = (pthread_t *)malloc(
        machineCount * sizeof(pthread_t)
    );

    if (threads == NULL)
    {
        printf("Thread memory allocation failed.\n");

        free(machines);

        return 1;
    }

    printf("\n--- Collecting Sensor Data Concurrently ---\n");

    for (i = 0; i < machineCount; i++)
    {
        int *index = (int *)malloc(sizeof(int));

        *index = i;

        pthread_create(
            &threads[i],
            NULL,
            collectSensorData,
            index
        );
    }

    /* Wait for all threads */
    for (i = 0; i < machineCount; i++)
    {
        pthread_join(threads[i], NULL);
    }

    /* Display results */
    printf("\n========================================\n");
    printf(" MACHINE STATUS REPORT\n");
    printf("========================================\n");

    for (i = 0; i < machineCount; i++)
    {
        displayMachine(&machines[i]);
    }

    /* Free dynamic memory */
    pthread_mutex_destroy(&machineMutex);

    free(threads);

    free(machines);

    printf("\nHistorical data saved in "
           "machine_history.txt\n");

    printf("Predictive Maintenance System Completed.\n");

    return 0;
}
```
