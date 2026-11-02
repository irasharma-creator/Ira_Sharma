
#include <stdio.h>

#define MAX_DAYS 31
#define THRESHOLD 25.0

// Function declarations
float total_rainfall(float arr[], int n);
float average_rainfall(float arr[], int n);
int wettest_day(float arr[], int n);
int driest_day(float arr[], int n);
int count_above_threshold(float arr[], int n, float threshold);

void enter_data(float arr[], int *n);
void display_data(float arr[], int n);
void display_summary(float arr[], int n);
void compare_months(float a[], int n1, float b[], int n2);

int main()
{
    float month1[MAX_DAYS], month2[MAX_DAYS];
    int n1, n2;
    char choice;

    printf("=================================\n");
    printf("       RAINFALL TRACKER\n");
    printf("=================================\n");

    // First month
    printf("\nENTER FIRST MONTH DATA\n");
    enter_data(month1, &n1);

    display_data(month1, n1);
    display_summary(month1, n1);

    // Ask for second month
    printf("\nDo you want to enter second month data? (y/n): ");
    scanf(" %c", &choice);

    if (choice == 'y' || choice == 'Y')
    {
        printf("\nENTER SECOND MONTH DATA\n");
        enter_data(month2, &n2);

        display_data(month2, n2);
        display_summary(month2, n2);

        compare_months(month1, n1, month2, n2);
    }
    else
    {
        printf("\nThank you for using Rainfall Tracker!\n");
    }

    return 0;
}

// Enter rainfall data
void enter_data(float arr[], int *n)
{
    int i;

    do
    {
        printf("Enter number of days (1-31): ");
        scanf("%d", n);

        if (*n < 1 || *n > 31)
        {
            printf("Invalid number of days. Try again.\n");
        }

    } while (*n < 1 || *n > 31);

    for (i = 0; i < *n; i++)
    {
        do
        {
            printf("Enter rainfall for day %d (mm): ", i + 1);
            scanf("%f", &arr[i]);

            if (arr[i] < 0)
            {
                printf("Rainfall cannot be negative. Try again.\n");
            }

        } while (arr[i] < 0);
    }
}

// Display rainfall table
void display_data(float arr[], int n)
{
    int i;

    printf("\nDay\tRainfall (mm)\n");
    printf("----------------------\n");

    for (i = 0; i < n; i++)
    {
        printf("%d\t%.2f\n", i + 1, arr[i]);
    }
}

// Calculate total rainfall
float total_rainfall(float arr[], int n)
{
    float total = 0;
    int i;

    for (i = 0; i < n; i++)
    {
        total += arr[i];
    }

    return total;
}

// Calculate average rainfall
float average_rainfall(float arr[], int n)
{
    return total_rainfall(arr, n) / n;
}

// Find wettest day
int wettest_day(float arr[], int n)
{
    int i, max = 0;

    for (i = 1; i < n; i++)
    {
        if (arr[i] > arr[max])
        {
            max = i;
        }
    }

    return max;
}

// Find driest day
int driest_day(float arr[], int n)
{
    int i, min = 0;

    for (i = 1; i < n; i++)
    {
        if (arr[i] < arr[min])
        {
            min = i;
        }
    }

    return min;
}

// Count days above threshold
int count_above_threshold(float arr[], int n, float threshold)
{
    int i, count = 0;

    for (i = 0; i < n; i++)
    {
        if (arr[i] > threshold)
        {
            count++;
        }
    }

    return count;
}

// Display statistical summary
void display_summary(float arr[], int n)
{
    int wet = wettest_day(arr, n);
    int dry = driest_day(arr, n);

    printf("\n======= RAINFALL SUMMARY =======\n");

    printf("Total Rainfall  : %.2f mm\n",
           total_rainfall(arr, n));

    printf("Average Per Day : %.2f mm\n",
           average_rainfall(arr, n));

    printf("Wettest Day     : Day %d (%.2f mm)\n",
           wet + 1, arr[wet]);

    printf("Driest Day      : Day %d (%.2f mm)\n",
           dry + 1, arr[dry]);

    printf("Days Above 25mm : %d\n",
           count_above_threshold(arr, n, THRESHOLD));

    printf("================================\n");
}

// Compare two months
void compare_months(float a[], int n1, float b[], int n2)
{
    float total1, total2, avg1, avg2;
    int count1, count2;

    total1 = total_rainfall(a, n1);
    total2 = total_rainfall(b, n2);

    avg1 = average_rainfall(a, n1);
    avg2 = average_rainfall(b, n2);

    count1 = count_above_threshold(a, n1, THRESHOLD);
    count2 = count_above_threshold(b, n2, THRESHOLD);

    printf("\n======= MONTHLY COMPARISON =======\n");

    printf("\tMonth 1\tMonth 2\n");

    printf("Total\t%.2f\t%.2f\n", total1, total2);
    printf("Average\t%.2f\t%.2f\n", avg1, avg2);
    printf("Days >25\t%d\t%d\n", count1, count2);

    if (total1 > total2)
        printf("\nMonth 1 had higher total rainfall.\n");
    else if (total2 > total1)
        printf("\nMonth 2 had higher total rainfall.\n");
    else
        printf("\nBoth months had equal total rainfall.\n");

    if (count1 > count2)
        printf("Month 1 had more days above 25mm.\n");
    else if (count2 > count1)
        printf("Month 2 had more days above 25mm.\n");
    else
        printf("Both months had equal days above 25mm.\n");

    printf("Difference in average rainfall: %.2f mm\n",
           (avg1 > avg2) ? avg1 - avg2 : avg2 - avg1);

    printf("==================================\n");
}
