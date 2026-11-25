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
                                         # Week 3


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
# Week 4


## sum_numbers.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int n;
    int sum = 0;
    cout << "Enter a positive number (N): ";
    cin >> n;
    for (int i = 1; i <= n; i++) {
        sum += i;
    }
    cout << "The sum of numbers from 1 to " << n << " is: " << sum << endl;

    return 0;
}

//g++ sum_numbers.cpp -o sum_numbers
//./sum_numbers
```


## break_continue.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    cout << "Number filter: Skip multiples of 3, stop at 15" << endl;
    for (int i = 1; i <= 20; i++) {
        if (i == 15) {
            cout << "Breaking at " << i << "!" << endl;
            break;
        }
        if (i % 3 == 0) {
            continue;
        }
        cout << i << " ";
    }   // End of for loop
    cout << endl;

    return 0;
}

//g++ break_continue.cpp -o break_continue
//./break_continue
```


## validation_while.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int number;
    cout << "Enter a positive number: ";
    cin >> number;
    while (number <= 0) {
        cout << "Invalid! Please enter a positive number: ";
        cin >> number;
    }
    cout << "You entered: " << number << endl;

    return 0;
}

//g++ validation_while.cpp -o validation_while
//./validation_while
```


## validation_dowhile.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int number = 0;
    do {
        cout << "Enter a positive number: ";
        cin >> number;
        if (number <= 0) {
            cout << "Invalid! ";
        }
    } while (number <= 0);   // Condition checked AFTER the body runs
    cout << "You entered: " << number << endl;

    return 0;
}

//g++ validation_dowhile.cpp -o validation_dowhile
//./validation_dowhile
```


## multiplication_table.cpp

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    cout << "========================================" << endl;
    cout << " MULTIPLICATION TABLE (1 to 10)" << endl;
    cout << "========================================" << endl;
    cout << endl;
    for (int i = 1; i <= 10; i++) {
        for (int j = 1; j <= 10; j++) {
            cout << setw(5) << i * j;
        }
        cout << endl;
    }   // End of outer loop - all rows are printed
    cout << "========================================" << endl;

    return 0;
}

//g++ multiplication_table.cpp -o multiplication_table
//./multiplication_table
```


## sum_numbers.c

```c
#include <stdio.h>

int main() {
    int n;
    int sum = 0;
    printf("Enter a positive number (N): ");
    scanf("%d", &n);
    for (int i = 1; i <= n; i++) {
        sum += i;
    }
    printf("The sum of numbers from 1 to %d is: %d\n", n, sum);

    return 0;
}

//gcc sum_numbers.c -o sum_numbers
//./sum_numbers
```


## break_continue.c

```c
#include <stdio.h>

int main() {
    printf("Number filter: Skip multiples of 3, stop at 15\n");
    for (int i = 1; i <= 20; i++) {
        if (i == 15) {
            printf("Breaking at %d!\n", i);
            break;
        }
        if (i % 3 == 0) {
            continue;
        }
        printf("%d ", i);
    }   // End of for loop
    printf("\n");

    return 0;
}

//gcc break_continue.c -o break_continue
//./break_continue
```


## validation_while.c

```c
#include <stdio.h>

int main() {
    int number;
    printf("Enter a positive number: ");
    scanf("%d", &number);
    while (number <= 0) {
        printf("Invalid! Please enter a positive number: ");
        scanf("%d", &number);
    }
    printf("You entered: %d\n", number);

    return 0;
}

//gcc validation_while.c -o validation_while
//./validation_while
```


## validation_dowhile.c

```c
#include <stdio.h>

int main() {
    int number = 0;
    do {
        printf("Enter a positive number: ");
        scanf("%d", &number);
        if (number <= 0) {
            printf("Invalid! ");
        }
    } while (number <= 0);   // Condition checked AFTER the body runs
    printf("You entered: %d\n", number);

    return 0;
}

//gcc validation_dowhile.c -o validation_dowhile
//./validation_dowhile
```


## multiplication_table.c

```c
#include <stdio.h>

int main() {
    printf("========================================\n");
    printf(" MULTIPLICATION TABLE (1 to 10)\n");
    printf("========================================\n\n");
    for (int i = 1; i <= 10; i++) {
        for (int j = 1; j <= 10; j++) {
            printf("%5d", i * j);
        }
        printf("\n");
    }   // End of outer loop - all rows are printed
    printf("========================================\n");

    return 0;
}

//gcc multiplication_table.c -o multiplication_table
//./multiplication_table
```
# Week 5


## swap_by_value.cpp

```cpp
#include <iostream>

using namespace std;

void swapByValue(int a, int b) {
    cout << " Inside function - Before swap: a = " << a << ", b = " << b << endl;
    int temp = a;
    a = b;
    b = temp;
    cout << " Inside function - After swap: a = " << a << ", b = " << b << endl;
}

int main() {
    int x = 10;
    int y = 20;
    cout << "Before calling swapByValue:" << endl;
    cout << " x = " << x << ", y = " << y << endl;
    swapByValue(x, y);
    cout << "After calling swapByValue:" << endl;
    cout << " x = " << x << ", y = " << y << endl;
    cout << "\nExplanation: The function received COPIES of x and y." << endl;
    cout << "Changes made inside the function do not affect the originals." << endl;

    return 0;
}

//g++ swap_by_value.cpp -o swap_by_value
//./swap_by_value
```


## variable_scope.cpp

```cpp
#include <iostream>

