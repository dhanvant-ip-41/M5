# EX-21-POINTERS
## AIM:
Write a C program to convert a 23.65 into 25 using pointer

## ALGORITHM:
1.	Declare a double variable to hold the floating-point number (23.65).
2.	Declare a pointer to double to point to the address of the variable.
3.	Use the pointer to modify the value to 25.0.
4.	Print the modified value.

## PROGRAM:
```c
#include <stdio.h>
#include <math.h>

void roundToNext25(float *num, int *result) {
    // Round *num up to next multiple of 25
    *result = (int)(ceil((*num) / 25) * 25);
}

int main() {
    float number = 23.65;
    int rounded;

    roundToNext25(&number, &rounded);

    printf("Original number: %.2f\n", number);
    printf("Rounded up to nearest 25: %d\n", rounded);

    return 0;
}

```
## OUTPUT:
 ![445630037-ce515fb9-87b0-42a1-85ed-8e6b55a40f94](https://github.com/user-attachments/assets/eaf766bb-f277-4dab-ba37-ac7f1f2b78db)












## RESULT:
Thus the program to convert a 23.65 into 25 using pointer has been executed successfully.
 
 


# EX-22-FUNCTIONS AND STORAGE CLASS

## AIM:

Write a C program to calculate the Product of first 12 natural numbers using Recursion

## ALGORITHM:

1.	Define a recursive function calculateProduct that takes an integer parameter n.
2.	Return n multiplied by the result of the calculateProduct function called with n - 1.
3.	Declare an integer variable n and an unsigned long long variable product.
4.	Initialize n with the value 12 (for the first 12 natural numbers).
5.	Call the calculateProduct function with n and store the result in the product variable.
6.	Print the result, indicating it is the product of the first 12 natural numbers.

## PROGRAM:
```c
#include <stdio.h>

// Recursive function to calculate product of first n natural numbers
unsigned long long product(int n) {
    if (n == 1) {
        return 1;  // Base case
    }
    return n * product(n - 1);  // Recursive case
}

int main() {
    int n = 12;
    unsigned long long result = product(n);
    printf("Product of first %d natural numbers is: %llu\n", n, result);
    return 0;
}
```

## OUTPUT:
![445630606-ef338eef-1dd7-476f-b921-ad086c9928c8](https://github.com/user-attachments/assets/f2a4c1fa-6f19-4f75-bdfd-748f40b8f4d5)
         		
## RESULT:

Thus the program has been executed successfully.
 
 


# EX-23-ARRAYS AND ITS OPERATIONS

## AIM:

Write C Program to find Sum of each row of a Matrix

## ALGORITHM:

1.	Declare and initialize the matrix with the desired values.
2.	Create a loop to iterate through each row of the matrix.
3.	Inside the loop, calculate the sum of the elements in each row.
4.	Print the sum for each row.

## PROGRAM:
```c
#include <stdio.h>

int main() {
    int rows, cols;
    
    printf("Enter the number of rows: ");
    scanf("%d", &rows);
    
    printf("Enter the number of columns: ");
    scanf("%d", &cols);
    
    int matrix[rows][cols];
    
    // Input matrix elements
    printf("Enter the elements of the matrix:\n");
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    
    // Calculate and print sum of each row
    for(int i = 0; i < rows; i++) {
        int rowSum = 0;
        for(int j = 0; j < cols; j++) {
            rowSum += matrix[i][j];
        }
        printf("Sum of row %d = %d\n", i+1, rowSum);
    }
    
    return 0;
}

```

## OUTPUT

![445631403-bb94afa7-da58-4b41-95fa-0b7347409555](https://github.com/user-attachments/assets/4a5b4476-a7aa-4df1-935f-147b817fc82a)

 
 

 ## RESULT
Thus the program to find the sum of each row of the matrix is executed successfully 


# EX-24-STRINGS

## AIM:

Write C program for the below pyramid string pattern. Enter a string: PROGRAM Enter number of rows: 5 P R O G R A M P R O G R A M P R O G R A M

## ALGORITHM:

1.	Input the number of rows for the pyramid (e.g., num_rows).
2.	Initialize variables:i for the row count (starting from 1),j for the character count (starting from 1)
3.	Start a loop for i from 1 to num_rows (for each row of the pyramid).
4.	Calculate the midpoint position as midpoint = (2 * num_rows - 1) / 2.
5.	End the program.

## PROGRAM:
```c
#include <stdio.h>
#include <string.h>

void printPyramidPattern(char str[], int rows) {
    int len = strlen(str);
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j <= i; j++) {
            printf("%c ", str[j % len]);
        }
        printf("\n");
    }
}

int main() {
    char str[100];
    int rows;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = 0; // Remove newline character

    printf("Enter number of rows: ");
    scanf("%d", &rows);

    printPyramidPattern(str, rows);

    return 0;
}
```

 ## OUTPUT
![445633845-ad541ab3-c69c-4628-8ba1-18e290c8befa](https://github.com/user-attachments/assets/bd881640-e11c-4352-b856-6a030093f780)

 

## RESULT

Thus the C program to String process executed successfully



# EX -25 –DISPLAYING ARRAYS USING POINTERS
## AIM

Write a c program to read and display an array of any 6 integer elements using pointer

## ALGORITHM
Step 1: Start the program.
Step 2: Declare the following:
•	Integer variable i for iteration.
•	Integer variable n to store the number of elements.
•	Integer array arr[10] to hold up to 10 elements.
•	Integer pointer parr and initialize it to point to the array arr.
Step 3: Read the value of n (number of elements) from the user.
Step 4: Loop from i = 0 to i < n:
•	Read an integer value and store it in the address parr + i using pointer arithmetic.
Step 5: Loop from i = 0 to i < n:
•	Print the element at *(parr + i) using pointer dereferencing.
Step 6: End the program.

## PROGRAM
```c
#include <stdio.h>

void readArray(int *arr, int size) {
    printf("Enter %d elements: ", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", arr + i);
    }
}

void displayArray(int *arr, int size) {
    printf("Array elements: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", *(arr + i));
    }
    printf("\n");
}

int main() {
    int arr[6];

    readArray(arr, 6);
    displayArray(arr, 6);

    return 0;
}
```
## OUTPUT
![445634733-7b5242f1-ab69-4b8d-9caf-bd73e5456848](https://github.com/user-attachments/assets/6f3ac850-09ae-4251-a3de-4eb715493e7b)

 

## RESULT

Thus the C program to read and display an array of any 6 integer elements using pointer has been executed


