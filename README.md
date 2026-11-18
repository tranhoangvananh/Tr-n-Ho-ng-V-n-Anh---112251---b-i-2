#include <stdio.h>
#include <stdlib.h>
int main() {
    int rows, cols;
    printf("Nhap so hang: ");
    scanf("%d", &rows);
    printf("Nhap so cot: ");
    scanf("%d", &cols);
    if (rows <= 0 || cols <= 0) {
        printf("So hang va so cot phai lon hon 0!\n");
        return 1;
    }
    float *arr = malloc((size_t)rows * cols * sizeof(float));
    if (arr == NULL) {
        printf("Khong du bo nho!\n");
        return 1;
    }
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("Nhap arr[%d][%d]: ", i, j);
            scanf("%f", arr + i * cols + j);
        }
    }
    printf("\nMa tran vua nhap:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("%.2f\t", *(arr + i * cols + j));
        }
        printf("\n");
    }
    free(arr);
    arr = NULL;
    return 0;
}