using namespace std;

// Global variable
int globalCounter = 100;
void displayGlobal() {
    cout << "Inside displayGlobal: globalCounter = " << globalCounter << endl;

    // cout << localCounter; // ERROR: localCounter is not declared here
}

void modifyGlobal() {
    globalCounter = 500;
    cout << "Inside modifyGlobal: globalCounter changed to " << globalCounter << endl;
}

void localDemo() {
    int globalCounter = 999;   // This SHADOWS the global variable
    cout << "Inside localDemo: globalCounter = " << globalCounter << endl;
}

int main() {
    int localCounter = 50;
    cout << "In main: globalCounter = " << globalCounter << endl;
    cout << "In main: localCounter = " << localCounter << endl;
    displayGlobal();
    modifyGlobal();
    localDemo();
    cout << "Back in main: globalCounter = " << globalCounter << endl;

    // cout << globalCounterLocal; // ERROR: not declared

    return 0;
}

//g++ variable_scope.cpp -o variable_scope
//./variable_scope
```


## recursion_factorial.cpp

```cpp
#include <iostream>

using namespace std;

int factorialRecursive(int n) {
    if (n <= 1) {
        return 1;
    }

    return n * factorialRecursive(n - 1);
}

int factorialTail(int n, int accumulator = 1) {
    if (n <= 1) {
        return accumulator;
    }

    return factorialTail(n - 1, n * accumulator);
}

int main() {
    int num;
    cout << "Enter a number to calculate factorial: ";
    cin >> num;
    if (num < 0) {
        cout << "Factorial is not defined for negative numbers." << endl;

        return 1;
    }
    cout << "\nUsing simple recursion:" << endl;
    cout << " " << num << "! = " << factorialRecursive(num) << endl;
    cout << "\nUsing tail recursion:" << endl;
    cout << " " << num << "! = " << factorialTail(num) << endl;
    cout << "\n--- Comparison ---" << endl;
    cout << "Simple recursion: Clear, matches mathematical definition." << endl;
    cout << "Tail recursion: More efficient for large n (compiler optimization)." << endl;

    return 0;
}

//g++ recursion_factorial.cpp -o recursion_factorial
//./recursion_factorial
```


## geometry_library.cpp

```cpp
#include <iostream>
#include <iomanip>   // For setprecision
#include <cmath>   // For pow()

using namespace std;

// Constant: pi
const double PI = 3.14159;
double areaOfCircle(double radius) {
    if (radius < 0) {
        cout << "Error: Radius cannot be negative." << endl;

        return 0.0;
    }

    return PI * radius * radius;
}

double areaOfRectangle(double length, double width) {
    if (length < 0 || width < 0) {
        cout << "Error: Length and width cannot be negative." << endl;

        return 0.0;
    }

    return length * width;
}

double areaOfTriangle(double base, double height) {
    if (base < 0 || height < 0) {
        cout << "Error: Base and height cannot be negative." << endl;

        return 0.0;
    }

    return 0.5 * base * height;
}

void displayMenu() {
    cout << "\n===== GEOMETRY CALCULATOR =====" << endl;
    cout << "1. Area of Circle" << endl;
    cout << "2. Area of Rectangle" << endl;
    cout << "3. Area of Triangle" << endl;
    cout << "4. Exit" << endl;
    cout << "Enter your choice: ";
}

int main() {
    int choice;
    double radius, length, width, base, height, area;
    do {
        displayMenu();
        cin >> choice;
        switch (choice) {
            case 1:
                cout << "Enter radius: ";
                cin >> radius;
                area = areaOfCircle(radius);
                cout << "Area of circle: " << fixed << setprecision(2) << area << endl;
                break;
            case 2:
                cout << "Enter length: ";
                cin >> length;
                cout << "Enter width: ";
                cin >> width;
                area = areaOfRectangle(length, width);
                cout << "Area of rectangle: " << fixed << setprecision(2) << area << endl;
                break;
            case 3:
                cout << "Enter base: ";
                cin >> base;
                cout << "Enter height: ";
                cin >> height;
                area = areaOfTriangle(base, height);
                cout << "Area of triangle: " << fixed << setprecision(2) << area << endl;
                break;
            case 4:
                cout << "Goodbye!" << endl;
                break;
            default:
                cout << "Invalid choice. Please try again." << endl;
        }
    } while (choice != 4);

    return 0;
}

//g++ geometry_library.cpp -o geometry_library
//./geometry_library
```


## swap_by_value.c

```c
#include <stdio.h>

void swapByValue(int a, int b) {
    printf(" Inside function - Before swap: a = %d, b = %d\n", a, b);
    int temp = a;
    a = b;
    b = temp;
    printf(" Inside function - After swap: a = %d, b = %d\n", a, b);
}

int main() {
    int x = 10;
    int y = 20;
    printf("Before calling swapByValue:\n");
    printf(" x = %d, y = %d\n", x, y);
    swapByValue(x, y);
    printf("After calling swapByValue:\n");
    printf(" x = %d, y = %d\n", x, y);
    printf("\nExplanation: The function received COPIES of x and y.\n");
    printf("Changes made inside the function do not affect the originals.\n");

    return 0;
}

//gcc swap_by_value.c -o swap_by_value
//./swap_by_value
```


## swap_by_pointer.c

```c
void swapByPointer(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 10, y = 20;
    swapByPointer(&x, &y);
    printf("x = %d, y = %d\n", x, y);

    return 0;
}

