# C_Programming_Group_D_Assignment_2_ID-20251SEN081

# NAMES: MUNNYENGABE ISHIMWE Kelly leondry
# ID: 20251SEN081

# Codes and Explanation for Each Question



# QUESTION 1

[Screenshoot_QUESTION 1](SCREENSHOOTS/Q1.png)


CODES
    
    
    #include <stdio.h>

int main(){
	
	
	int Marks;
	int Family_income;
	int Disability_status;
	
	
	printf("Enter student Marks(0-100%%) ");
	scanf("%d", &Marks);
		
	printf("Enter Family Income(Rwf) ");
	scanf("%d", &Family_income);
	
	printf("Enter Disability status(1 FOR YES or 0 FOR NO) ");
	scanf("%d", &Disability_status);
		
		if (Marks < 0 || Marks > 100 || Family_income < 0 || (Disability_status != 0 && Disability_status != 1)) {
			printf("Invalid input" );
		}	
		
		else if (Disability_status == 1){
	
			printf("========= RESULTS =========\n ");
			printf("Qualified for scholarship ");
		}
		
		else  if (Marks >= 80 && Family_income <= 300000){
			
			printf("========= RESULTS =========\n ");
			printf("Qualified for scholarship ");	
		}
		else {
			
			printf("=========== RESULTS ===========\n ");
			printf("Not Qualified for scholarship ");
			
		}
	
return 0;	
}

# EXplanation of how program works

The program asks the user to enter the student's marks, family income, and disability status. It checks whether the entered values are valid, ensuring that marks are between 0 and 100, family income is not negative, and disability status is either 1 for Yes or 0 for No. If any input is invalid, the program displays "Invalid input." Otherwise, the student qualifies for a scholarship if they have a disability, or if they score at least 80 marks and their family income is not more than 300,000 RWF. If neither condition is satisfied, the program displays "Not Qualified for scholarship." Finally, it displays the scholarship results based on the entered information.




# QUESTION 2

[Screenshoot_QUESTION_2](SCREENSHOOTS/Q2.png)

CODES

      #include <stdio.h>

int main() {
    int choice;
    float balance = 50000, amount;

    while (1) {
        printf("\n--- ATM MENU ---\n");
        printf("1. Check Balance\n");
        printf("2. Deposit\n");
        printf("3. Withdraw\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Current balance: %.2f RWF\n", balance);
                break;

            case 2:
                printf("Enter deposit amount: ");
                scanf("%f", &amount);

                if (amount <= 0) {
                    printf("Invalid deposit amount.\n");
                } else {
                    balance += amount;
                    printf("Updated balance: %.2f RWF\n", balance);
                }
                break;

            case 3:
                printf("Enter withdrawal amount: ");
                scanf("%f", &amount);

                if (amount <= 0) {
                    printf("Invalid withdrawal amount.\n");
                } else if (amount > balance) {
                    printf("Insufficient funds.\n");
                } else {
                    balance -= amount;
                    printf("Updated balance: %.2f RWF\n", balance);
                }
                break;

            case 4:
                printf("Exit\n");
                return 0;

            default:
                printf("Invalid option.\n");
                break;
        }
    }

    return 0;
}

# Explanation of how program works
The program starts with an initial balance of 50,000 RWF and displays a menu with four options: Check Balance, Deposit, Withdraw, and Exit. A while loop keeps the menu running until the user chooses Exit. A switch statement identifies the selected option and performs the corresponding action. If the user checks the balance, the current amount is displayed. For deposits and withdrawals, the program validates the amount before updating the balance. It also displays error messages for invalid amounts or insufficient funds. If the user selects Exit, the program terminates; otherwise, an invalid menu choice displays an error message and returns to the menu.


# QUESTION 3
[Screenshoot_QUESTION_3]()

CODES

    #include <stdio.h>

int main() {
    int pin, attempts = 0;

    while (attempts < 3) {
        printf("Enter your PIN: ");
        scanf("%d", &pin);

        if (pin == 1234) {
            printf("Access Granted\n");
            return 0;
        }

        attempts++;

        if (attempts == 3) {
            printf("Account Locked\n");
        } else {
            printf("Wrong PIN. %d attempt(s) remaining.\n",
                   3 - attempts);
        }
    }

    return 0;
}

# Explanation of how program works

