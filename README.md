# Introduction-to-programming- # Week 1


## about_me.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    // Variable declarations
    string name;
    string course;
    string hobby;
    string reason;
    string expectation;
    string definition;

    // Welcome message
    cout << "========================================" << endl;
    cout << " WELCOME TO YOUR FIRST PROGRAM!" << endl;
    cout << "========================================" << endl;
    cout << endl;

    // Question 1: name
    cout << "1. What is your name? ";
    getline(cin, name);

    // Question 2: course
    cout << "2. What course are you doing? (BBIT/BCS): ";
    getline(cin, course);

    // Question 3: hobby
    cout << "3. What is your hobby? ";
    getline(cin, hobby);

    // Question 4: reason
    cout << "4. Why did you choose this course? ";
    getline(cin, reason);

    // Question 5: expectation
    cout << "5. What do you expect to learn in programming? ";
    getline(cin, expectation);

    // Question 6: definition
    cout << "6. In your own words, what is programming? ";
    getline(cin, definition);

    // Display summary
    cout << endl;
    cout << "========================================" << endl;
    cout << " YOUR PROFILE SUMMARY" << endl;
    cout << "========================================" << endl;
    cout << endl;
    cout << "Name: " << name << endl;
    cout << "Course: " << course << endl;
    cout << "Hobby: " << hobby << endl;
    cout << "Reason: " << reason << endl;
    cout << "Expectation: " << expectation << endl;
    cout << "Programming is: " << definition << endl;
    cout << endl;
    cout << "========================================" << endl;
    cout << " Thank you for completing this!" << endl;
    cout << "========================================" << endl;

    return 0;
}

//g++ about_me.cpp -o about_me
//./about_me
```


## about_me.c

```c
#include <stdio.h>
#include <string.h>

#define MAX_LEN 100

int main() {
    // Variable declarations
    char name[MAX_LEN];   // Stores the user's name
    char course[MAX_LEN];   // Stores the course (BBIT or BCS)
    char hobby[MAX_LEN];   // Stores the hobby
    char reason[MAX_LEN];   // Stores why they chose the course
    char expectation[MAX_LEN];   // Stores what they expect to learn
    char definition[MAX_LEN];   // Stores their definition of programming

    // Welcome message
    printf("========================================\n");
    printf(" WELCOME TO YOUR FIRST C PROGRAM!\n");
    printf("========================================\n\n");

    // Question 1: name
    printf("1. What is your name? ");
    fgets(name, MAX_LEN, stdin);
    name[strcspn(name, "\n")] = '\0';

    // Question 2: course
    printf("2. What course are you doing? (BBIT/BCS): ");
    fgets(course, MAX_LEN, stdin);
    course[strcspn(course, "\n")] = '\0';

    // Question 3: hobby
    printf("3. What is your hobby? ");
    fgets(hobby, MAX_LEN, stdin);
    hobby[strcspn(hobby, "\n")] = '\0';

    // Question 4: reason for choosing course
    printf("4. Why did you choose this course? ");
    fgets(reason, MAX_LEN, stdin);
    reason[strcspn(reason, "\n")] = '\0';

    // Question 5: expectations
    printf("5. What do you expect to learn in programming? ");
    fgets(expectation, MAX_LEN, stdin);
    expectation[strcspn(expectation, "\n")] = '\0';

    // Question 6: definition of programming
    printf("6. In your own words, what is programming? ");
    fgets(definition, MAX_LEN, stdin);
    definition[strcspn(definition, "\n")] = '\0';

    // Display summary
    printf("\n========================================\n");
    printf(" YOUR PROFILE SUMMARY\n");
    printf("========================================\n\n");
    printf("Name: %s\n", name);
    printf("Course: %s\n", course);
    printf("Hobby: %s\n", hobby);
    printf("Reason: %s\n", reason);
    printf("Expectation: %s\n", expectation);
    printf("Programming is: %s\n", definition);
    printf("\n========================================\n");
    printf(" Thank you for completing this!\n");
    printf("========================================\n");

    return 0;
}

//gcc about_me.c -o about_me

//./about_me
```
# Week 2


## score_calculator.cpp

```cpp
#include <iostream>
#include <string>
#include <iomanip>

using namespace std;