//gcc swap_by_pointer.c -o swap_by_pointer
//./swap_by_pointer
```


## variable_scope.c

```c
#include <stdio.h>

// Global variable
int globalCounter = 100;
void displayGlobal() {
    printf("Inside displayGlobal: globalCounter = %d\n", globalCounter);

    // printf("%d", localCounter); // ERROR: localCounter not declared here
}

void modifyGlobal() {
    globalCounter = 500;
    printf("Inside modifyGlobal: globalCounter changed to %d\n", globalCounter);
}

void localDemo() {
    int globalCounter = 999;   // This SHADOWS the global variable
    printf("Inside localDemo: globalCounter = %d\n", globalCounter);
}

int main() {
    int localCounter = 50;
    printf("In main: globalCounter = %d\n", globalCounter);
    printf("In main: localCounter = %d\n", localCounter);
    displayGlobal();
    modifyGlobal();
    localDemo();
    printf("Back in main: globalCounter = %d\n", globalCounter);

    // printf("%d", globalCounterLocal); // ERROR: not declared

    return 0;
}

//gcc variable_scope.c -o variable_scope
//./variable_scope
```


## recursion_factorial.c

```c
#include <stdio.h>

int factorialRecursive(int n) {
    if (n <= 1) {
        return 1;
    }

    return n * factorialRecursive(n - 1);
}

int factorialTailHelper(int n, int accumulator) {
    if (n <= 1) {
        return accumulator;
    }

    return factorialTailHelper(n - 1, n * accumulator);
}

int factorialTail(int n) {
    return factorialTailHelper(n, 1);
}

int main() {
    int num;
    printf("Enter a number to calculate factorial: ");
    scanf("%d", &num);
    if (num < 0) {
        printf("Factorial is not defined for negative numbers.\n");

        return 1;
    }
    printf("\nUsing simple recursion:\n");
    printf(" %d! = %d\n", num, factorialRecursive(num));
    printf("\nUsing tail recursion:\n");
    printf(" %d! = %d\n", num, factorialTail(num));
    printf("\n--- Comparison ---\n");
    printf("Simple recursion: Clear, matches mathematical definition.\n");
    printf("Tail recursion: More efficient for large n (compiler optimization).\n");

    return 0;
}

//gcc recursion_factorial.c -o recursion_factorial
//./recursion_factorial
```


## geometry_library.c

```c
#include <stdio.h>

// Constant: pi
#define PI 3.14159

double areaOfCircle(double radius) {
    if (radius < 0) {
        printf("Error: Radius cannot be negative.\n");

        return 0.0;
    }

    return PI * radius * radius;
}

double areaOfRectangle(double length, double width) {
    if (length < 0 || width < 0) {
        printf("Error: Length and width cannot be negative.\n");

        return 0.0;
    }

    return length * width;
}

double areaOfTriangle(double base, double height) {
    if (base < 0 || height < 0) {
        printf("Error: Base and height cannot be negative.\n");

        return 0.0;
    }

    return 0.5 * base * height;
}

void displayMenu() {
    printf("\n===== GEOMETRY CALCULATOR =====\n");
    printf("1. Area of Circle\n");
    printf("2. Area of Rectangle\n");
    printf("3. Area of Triangle\n");
    printf("4. Exit\n");
    printf("Enter your choice: ");
}

int main() {
    int choice;
    double radius, length, width, base, height, area;
    do {
        displayMenu();
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter radius: ");
                scanf("%lf", &radius);
                area = areaOfCircle(radius);
                printf("Area of circle: %.2f\n", area);
                break;
            case 2:
                printf("Enter length: ");
                scanf("%lf", &length);
                printf("Enter width: ");
                scanf("%lf", &width);
                area = areaOfRectangle(length, width);
                printf("Area of rectangle: %.2f\n", area);
                break;
            case 3:
                printf("Enter base: ");
                scanf("%lf", &base);
                printf("Enter height: ");
                scanf("%lf", &height);
                area = areaOfTriangle(base, height);
                printf("Area of triangle: %.2f\n", area);
                break;
            case 4:
                printf("Goodbye!\n");
                break;
            default:
                printf("Invalid choice. Please try again.\n");
        }
# Week 6


## linear_search.cpp

```cpp
#include <iostream>

using namespace std;

int linearSearch(int arr[], int size, int target) {
    for (int i = 0; i < size; i++) {
        if (arr[i] == target) {
            return i;
        }
    }

    return -1;
}

int main() {
    int numbers[8] = {15, 42, 7, 89, 23, 56, 11, 74};
    int size = sizeof(numbers) / sizeof(numbers[0]);
    int target;
    cout << "Array contents: ";
    for (int i = 0; i < size; i++) {
        cout << numbers[i] << " ";
    }
    cout << endl;
    cout << "Enter a number to search: ";
    cin >> target;
    int position = linearSearch(numbers, size, target);
    if (position != -1) {
        cout << "Element found at index: " << position << endl;
    } else {
        cout << "Element not found in the array." << endl;
    }

    return 0;
}

//g++ linear_search.cpp -o linear_search
//./linear_search
```


## row_major.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int matrix[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    cout << "Row-major traversal (row by row):" << endl;
    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 4; col++) {
            cout << matrix[row][col] << " ";
        }
        cout << endl;
    }
    cout << "\nMemory addresses (each int takes 4 bytes):" << endl;
    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 4; col++) {
            cout << "matrix[" << row << "][" << col << "] = "
                << matrix[row][col]
                << " at address " << &matrix[row][col] << endl;
        }
    }
    cout << "\nObservation: Addresses increase row by row." << endl;
    cout << "Row 0 is stored completely, then row 1, then row 2." << endl;
    cout << "This is called ROW-MAJOR ORDER." << endl;

    return 0;
}