The program asks the user to enter a PIN, which must be 1234. A counter records the number of incorrect attempts, while a while loop allows a maximum of three attempts. If the correct PIN is entered, the program displays "Access Granted" and stops immediately. If the PIN is incorrect, the counter increases, and the program displays the remaining attempts after the first or second mistake. If the third attempt is incorrect, the program displays "Account Locked" and terminates without displaying the "Wrong PIN" message.


# QUESTION 4

[Screenshoot_QUESTION_4](SCREENSHOOTS/Q4.png)
CODES

      #include <stdio.h>

int main() {
    int code, hour;

    printf("Enter traffic light code (1-3): ");
    scanf("%d", &code);

    printf("Enter hour of the day (0-23): ");
    scanf("%d", &hour);

    if (code < 1 || code > 3 || hour < 0 || hour > 23) {
        printf("Invalid input\n");
        return 0;
    }

    if (hour >= 0 && hour <= 4) {
        printf("Blinking Yellow\n");
    } else {
        switch (code) {
            case 1:
                printf("Stop\n");
                break;

            case 2:
                printf("Get Ready\n");
                break;

            case 3:
                printf("GO\n");
                break;

            default:
                printf("Invalid input\n");
                break;
        }
    }

    return 0;
}

# Explanation of how program works
The program asks the user to enter a traffic light code and the hour of the day. It checks whether the code is between 1 and 3 and the hour is between 0 and 23. If either input is invalid, the program displays "Invalid input" and terminates. An if-else statement checks whether the time is between midnight and 4 AM, inclusive. During these hours, the program displays "Blinking Yellow" regardless of the traffic light code. At other times, a switch statement displays "Stop" for code 1, "Get Ready" for code 2, or "GO" for code 3.

# QUESTION 5
[Screenshoot_QUESTION_5](SCREENSHOOTS/Q5.png)

CODES

      #include <stdio.h>

int main() {
    int student, course;
    float mark, total, average, highest, lowest;
    char grade[3][20];
    char letter;

    for (student = 1; student <= 5; student++) {
        total = 0;
        highest = 0;
        lowest = 100;

        printf("\n--- Student %d ---\n", student);

        for (course = 1; course <= 5; course++) {
            do {
                printf("Enter mark for course %d (0-100): ",
                       course);
                scanf("%f", &mark);

                if (mark < 0 || mark > 100) {
                    printf("Invalid mark. Please enter again.\n");
                }
            } while (mark < 0 || mark > 100);

            total += mark;

            if (course == 1) {
                highest = mark;
                lowest = mark;
            } else {
                if (mark > highest) {
                    highest = mark;
                }

                if (mark < lowest) {
                    lowest = mark;
                }
            }
        }

        average = total / 5;

        if (average >= 90) {
            letter = 'A';
        } else if (average >= 80) {
            letter = 'B';
        } else if (average >= 70) {
            letter = 'C';
        } else if (average >= 60) {
            letter = 'D';
        } else if (average >= 50) {
            letter = 'E';
        } else {
            letter = 'F';
        }

        printf("\nTotal marks: %.2f\n", total);
        printf("Average mark: %.2f\n", average);
        printf("Highest mark: %.2f\n", highest);
        printf("Lowest mark: %.2f\n", lowest);
        printf("Grade: %c\n", letter);

        switch (letter) {
            case 'A':
                printf("Interpretation: Outstanding\n");
                break;
            case 'B':
                printf("Interpretation: Very Good\n");
                break;
            case 'C':
                printf("Interpretation: Good\n");
                break;
            case 'D':
                printf("Interpretation: Satisfactory\n");
                break;
            case 'E':
                printf("Interpretation: Needs Improvement\n");
                break;
            case 'F':
                printf("Interpretation: Fail\n");
                break;
        }
    }

    return 0;
}

# Explanation of how program works
The program processes five students, each taking five courses, using nested for loops. The outer loop handles each student, while the inner loop collects marks for each course. Every mark must be between 0 and 100; invalid marks are rejected until a valid mark is entered. The program calculates the total and average marks and identifies the highest and lowest marks. It uses the average to assign a grade from A to F according to the given grading scale. A switch statement displays the interpretation of each grade, such as Outstanding, Very Good, Good, or Fail. Finally, the program displays each student's results before moving to the next student and terminates after processing all five students.




