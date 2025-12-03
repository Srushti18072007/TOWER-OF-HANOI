#include <stdio.h>

void tow(int n, char first_rod, char sec_rod, char third_rod) {
    if (n == 1) {
        printf("Move disk 1 from %c to %c\n", first_rod, sec_rod);
        return;
    }

    tow(n - 1, first_rod, third_rod, sec_rod);

    printf("Move disk %d first %c sec %c\n", n, first_rod, sec_rod);

    tow(n - 1, third_rod, sec_rod, first_rod);
}

int main() {
    int n;
    printf("Enter number of disks: \n");
    scanf("%d", &n);

    tow(n, 'A', 'C', 'B');
    return 0;
}