//g++ row_major.cpp -o row_major
//./row_major
```


## cstring_version.cpp

```cpp
#include <iostream>
#include <cstring>   // For strlen, strcpy

using namespace std;

int main() {
    char name[50];
    cout << "Enter your name: ";
    cin.getline(name, 50);   // Reads a full line into the C-string
    cout << "Name: " << name << endl;
    cout << "Length: " << strlen(name) << endl;
    cout << "First character: " << name[0] << endl;
    char copy[50];
    strcpy(copy, name);
    cout << "Copy: " << copy << endl;

    return 0;
}

//g++ cstring_version.cpp -o cstring_version
//./cstring_version
```


## stdstring_version.cpp

```cpp
#include <iostream>
#include <string>   // For std::string

using namespace std;

int main() {
    string name;
    cout << "Enter your name: ";
    getline(cin, name);   // Reads a full line into the string
    cout << "Name: " << name << endl;
    cout << "Length: " << name.length() << endl;
    cout << "First character: " << name[0] << endl;
    string copy = name;
    cout << "Copy: " << copy << endl;
    string greeting = "Hello, " + name + "!";
    cout << greeting << endl;

    return 0;
}

//g++ stdstring_version.cpp -o stdstring_version
//./stdstring_version
```


## score_analyzer.cpp

```cpp
#include <iostream>
#include <iomanip>   // For setprecision

using namespace std;

double calculateAverage(int scores[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += scores[i];
    }

    return (double)sum / size;
}

void displayAboveAverage(int scores[], int size, double average) {
    cout << "\nScores above average (" << average << "):" << endl;
    bool found = false;
    for (int i = 0; i < size; i++) {
        if (scores[i] > average) {
            cout << " Score " << scores[i] << " at position " << i + 1 << endl;
            found = true;
        }
    }
    if (!found) {
        cout << " None" << endl;
    }
}

int main() {
    const int SIZE = 10;   // Number of scores
    int scores[SIZE];   // Array to store scores
    cout << "Enter " << SIZE << " student scores:" << endl;
    for (int i = 0; i < SIZE; i++) {
        cout << "Score " << i + 1 << ": ";
        cin >> scores[i];
    }
    double average = calculateAverage(scores, SIZE);
    cout << "\n--- Results ---" << endl;
    cout << "Average score: " << fixed << setprecision(2) << average << endl;
    displayAboveAverage(scores, SIZE, average);

    return 0;
}

//g++ score_analyzer.cpp -o score_analyzer
//./score_analyzer
```


## linear_search.c

```c
#include <stdio.h>

int linearSearch(int arr[], int size, int target) {
    for (int i = 0; i < size; i++) {
        if (arr[i] == target) {
            return i;
        }
    }

    return -1;
}

int main() {
    int numbers[8] = {15, 42, 7, 89, 23, 56, 11, 74};
    int size = sizeof(numbers) / sizeof(numbers[0]);
    int target;
    printf("Array contents: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", numbers[i]);
    }
    printf("\n");
    printf("Enter a number to search: ");
    scanf("%d", &target);
    int position = linearSearch(numbers, size, target);
    if (position != -1) {
        printf("Element found at index: %d\n", position);
    } else {
        printf("Element not found in the array.\n");
    }

    return 0;
}

//gcc linear_search.c -o linear_search
//./linear_search
```


## row_major.c

```c
#include <stdio.h>

int main() {
    int matrix[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    printf("Row-major traversal (row by row):\n");
    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 4; col++) {
            printf("%d ", matrix[row][col]);
        }
        printf("\n");
    }
    printf("\nMemory addresses (each int takes 4 bytes):\n");
    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 4; col++) {
            printf("matrix[%d][%d] = %d at address %p\n",
                    row, col, matrix[row][col], (void*)&matrix[row][col]);
        }
    }
    printf("\nObservation: Addresses increase row by row.\n");
    printf("Row 0 is stored completely, then row 1, then row 2.\n");
    printf("This is called ROW-MAJOR ORDER.\n");

    return 0;
}

//gcc row_major.c -o row_major
//./row_major
```


## cstring_version.c

```c
#include <stdio.h>
#include <string.h>   // For strlen, strcpy

int main() {
    char name[50];
    printf("Enter your name: ");
    fgets(name, 50, stdin);
    name[strcspn(name, "\n")] = '\0';
    printf("Name: %s\n", name);
    printf("Length: %lu\n", strlen(name));
    printf("First character: %c\n", name[0]);
    char copy[50];
    strcpy(copy, name);
    printf("Copy: %s\n", copy);

    return 0;
}

//gcc cstring_version.c -o cstring_version
//./cstring_version
```


## score_analyzer.c

```c
#include <stdio.h>

double calculateAverage(int scores[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += scores[i];
    }

    return (double)sum / size;
}