int main() {
    // Variable declarations
    string studentName;   // Text - stores the student's name
    string course;   // Text - stores the course (BBIT/BCS)
    int score1, score2, score3;   // Whole numbers - test scores
    int totalScore;   // Whole number - sum of scores
    double average;   // Decimal number - average score
    double percentage;   // Decimal number - percentage

    // Constant declaration
    const int MAX_SCORE = 100;   // Maximum possible score per test

    // Welcome banner
    cout << "========================================" << endl;
    cout << " STUDENT SCORE CALCULATOR" << endl;
    cout << "========================================" << endl;
    cout << endl;

    // Input: student name
    cout << "Enter student name: ";
    getline(cin, studentName);

    // Input: course
    cout << "Enter course (BBIT/BCS): ";
    getline(cin, course);

    // Input: test scores
    cout << "Enter score for Test 1: ";
    cin >> score1;
    cout << "Enter score for Test 2: ";
    cin >> score2;
    cout << "Enter score for Test 3: ";
    cin >> score3;

    // Calculations
    totalScore = score1 + score2 + score3;   // Add scores
    average = totalScore / 3.0;   // Decimal division
    percentage = (totalScore / 300.0) * 100;   // Percentage

    // Output: report card
    cout << endl;
    cout << "========================================" << endl;
    cout << " REPORT CARD" << endl;
    cout << "========================================" << endl;
    cout << endl;
    cout << "Student: " << studentName << endl;
    cout << "Course: " << course << endl;
    cout << endl;
    cout << "Test 1: " << score1 << "/" << MAX_SCORE << endl;
    cout << "Test 2: " << score2 << "/" << MAX_SCORE << endl;
    cout << "Test 3: " << score3 << "/" << MAX_SCORE << endl;
    cout << endl;
    cout << "Total: " << totalScore << "/300" << endl;
    cout << "Average: " << fixed << setprecision(2) << average << endl;
    cout << "Percentage: " << fixed << setprecision(2) << percentage << "%" << endl;
    cout << endl;
    if (percentage >= 50) {
        cout << "Result: PASS" << endl;
    } else {
        cout << "Result: FAIL" << endl;
    }
    cout << "========================================" << endl;

    return 0;
}

//g++ score_calculator.cpp -o score_calculator
//./score_calculator
```


## score_calculator.c

```c
#include <stdio.h>
#include <string.h>

#define MAX_LEN 100
#define MAX_SCORE 100

int main() {
    // Variable declarations
    char studentName[MAX_LEN];   // Character array for name
    char course[MAX_LEN];   // Character array for course
    int score1, score2, score3;   // Whole numbers - test scores
    int totalScore;   // Whole number - sum of scores
    double average;   // Decimal number - average
    double percentage;   // Decimal number - percentage

    // Welcome banner
    printf("========================================\n");
    printf(" STUDENT SCORE CALCULATOR\n");
    printf("========================================\n\n");

    // Input: student name
    printf("Enter student name: ");
    fgets(studentName, MAX_LEN, stdin);
    studentName[strcspn(studentName, "\n")] = '\0';

    // Input: course
    printf("Enter course (BBIT/BCS): ");
    fgets(course, MAX_LEN, stdin);
    course[strcspn(course, "\n")] = '\0';

    // Input: test scores
    printf("Enter score for Test 1: ");
    scanf("%d", &score1);
    printf("Enter score for Test 2: ");
    scanf("%d", &score2);
    printf("Enter score for Test 3: ");
    scanf("%d", &score3);

    // Calculations
    totalScore = score1 + score2 + score3;   // Add scores
    average = totalScore / 3.0;   // Decimal division
    percentage = (totalScore / 300.0) * 100;   // Percentage

    // Output: report card
    printf("\n");
    printf("========================================\n");
    printf(" REPORT CARD\n");
    printf("========================================\n\n");
    printf("Student: %s\n", studentName);
    printf("Course: %s\n", course);
    printf("\n");
    printf("Test 1: %d/%d\n", score1, MAX_SCORE);
    printf("Test 2: %d/%d\n", score2, MAX_SCORE);
    printf("Test 3: %d/%d\n", score3, MAX_SCORE);
    printf("\n");
    printf("Total: %d/300\n", totalScore);
    printf("Average: %.2f\n", average);
    printf("Percentage: %.2f%%\n", percentage);
    printf("\n");
    if (percentage >= 50) {
        printf("Result: PASS\n");
    } else {
        printf("Result: FAIL\n");
    }
    printf("========================================\n");

    return 0;
}

