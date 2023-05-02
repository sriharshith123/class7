#include <stdio.h>

int main() {
    int n, i, j, month, mark, sum_original = 0, sum_revised = 0;
    float avg_original, avg_revised;

    printf("Enter the number of students: ");
    scanf("%d", &n);

    // Input original marks and calculate sum
    printf("Enter the original marks for each student:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &mark);
        sum_original += mark;
    }

    // Input birth month and calculate revised marks
    printf("Enter the birth month for each student:\n");
    for (j = 0; j < n; j++) {
        scanf("%d", &month);
        mark = month + 5; // add booster marks
        sum_revised += mark;
    }

    // Calculate averages
    avg_original = (float) sum_original / n;
    avg_revised = (float) sum_revised / n;

    // Check if revision brings significant increase
    if (avg_revised - avg_original >= 5) {
        printf("Can implement - Significant increase in class average\n");
    } else {
        printf("Need not implement - No significant increase in class average\n");
    }

    return 0;
}
