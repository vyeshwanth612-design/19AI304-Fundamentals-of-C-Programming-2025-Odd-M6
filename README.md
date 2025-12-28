# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
## 11. Implementation of the concept of pointer to function.
## 12. Implementation of programs using structure and union.
## 13. Implementation of programs for different storage classes.
# Ex.No:26
  Develop a C program using static storage class in function with parameter and without return to display the incremental float values as indicated in the following output.
| Input | Output                                       |
|-------|----------------------------------------------|
| 1     | 101.25&nbsp;&nbsp;201.50&nbsp;&nbsp;301.75&nbsp;&nbsp;402.00&nbsp;&nbsp;502.75 |
# Date : 
# Aim:
To develop a C program using the static storage class in a function with a parameter and without a return value to display the required output.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  a. Declare an integer variable `input` to store the user’s number.  
  b. Inside the function `display(int n)`, declare a static float variable `base` and initialize it to 100.25.
### Step 4:
  Read an integer from the user and store it in `input`.
### Step 5:
  Call the function `display(input)` five times.
### Step 6:
  Inside the `display` function, for each call:  
  a. Calculate the sum of `base` and `n`.  
  b. Display the value.  
  c. Increase the value of `base` by 100.25.
### Step 7:
  Repeat Step 6 for all function calls.
### Step 8:
  Stop
# Program:
```c
#include <stdio.h>


void display(float increment) {
    static float value = 101.25;  

    printf("%.2f ", value);
    value += increment;
}

int main() {
    int i;
    int n = 5;          
    float inc = 100.25; 

    for (i = 0; i < n; i++) {
        display(inc);
    }

    return 0;
}

```
# Output:

<img width="1446" height="713" alt="new4 1" src="https://github.com/user-attachments/assets/12829ac9-28e0-4ce5-b1d7-d8296ddc7b73" />





# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:27
  Implement a C program to perform arithmetic operations (addition, subtraction, multiplication, division) on two integers using function pointers. The user should input two numbers and select the desired operation from a menu.
# Date : 
# Aim:
  To implement a C program that uses function pointers to perform arithmetic operations (add, subtract, multiply, divide) on two integers based on user choice.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Declare four functions to perform arithmetic operations:  
  - `add(int a, int b)`  
  - `subtract(int a, int b)`  
  - `multiply(int a, int b)`  
  - `divide(int a, int b)`
### Step 4:
  Declare a function pointer `int (*operation)(int, int)` to point to any of the arithmetic functions.
### Step 5:
  Input two integers from the user (`num1` and `num2`).
### Step 6:
  Display a menu for the user to choose an operation:  
  - Add  
  - Subtract  
  - Multiply  
  - Divide
### Step 7:
  Read the user’s choice.
### Step 8:
  Use a switch statement to assign the function pointer `operation` to the appropriate function based on the user’s choice.  
  - **Step 8.1:** If the choice is 4 (divide), check if the second number is zero. If yes, display an error and terminate.  
  - **Step 8.2:** If the choice is invalid, display an error and terminate.
### Step 9:
  Call the function using the function pointer and store the result in a variable `result`.
### Step 10:
  Display the result.
### Step 11:
  Stop
# Program:
```c
#include <stdio.h>


int add(int a, int b);
int subtract(int a, int b);
int multiply(int a, int b);
int divide(int a, int b);

int main() {
    int num1, num2, choice;
    int (*operation)(int, int);   

    
    printf("Enter two integers: ");
    scanf("%d %d", &num1, &num2);

    printf("\nChoose an operation:\n");
    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    
    switch (choice) {
        case 1:
            operation = add;
            break;
        case 2:
            operation = subtract;
            break;
        case 3:
            operation = multiply;
            break;
        case 4:
            if (num2 == 0) {
                printf("Error: Division by zero is not allowed.\n");
                return 0;
            }
            operation = divide;
            break;
        default:
            printf("Invalid choice!\n");
            return 0;
    }

    
    printf("Result = %d\n", operation(num1, num2));

    return 0;
}

int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

int divide(int a, int b) {
    return a / b;
}

```
# Output:

<img width="1444" height="724" alt="new4 2" src="https://github.com/user-attachments/assets/eea8b40b-5941-4cfe-9181-3f6f5eef27e3" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:28
  Develop a C program to store details of n employees (employee number, name, and salary) using structures, and display the employee(s) with the highest salary.
# Date : 
# Aim:
  To develop and implement a C program that uses a structure to store employee details (employee number, name, and salary) and determine the employee(s) with the highest salary.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure `employee` with the following members:  
  - `eno` (employee number)  
  - `ename` (employee name)  
  - `salary` (employee salary)
### Step 4:
  Declare an array of structures to store details of multiple employees.
### Step 5:
  Input the number of employees, `n`.
### Step 6:
  For each employee (`i = 0` to `n-1`), do the following:  
  - **Step 6.1:** Input employee number.  
  - **Step 6.2:** Input employee name (allow spaces).  
  - **Step 6.3:** Input employee salary.  
  - **Step 6.4 (Optional):** Print the entered details for verification.
### Step 7:
  Initialize a variable `high` with the salary of the first employee.
### Step 8:
  For each employee (`i = 1` to `n-1`), do the following:  
  - **Step 8.1:** Compare employee salary with `high`.  
  - **Step 8.2:** If the salary is greater than `high`, update `high` with this salary.