//gcc score_calculator.c -o score_calculator
//./score_calculator
```


## favourite_colour.c

```c
#include <stdio.h>
#include <string.h>

#define MAX_LEN 50# Week 3


## nested.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int a, b, c;
    cout << "Enter three numbers: ";
    cin >> a >> b >> c;
    if (a > b) {
        if (b > c) {
            cout << "Path 1: a > b > c" << endl;
        } else {
            if (a > c) {
                cout << "Path 2: a > c > b" << endl;
            } else {
                cout << "Path 3: c > a > b" << endl;
            }
        }
    } else {
        if (a > c) {
            cout << "Path 4: b > a > c" << endl;
        } else {
            if (b > c) {
                cout << "Path 5: b > c > a" << endl;
            } else {
                cout << "Path 6: c > b > a" << endl;
            }
        }
    }

    return 0;
}

//g++ nested.cpp -o nested
//./nested
```


## menu_ifelse.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int choice;
    cout << "Menu:\n1. Start\n2. Load\n3. Settings\n4. Exit\nChoice: ";
    cin >> choice;
    if (choice == 1) {
        cout << "Starting game..." << endl;
    } else if (choice == 2) {
        cout << "Loading game..." << endl;
    } else if (choice == 3) {
        cout << "Opening settings..." << endl;
    } else if (choice == 4) {
        cout << "Exiting..." << endl;
    } else {
        cout << "Invalid choice!" << endl;
    }

    return 0;
}

//g++ menu_ifelse.cpp -o menu_ifelse
//./menu_ifelse
```


## menu_switch.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int choice;
    cout << "Menu:\n1. Start\n2. Load\n3. Settings\n4. Exit\nChoice: ";
    cin >> choice;
    switch (choice) {
        case 1:
            cout << "Starting game..." << endl;
            break;
        case 2:
            cout << "Loading game..." << endl;
            break;
        case 3:
            cout << "Opening settings..." << endl;
            break;
        case 4:
            cout << "Exiting..." << endl;
            break;
        default:
            cout << "Invalid choice!" << endl;
    }

    return 0;
}

//g++ menu_switch.cpp -o menu_switch
//./menu_switch
```


## grade_calculator.cpp

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    double score;
    char grade;
    char modifier = ' ';   // space means no modifier
    cout << "===== GRADE CALCULATOR =====" << endl;
    cout << "Enter percentage score (0-100): ";
    cin >> score;
    if (score < 0 || score > 100) {
        cout << "Invalid score! Must be between 0 and 100." << endl;

        return 1;
    }
    if (score >= 90) {
        grade = 'A';
    } else if (score >= 80) {
        grade = 'B';
    } else if (score >= 70) {
        grade = 'C';
    } else if (score >= 60) {
        grade = 'D';
    } else {
        grade = 'F';
    }
    if (grade != 'F') {
        int lastDigit = (int)score % 10;
        if (grade == 'A') {
            if (score >= 97) modifier = '+';
            else if (score < 93) modifier = '-';
        } else if (grade == 'B' || grade == 'C') {
            if (lastDigit >= 7) modifier = '+';
            else if (lastDigit <= 3) modifier = '-';
        } else if (grade == 'D') {
            if (lastDigit >= 7) modifier = '+';
            else if (lastDigit <= 3) modifier = '-';
        }
    }
    cout << "\nScore: " << fixed << setprecision(1) << score << "%" << endl;
    cout << "Grade: " << grade;
    if (modifier != ' ') cout << modifier;
    cout << endl;

    return 0;
}

//g++ grade_calculator.cpp -o grade_calculator
//./grade_calculator
```


## pass_fail.c

```c
#include <stdio.h>

int main() {
    int score;
    printf("Enter score: ");
    scanf("%d", &score);
    if (score >= 60) {
        printf("You passed!\n");
    } else {
        printf("You failed. Try again!\n");
    }

    return 0;
}

//gcc pass_fail.c -o pass_fail
//./pass_fail
```