void displayAboveAverage(int scores[], int size, double average) {
    printf("\nScores above average (%.2f):\n", average);
    int found = 0;
    for (int i = 0; i < size; i++) {
        if (scores[i] > average) {
            printf(" Score %d at position %d\n", scores[i], i + 1);
            found = 1;
        }
    }
    if (!found) {
        printf(" None\n");
    }
}

int main() {
    const int SIZE = 10;   // Number of scores
    int scores[SIZE];   // Array to store scores
    printf("Enter %d student scores:\n", SIZE);
    for (int i = 0; i < SIZE; i++) {
        printf("Score %d: ", i + 1);
        scanf("%d", &scores[i]);
    }
    double average = calculateAverage(scores, SIZE);
    printf("\n--- Results ---\n");
    printf("Average score: %.2f\n", average);
    displayAboveAverage(scores, SIZE, average);

    return 0;
}

//gcc score_analyzer.c -o score_analyzer
//./score_analyzer
```
# Week 7


## pointer_arithmetic.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};
    int* ptr = numbers;
    cout << "Array elements accessed via pointer arithmetic:" << endl;
    for (int i = 0; i < 5; i++) {
        cout << "Value: " << *ptr << endl;
        ptr++;
    }
    ptr = numbers;
    cout << "\nAccessing using offset arithmetic:" << endl;
    for (int i = 0; i < 5; i++) {
        cout << "Index " << i << " has value: " << *(ptr + i) << endl;
    }

    return 0;
}

//g++ pointer_arithmetic.cpp -o pointer_arithmetic
//./pointer_arithmetic
```


## pointers_vs_references.cpp

```cpp
#include <iostream>

using namespace std;

int main() {
    // 1. A normal integer variable
    int originalValue = 100;

    // 2. A REFERENCE variable.
    int& refValue = originalValue;

    // 3. A POINTER variable.
    int* ptrValue = &originalValue;
    cout << "--- Initial State ---" << endl;
    cout << "originalValue: " << originalValue << endl;
    cout << "refValue: " << refValue << endl;
    cout << "ptrValue points to: " << *ptrValue << endl;   // * dereferences to get the value

    // --- modification 1 ---
    refValue = 200;
    cout << "\n--- After setting refValue = 200 ---" << endl;
    cout << "originalValue: " << originalValue << endl;   // Expected: 200
    cout << "ptrValue points to: " << *ptrValue << endl;   // Expected: 200

    // --- modification 2 ---
    *ptrValue = 300;
    cout << "\n--- After setting *ptrValue = 300 ---" << endl;
    cout << "originalValue: " << originalValue << endl;   // Expected: 300
    cout << "refValue: " << refValue << endl;   // Expected: 300

    // --- modification 3 ---
    int anotherValue = 500;
    ptrValue = &anotherValue;
    cout << "\n--- After pointing ptrValue to anotherValue ---" << endl;
    cout << "originalValue: " << originalValue << endl;   // Expected: 300
    cout << "ptrValue points to: " << *ptrValue << endl;   // Expected: 500

    // refValue = anotherValue; would just copy the value 500 into originalValue.

    return 0;
}

//g++ pointers_vs_references.cpp -o pointers_vs_references
//./pointers_vs_references
```


## memory_leak.cpp

```cpp
#include <iostream>

using namespace std;

void createLeak() {
    int* ptr = new int(42);
    cout << "Inside function. The value is: " << *ptr << endl;
    cout << "Memory allocated at address: " << ptr << endl;
}

int main() {
    cout << "Calling function that leaks memory..." << endl;
    createLeak();
    cout << "Function finished. The memory is now leaked." << endl;

    return 0;
}

//g++ memory_leak.cpp -o memory_leak
//./memory_leak
```


## memory_leak_fix.cpp

```cpp
#include <iostream>

using namespace std;

void fixLeak() {
    int* ptr = new int(42);
    cout << "Inside fixed function. Value: " << *ptr << endl;
    cout << "Memory allocated at address: " << ptr << endl;
    delete ptr;
    ptr = nullptr;
    cout << "Memory has been successfully freed." << endl;
}

int main() {
    cout << "--- Testing the Fix ---" << endl;
    fixLeak();

    return 0;
}

//g++ memory_leak_fix.cpp -o memory_leak_fix
//./memory_leak_fix
```


## dynamic_array.cpp

```cpp
#include <iostream>

using namespace std;

class DynamicArray {
private:
    int* data;
    int size;
    int capacity;
public:
    DynamicArray(int initialCapacity) {
        capacity = initialCapacity;
        size = 0;
        data = new int[capacity];
    }
    ~DynamicArray() {
        delete[] data;
    }
    void push_back(int value) {
        // 1. Check if we have run out of space
        if (size == capacity) {
            int newCapacity = capacity * 2;
            int* newData = new int[newCapacity];
            for (int i = 0; i < size; i++) {
                newData[i] = data[i];
            }
            delete[] data;
            data = newData;
            capacity = newCapacity;
            cout << "[Resized capacity from " << capacity/2 << " to " << capacity << "]" << endl;
        }

        // 2. Add the new value at the next available slot
        data[size] = value;
        size++;   // Increment the size counter
    }
    void display() {
        cout << "Array (Size: " << size << ", Capacity: " << capacity << "): ";
        for (int i = 0; i < size; i++) {
            cout << data[i] << " ";
        }
        cout << endl;
    }
};

int main() {
    DynamicArray myArray(2);
    cout << "Created dynamic array with capacity 2." << endl;
    myArray.push_back(10);
    myArray.push_back(20);
    myArray.display();
    cout << "\nAdding third element..." << endl;
    myArray.push_back(30);
    myArray.display();
    cout << "\nAdding fourth and fifth elements..." << endl;
    myArray.push_back(40);
    myArray.push_back(50);   // This will trigger another resize
    myArray.display();

    return 0;
}

//g++ dynamic_array.cpp -o dynamic_array
//./dynamic_array
```


