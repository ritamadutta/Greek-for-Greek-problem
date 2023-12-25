#include <stdio.h>

#define MAX_SIZE 10

// Function to find the determinant of a matrix
int determinant(int matrix[MAX_SIZE][MAX_SIZE], int n);

int main() {
    int n, i, j;

    // Input the size of the matrix
    printf("Enter the size of the square matrix (maximum %d): ", MAX_SIZE);
    scanf("%d", &n);

    if (n > 0 && n <= MAX_SIZE) {
        int matrix[MAX_SIZE][MAX_SIZE];

        // Input the elements of the matrix
        printf("Enter the elements of the matrix:\n");
        for (i = 0; i < n; i++) {
            for (j = 0; j < n; j++) {
                printf("Enter element [%d][%d]: ", i, j);
                scanf("%d", &matrix[i][j]);
            }
        }

        // Calculate and print the determinant
        int det = determinant(matrix, n);
        printf("Determinant of the matrix is: %d\n", det);
    } else {
        printf("Invalid matrix size. Please enter a size between 1 and %d.\n", MAX_SIZE);
    }

    return 0;
}

// Function to find the determinant of a matrix
int determinant(int matrix[MAX_SIZE][MAX_SIZE], int n) {
    int det = 0, i,j,k;

    if (n == 1) {
        return matrix[0][0];
    } else if (n == 2) {
        return matrix[0][0] * matrix[1][1] - matrix[0][1] * matrix[1][0];
    } else {
        int sign = 1;
        for (i = 0; i < n; i++) {
            // Calculate the cofactor and recursive call for submatrix
            int submatrix[MAX_SIZE][MAX_SIZE];
            for (j = 1; j < n; j++) {
                for (k = 0; k < n; k++) {
                    if (k < i) {
                        submatrix[j - 1][k] = matrix[j][k];
                    } else if (k > i) {
                        submatrix[j - 1][k - 1] = matrix[j][k];
                    }
                }
            }
            det += sign * matrix[0][i] * determinant(submatrix, n - 1);
            sign = -sign;
        }
    }

    return det;
}