## grade_elseif.c

```c
#include <stdio.h>

int main() {
    int score;
    char grade;
    printf("Enter score (0-100): ");
    scanf("%d", &score);
    if (score >= 90) {
        grade = 'A';
    } else if (score >= 80) {
        grade = 'B';
    } else if (score >= 70) {
        grade = 'C';
    } else if (score >= 60) {
        grade = 'D';
    } else {
        grade = 'F';
    }
    printf("Grade: %c\n", grade);

    return 0;
}

//gcc grade_elseif.c -o grade_elseif
//./grade_elseif
```


## event_admission.c

```c
#include <stdio.h>

int main() {
    int age;
    int hasTicket;   // We use 1 for yes, 0 for no
    printf("Enter age: ");
    scanf("%d", &age);
    printf("Has ticket? (1 for yes, 0 for no): ");
    scanf("%d", &hasTicket);
    if (age >= 18) {
        printf("Adult verified.\n");
        if (hasTicket) {
            printf("Welcome to the event!\n");
        } else {
            printf("Please purchase a ticket at the door.\n");
        }
    } else {
        printf("Minor detected.\n");
        if (age >= 12) {
            printf("Teenager - needs guardian signature.\n");
        } else {
            printf("Child - must be accompanied by adult.\n");
        }
    }

    return 0;
}

//gcc event_admission.c -o event_admission
//./event_admission
```


## movie_eligibility.c

```c
#include <stdio.h>

int main() {
    int age;
    int hasParentalConsent;   // 1 = yes, 0 = no
    int isWeekend;   // 1 = yes, 0 = no
    printf("Enter age: ");
    scanf("%d", &age);
    printf("Has parental consent? (1 for yes, 0 for no): ");
    scanf("%d", &hasParentalConsent);
    printf("Is it weekend? (1 for yes, 0 for no): ");
    scanf("%d", &isWeekend);
    int canWatchMovie = (age >= 18) ||
                            (age >= 13 && hasParentalConsent) ||
                            (isWeekend && age >= 10);
    if (canWatchMovie) {
        printf("You can watch the movie!\n");
    } else {
        printf("Sorry, you cannot watch this movie.\n");
    }
    int eligibleForDiscount = (age >= 65) ||
                                (age <= 12) ||
                                (isWeekend && age <= 18);
    if (eligibleForDiscount) {
        printf("You qualify for a discount!\n");
    }

    return 0;
}

//gcc movie_eligibility.c -o movie_eligibility
//./movie_eligibility
```


## day_of_week.c

```c
#include <stdio.h>

int main() {
    int day;
    printf("Enter day number (1-7): ");
    scanf("%d", &day);
    switch (day) {
        case 1:
            printf("Monday\n");
            break;   // break exits the switch
        case 2:
            printf("Tuesday\n");
            break;
        case 3:
            printf("Wednesday\n");
            break;
        case 4:
            printf("Thursday\n");
            break;
        case 5:
            printf("Friday\n");
            break;
        case 6:
            printf("Saturday\n");
            break;
        case 7:
            printf("Sunday\n");
            break;
        default:
            printf("Invalid day number!\n");
            break;
    }

    return 0;
}

//gcc day_of_week.c -o day_of_week
//./day_of_week
```


## grade_switch.c

```c
#include <stdio.h>

int main() {
    char grade;
    printf("Enter your grade (A, B, C, D, F): ");
    scanf(" %c", &grade);
    switch (grade) {
        case 'A':
        case 'a':
            printf("Excellent! 90-100%%\n");   // %% prints a literal %
            break;
        case 'B':
        case 'b':
            printf("Good! 80-89%%\n");
            break;
        case 'C':
        case 'c':
            printf("Satisfactory! 70-79%%\n");
            break;
        case 'D':
        case 'd':
            printf("Passing! 60-69%%\n");
            break;
        case 'F':
        case 'f':
            printf("Failing. Please retake.\n");
            break;
        default:
            printf("Invalid grade entered!\n");
            break;
    }

    return 0;
}

//gcc grade_switch.c -o grade_switch
//./grade_switch
```


## game_menu.cpp