## pointer_arithmetic.c

```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};
    int *ptr = numbers;
    printf("Array elements accessed via pointer arithmetic:\n");
    for (int i = 0; i < 5; i++) {
        printf("Value: %d\n", *ptr);
        ptr++;
    }
    ptr = numbers;
    printf("\nAccessing using offset arithmetic:\n");
    for (int i = 0; i < 5; i++) {
        printf("Index %d has value: %d\n", i, *(ptr + i));
    }

    return 0;
}

//gcc pointer_arithmetic.c -o pointer_arithmetic
//./pointer_arithmetic
```


## pointers_in_c.c

```c
#include <stdio.h>

int main() {
    // 1. A normal integer variable
    int originalValue = 100;

    // 2. In C++, we would use a reference: int& refValue = originalValue;
    int *ptr1 = &originalValue;
    int *ptr2 = &originalValue;
    printf("--- Initial State ---\n");
    printf("originalValue: %d\n", originalValue);
    printf("Value via ptr1: %d\n", *ptr1);   // * dereferences to get the value

    // --- modification 1 ---
    *ptr1 = 200;
    printf("\n--- After setting *ptr1 = 200 ---\n");
    printf("originalValue: %d\n", originalValue);   // Expected: 200
    printf("Value via ptr2: %d\n", *ptr2);   // Expected: 200

    // --- modification 2 ---
    *ptr2 = 300;
    printf("\n--- After setting *ptr2 = 300 ---\n");
    printf("originalValue: %d\n", originalValue);   // Expected: 300
    printf("Value via ptr1: %d\n", *ptr1);   // Expected: 300

    // --- modification 3 ---
    int anotherValue = 500;
    ptr1 = &anotherValue;
    printf("\n--- After pointing ptr1 to anotherValue ---\n");
    printf("originalValue: %d\n", originalValue);   // Expected: 300 (Unchanged)
    printf("Value via ptr1: %d\n", *ptr1);   // Expected: 500

    return 0;
}

//gcc pointers_in_c.c -o pointers_in_c
//./pointers_in_c
```


## memory_leak.c

```c
#include <stdio.h>
#include <stdlib.h>

void createLeak() {
    int *ptr = (int*)malloc(sizeof(int));
    if (ptr == NULL) {
        printf("Memory allocation failed!\n");

        return;
    }
    *ptr = 42;
    printf("Inside function. The value is: %d\n", *ptr);
    printf("Memory allocated at address: %p\n", (void*)ptr);
}

int main() {
    printf("Calling function that leaks memory...\n");
    createLeak();
    printf("Function finished. The memory is now leaked.\n");

    return 0;
}

//gcc memory_leak.c -o memory_leak
//./memory_leak
```


## memory_leak_fix.c

```c
#include <stdio.h>
#include <stdlib.h>

void fixLeak() {
    int *ptr = (int*)malloc(sizeof(int));
    *ptr = 42;
    printf("Inside fixed function. Value: %d\n", *ptr);
    free(ptr);
    ptr = NULL;
    printf("Memory has been successfully freed.\n");
}

int main() {
    printf("--- Testing the Fix ---\n");
    fixLeak();

    return 0;
}

//gcc memory_leak_fix.c -o memory_leak_fix
//./memory_leak_fix
```


## dynamic_array.c

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int *data;
    int size;
    int capacity;
} DynamicArray;
void initArray(DynamicArray *arr, int initialCapacity) {
    arr->capacity = initialCapacity;
    arr->size = 0;
    arr->data = (int*)malloc(arr->capacity * sizeof(int));
    if (arr->data == NULL) {
        printf("Failed to allocate memory.\n");
        exit(1);
    }
}

void freeArray(DynamicArray *arr) {
    free(arr->data);
    arr->data = NULL;
    arr->size = 0;
    arr->capacity = 0;
}

void push_back(DynamicArray *arr, int value) {
    // 1. Check if we have run out of space
    if (arr->size == arr->capacity) {
        int newCapacity = arr->capacity * 2;
        int *newData = (int*)malloc(newCapacity * sizeof(int));
        if (newData == NULL) {
            printf("Failed to allocate memory during resize.\n");

            return;
        }
        for (int i = 0; i < arr->size; i++) {
            newData[i] = arr->data[i];
        }
        free(arr->data);
        arr->data = newData;
        arr->capacity = newCapacity;
        printf("[Resized capacity from %d to %d]\n", arr->capacity / 2, arr->capacity);
    }

    // 2. Add the new value at the next available slot
    arr->data[arr->size] = value;
    arr->size++;   // Increment the size counter
}

void display(DynamicArray *arr) {
    printf("Array (Size: %d, Capacity: %d): ", arr->size, arr->capacity);
    for (int i = 0; i < arr->size; i++) {
        printf("%d ", arr->data[i]);
    }
    printf("\n");
}