### Step 9:
  Print the details of employee(s) whose salary matches `high`:  
  - **Step 9.1:** Loop through all employees.  
  - **Step 9.2:** If employee salary equals `high`, print employee number, name, and salary.
### Step 10:
  Stop
# Program:
```c
#include <stdio.h>
#include <string.h>

struct Employee {
    int empNo;
    char name[50];
    float salary;
};

int main() {
    int n, i;
    float maxSalary = 0;

    printf("Enter number of employees: ");
    scanf("%d", &n);

    struct Employee emp[n];

        for (i = 0; i < n; i++) {
        printf("\nEnter details of employee %d\n", i + 1);

        printf("Employee Number: ");
        scanf("%d", &emp[i].empNo);

        printf("Employee Name: ");
        scanf(" %[^\n]", emp[i].name);  

        printf("Salary: ");
        scanf("%f", &emp[i].salary);

            if (emp[i].salary > maxSalary) {
            maxSalary = emp[i].salary;
        }
    }

        printf("\nEmployee(s) with Highest Salary (%.2f):\n", maxSalary);
    for (i = 0; i < n; i++) {
        if (emp[i].salary == maxSalary) {
            printf("\nEmployee Number: %d", emp[i].empNo);
            printf("\nEmployee Name  : %s", emp[i].name);
            printf("\nSalary         : %.2f\n", emp[i].salary);
        }
    }

    return 0;
}

```
# Output:

<img width="1352" height="725" alt="new4 3" src="https://github.com/user-attachments/assets/fce49e08-f35d-4907-ac42-210c8f6bf2d6" />


# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:29
  Create the C program to calculate the present age of a person by passing structure as a reference.
# Date : 
# Aim:
  To create a C program that uses a structure to store the current date and birth date, and to calculate the person’s present age in years, months, and days by passing the structure as a reference.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure named `date` with members to store:  
  - Current date (`c_date`, `c_month`, `c_year`)  
  - Birth date (`b_date`, `b_month`, `b_year`)  
  - Calculated age (`cal_date`, `cal_month`, `cal_year`)
### Step 4:
  Initialize a structure variable with the current date and birth date values.
### Step 5:
  Pass the structure variable to a function `findAge()` by reference.
### Step 6:
  Inside `findAge()`:  
  - a. Declare an integer array `month[]` to store the number of days in each month.  
  - b. If the birth date is greater than the current date:  
     - Add the number of days of the previous month to the current date.  
     - Decrease the current month by 1.  
  - c. If the birth month is greater than the current month:  
     - Decrease the current year by 1.  
     - Add 12 to the current month.  
  - d. Calculate the age in days, months, and years by subtracting the corresponding birth values from the current values.
### Step 7:
  Return the structure pointer containing the calculated age.
### Step 8:
  Display the calculated age (years, months, and days) in the `main` function.
### Step 9:
  Stop
# Program:
```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

void calculateAge(struct Date *birth, struct Date *current) {
    int d, m, y;

   
    if (birth->day > current->day) {
        current->day += 30;
        current->month -= 1;
    }

    d = current->day - birth->day;

        if (birth->month > current->month) {
        current->month += 12;
        current->year -= 1;
    }

    m = current->month - birth->month;
    y = current->year - birth->year;

    printf("\nAge is: %d Years, %d Months, %d Days\n", y, m, d);
}

int main() {
    struct Date birth, current;

    printf("Enter Birth Date (DD MM YYYY): ");
    scanf("%d %d %d", &birth.day, &birth.month, &birth.year);

    printf("Enter Current Date (DD MM YYYY): ");
    scanf("%d %d %d", &current.day, &current.month, &current.year);

    calculateAge(&birth, &current);

    return 0;
}

```
# Output:

<img width="1474" height="730" alt="new4 4" src="https://github.com/user-attachments/assets/5a072103-652b-4408-b84a-1889c48ee984" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:30
  Build a C program to demonstrate the use of a pointer to a union. Store an integer value in a union, access it using a union pointer, and display it as both an integer and a character.
# Date : 
# Aim:
  To build a program in C that uses a pointer to a union to store an integer value and display it in both integer and character format.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a union `abc` with the following members:  
  - `int a`  
  - `char b`
### Step 4:
  Declare a union variable `var` of type `abc`.
### Step 5:
  Declare a pointer `ptr` of type `union abc*`.
### Step 6:
  Assign the address of `var` to `ptr`.
### Step 7:
  Store an integer value (e.g., 90) in `var.a`.
### Step 8:
  Access and print the value of `a` using the pointer `ptr` in integer format.
### Step 9:
  Access and print the same value using the pointer `ptr` in character format.
### Step 10:
  Stop
# Program:
```c
#include <stdio.h>


union Data {
    int i;
    char c;
};

int main() {
    union Data d;
    union Data *ptr;

    
    d.i = 65;

    
    ptr = &d;

        printf("Integer value: %d\n", ptr->i);
    printf("Character value: %c\n", ptr->c);

    return 0;
}

```
# Output:

<img width="1437" height="730" alt="new4 5" src="https://github.com/user-attachments/assets/bc7e04d3-aa9d-495a-aa9e-45b010a84c8d" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