```cpp
#include <stdio.h>

int main() {
    int choice;
    printf("===== MAIN MENU =====\n");
    printf("1. Start Game\n");
    printf("2. Load Game\n");
    printf("3. Settings\n");
    printf("4. Credits\n");
    printf("5. Exit\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);
    switch (choice) {
        case 1:
            printf("Starting new game...\n");
        case 2:
            printf("Loading game assets...\n");
            printf("Game ready!\n");
            break;
        case 3:
            printf("Opening settings...\n");
            break;
        case 4:
            printf("Game developed by CS Students\n");
            break;
        case 5:
            printf("Goodbye!\n");
            break;
        default:
            printf("Invalid choice. Please try again.\n");
            break;
    }

    return 0;
}

//g++ game_menu.cpp -o game_menu
//./game_menu
```


## full_grading.c

```c
#include <stdio.h>

int main() {
    char studentName[50];   // Character array for name
    double score;
    char grade;
    printf("Enter student name: ");
    fgets(studentName, 50, stdin);
    studentName[strcspn(studentName, "\n")] = '\0';
    printf("Enter percentage score (0-100): ");
    scanf("%lf", &score);
    if (score < 0 || score > 100) {
        printf("ERROR: Score must be between 0 and 100!\n");

        return 1;
    }
    if (score >= 90) {
        grade = 'A';
    } else if (score >= 80) {
        grade = 'B';
    } else if (score >= 70) {
        grade = 'C';
    } else if (score >= 60) {
        grade = 'D';
    } else {
        grade = 'F';
    }
    printf("\n===== GRADE REPORT =====\n");
    printf("Student: %s\n", studentName);
    printf("Score: %.2f%%\n", score);
    printf("Letter Grade: %c\n", grade);
    printf("\n===== RECOMMENDATIONS =====\n");
    switch (grade) {
        case 'A':
            printf("Consider becoming a peer tutor\n");
            printf("Explore advanced topics\n");
            break;
        case 'B':
            printf("Review topics where you lost points\n");
            printf("Practice more problems\n");
            break;
        case 'C':
            printf("Attend office hours regularly\n");
            printf("Form a study group\n");
            break;
        case 'D':
        case 'F':
            printf("Mandatory tutoring sessions\n");
            printf("Meet with academic advisor\n");
            break;
        default:
            printf("Continue your good work\n");
            break;
    }

    return 0;
}

//gcc full_grading.c -o full_grading
//./full_grading
```


## ride_eligibility.c

```c
#include <stdio.h>

int main() {
    int height;
    int age;
    int hasAdult;   // 1 = yes, 0 = no
    int medicalClearance;   // 1 = yes, 0 = no
    int hasVipPass;   // 1 = yes, 0 = no
    printf("Enter height (in inches): ");
    scanf("%d", &height);
    printf("Enter age: ");
    scanf("%d", &age);
    printf("Has adult? (1/0): ");
    scanf("%d", &hasAdult);
    printf("Has medical clearance? (1/0): ");
    scanf("%d", &medicalClearance);
    printf("Has VIP pass? (1/0): ");
    scanf("%d", &hasVipPass);
    int canRide = (height >= 48) &&
                    (age >= 12 || hasAdult) &&
                    (age <= 65 || medicalClearance) ||
                    hasVipPass;
    if (canRide) {
        printf("You can ride!\n");
    } else {
        printf("Sorry, you cannot ride.\n");
    }

    return 0;
}

//gcc ride_eligibility.c -o ride_eligibility
//./ride_eligibility
```


## path_analysis.c

```c
#include <stdio.h>

int main() {
    int x = 10, y = 5;
    if (x > 0) {
        if (y > 0) {
            printf("Path A: Both positive\n");
        } else {
            printf("Path B: x positive, y non-positive\n");
        }
    } else {
        if (y > 0) {
            printf("Path C: x non-positive, y positive\n");
        } else {
            printf("Path D: Both non-positive\n");
        }
    }

    return 0;
}

//gcc path_analysis.c -o path_analysis
//./path_analysis
```

int main() {
    char colour[MAX_LEN];
    printf("Enter your favourite colour: ");
    fgets(colour, MAX_LEN, stdin);
    colour[strcspn(colour, "\n")] = '\0';
    printf("Your favourite colour is %s.\n", colour);