int main() {
    DynamicArray myArray;
    initArray(&myArray, 2);
    printf("Created dynamic array with capacity 2.\n");
    push_back(&myArray, 10);
    push_back(&myArray, 20);
    display(&myArray);
    printf("\nAdding third element...\n");
    push_back(&myArray, 30);
    display(&myArray);
    printf("\nAdding fourth and fifth elements...\n");
    push_back(&myArray, 40);
    push_back(&myArray, 50);   // This will trigger another resize
    display(&myArray);
    freeArray(&myArray);

    return 0;
}

//gcc dynamic_array.c -o dynamic_array
//./dynamic_array
```
# Week 8


## encapsulation.cpp

```cpp
#include <iostream>
#include <string>

using namespace std;

class Student {
private:
    string name;
    int age;
public:
    Student(string studentName, int studentAge) {
        name = studentName;
        setAge(studentAge);
    }
    string getName() {
        return name;
    }
    void setAge(int newAge) {
        if (newAge > 0 && newAge < 120) {
            age = newAge;
        } else {
            cout << "Error: Invalid age! Age must be between 1 and 119." << endl;
            age = 0;
        }
    }
    int getAge() {
        return age;
    }
};

int main() {
    Student s1("Alice", 20);
    cout << "Student Name: " << s1.getName() << endl;
    cout << "Student Age: " << s1.getAge() << endl;
    cout << "\nAttempting to change age to 25..." << endl;
    s1.setAge(25);
    cout << "New Age: " << s1.getAge() << endl;
    cout << "\nAttempting to change age to -5..." << endl;
    s1.setAge(-5);   // This will trigger our validation error!
    cout << "Age after invalid attempt: " << s1.getAge() << endl;

    // Uncommenting the lines below will cause a compilation error!
    // s1.age = 30; // ERROR: 'age' is private!
    // s1.name = "Bob"; // ERROR: 'name' is private!

    return 0;
}

//g++ encapsulation.cpp -o encapsulation
//./encapsulation
```


## stack_vs_heap.cpp

```cpp
#include <iostream>
#include <string>

using namespace std;

class Car {
public:
    string model;
    Car(string m) {
        model = m;
        cout << "Car created: " << model << endl;
    }
    ~Car() {
        cout << "Car destroyed: " << model << endl;
    }
};

int main() {
    cout << "--- Creating Stack Object ---" << endl;
    Car stackCar("Toyota");
    cout << "\n--- Creating Heap Object ---" << endl;
    Car* heapCar = new Car("Honda");
    cout << "Heap car model: " << heapCar->model << endl;
    cout << "\n--- End of main function ---" << endl;
    delete heapCar;

    return 0;
}

//g++ stack_vs_heap.cpp -o stack_vs_heap
//./stack_vs_heap
```


## bank_account_design.cpp

```cpp
#include <iostream>

using namespace std;

class BadBankAccount {
public:
    double balance;
    BadBankAccount() {
        balance = 0.0;
    }
};

class GoodBankAccount {
private:
    double balance;
public:
    GoodBankAccount() {
        balance = 0.0;
    }
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }
    double getBalance() {
        return balance;
    }
};

int main() {
    cout << "--- Testing BAD Design ---" << endl;
    BadBankAccount badAccount;
    badAccount.balance = -5000;   // Impossible in real life!
    cout << "Bad Account Balance: " << badAccount.balance << endl;
    cout << "\n--- Testing GOOD Design ---" << endl;
    GoodBankAccount goodAccount;

    // goodAccount.balance = -5000; // ERROR! Private! The compiler will block this!
    goodAccount.deposit(1000);
    cout << "Good Account Balance: " << goodAccount.getBalance() << endl;

    return 0;
}

//g++ bank_account_design.cpp -o bank_account_design
//./bank_account_design
```


## bank_account.cpp

```cpp
#include <iostream>
#include <string>

using namespace std;

class BankAccount {
private:
    string accountHolder;
    double balance;
public:
    BankAccount(string name, double initialBalance) {
        accountHolder = name;
        if (initialBalance >= 0) {
            balance = initialBalance;
        } else {
            balance = 0;
            cout << "Warning: Initial balance cannot be negative. Set to 0." << endl;
        }
    }
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            cout << "Successfully deposited: $" << amount << endl;
        } else {
            cout << "Error: Deposit amount must be greater than 0." << endl;
        }
    }
    void withdraw(double amount) {
        if (amount <= 0) {
            cout << "Error: Withdrawal amount must be greater than 0." << endl;

            return;   // Exit the function early
        }
        if (amount > balance) {
            cout << "Error: Insufficient funds! Current balance is $" << balance << endl;
        } else {
            balance -= amount;
            cout << "Successfully withdrew: $" << amount << endl;
        }
    }
    void displayBalance() {
        cout << "Account Holder: " << accountHolder << endl;
        cout << "Current Balance: $" << balance << endl;
    }
};

int main() {
    cout << "--- Opening Account ---" << endl;
    BankAccount aliceAccount("Alice Smith", 500.00);
    aliceAccount.displayBalance();
    cout << "\n--- Attempting Deposits ---" << endl;
    aliceAccount.deposit(200.00);   // Valid
    aliceAccount.deposit(-50.00);   // Invalid (negative)
    cout << "\n--- Attempting Withdrawals ---" << endl;
    aliceAccount.withdraw(100.00);   // Valid
    aliceAccount.withdraw(1000.00);   // Invalid (insufficient funds)
    aliceAccount.withdraw(-20.00);   // Invalid (negative)
    cout << "\n--- Final Account Status ---" << endl;
    aliceAccount.displayBalance();

    return 0;
}

//g++ bank_account.cpp -o bank_account
//./bank_account
```


## encapsulation.c

```c
#include <stdio.h>   // For printf and scanf
#include <string.h>   // For strcpy

struct Student {
    char name[50];
    int age;
};

void setAge(struct Student *s, int newAge) {
    if (newAge > 0 && newAge < 120) {
        s->age = newAge;
    } else {
        printf("Error: Invalid age! Age must be between 1 and 119.\n");
        s->age = 0;   // Set to default if invalid
    }
}

int getAge(struct Student *s) {
    return s->age;
}

int main() {
    // 1. Create a Student struct on the stack
    struct Student s1;
    strcpy(s1.name, "Alice");
    setAge(&s1, 20);
    printf("Student Name: %s\n", s1.name);
    printf("Student Age: %d\n", getAge(&s1));
    printf("\nAttempting to change age to -5...\n");
    setAge(&s1, -5);
    printf("Age after invalid attempt: %d\n", getAge(&s1));

    return 0;
}

//gcc encapsulation.c -o encapsulation
//./encapsulation
```


## stack_vs_heap.c

```c
#include <stdio.h>
#include <stdlib.h>   // Required for malloc and free
#include <string.h>

struct Car {
    char model[20];
};

void initCar(struct Car *c, const char *modelName) {
    strcpy(c->model, modelName);
    printf("Car created: %s\n", c->model);
}

void destroyCar(struct Car *c) {
    printf("Car destroyed: %s\n", c->model);
}

int main() {
    printf("--- Creating Stack Object ---\n");
    struct Car stackCar;
    initCar(&stackCar, "Toyota");
    printf("\n--- Creating Heap Object ---\n");
    struct Car *heapCar = (struct Car*)malloc(sizeof(struct Car));
    if (heapCar != NULL) {
        initCar(heapCar, "Honda");
        printf("Heap car model: %s\n", heapCar->model);
    }
    printf("\n--- End of main function ---\n");
    if (heapCar != NULL) {
        destroyCar(heapCar);
        free(heapCar);
        heapCar = NULL;   // Prevent dangling pointer
    }

    return 0;
}

//gcc stack_vs_heap.c -o stack_vs_heap
//./stack_vs_heap
```


## bank_account_design.c

```c
#include <stdio.h>

struct BadBankAccount {
    double balance;
};

struct GoodBankAccount {
    double balance;
};

void goodDeposit(struct GoodBankAccount *acc, double amount) {
    if (amount > 0) {
        acc->balance += amount;
    }
}

int main() {
    printf("--- Testing BAD Design ---\n");
    struct BadBankAccount badAccount;
    badAccount.balance = 100.0;
    badAccount.balance = -5000.00;   // Impossible in real life!
    printf("Bad Account Balance: %.2f\n", badAccount.balance);
    printf("\n--- Testing GOOD Design ---\n");
    struct GoodBankAccount goodAccount;
    goodAccount.balance = 100.0;
    goodDeposit(&goodAccount, 500.00);
    printf("Good Account Balance: %.2f\n", goodAccount.balance);

    return 0;
}

//gcc bank_account_design.c -o bank_account_design
//./bank_account_design
```


## bank_account.c

```c
#include <stdio.h>
#include <string.h>

struct BankAccount {
    char accountHolder[50];
    double balance;
};

void initAccount(struct BankAccount *acc, const char *name, double initialBalance) {
    strcpy(acc->accountHolder, name);
    if (initialBalance >= 0) {
        acc->balance = initialBalance;
    } else {
        acc->balance = 0;
        printf("Warning: Initial balance cannot be negative. Set to 0.\n");
    }
}

void deposit(struct BankAccount *acc, double amount) {
    if (amount > 0) {
        acc->balance += amount;
        printf("Successfully deposited: $%.2f\n", amount);
    } else {
        printf("Error: Deposit amount must be greater than 0.\n");
    }
}

void withdraw(struct BankAccount *acc, double amount) {
    if (amount <= 0) {
        printf("Error: Withdrawal amount must be greater than 0.\n");

        return;   // Exit the function early
    }
    if (amount > acc->balance) {
        printf("Error: Insufficient funds! Current balance is $%.2f\n", acc->balance);
    } else {
        acc->balance -= amount;
        printf("Successfully withdrew: $%.2f\n", amount);
    }
}

void displayBalance(struct BankAccount *acc) {
    printf("Account Holder: %s\n", acc->accountHolder);
    printf("Current Balance: $%.2f\n", acc->balance);
}

int main() {
    printf("--- Opening Account ---\n");
    struct BankAccount aliceAccount;
    initAccount(&aliceAccount, "Alice Smith", 500.00);
    displayBalance(&aliceAccount);
    printf("\n--- Attempting Deposits ---\n");
    deposit(&aliceAccount, 200.00);   // Valid
    deposit(&aliceAccount, -50.00);   // Invalid
    printf("\n--- Attempting Withdrawals ---\n");
    withdraw(&aliceAccount, 100.00);   // Valid
    withdraw(&aliceAccount, 1000.00);   // Invalid (insufficient funds)
    withdraw(&aliceAccount, -20.00);   // Invalid (negative)
    printf("\n--- Final Account Status ---\n");
    displayBalance(&aliceAccount);

    return 0;
