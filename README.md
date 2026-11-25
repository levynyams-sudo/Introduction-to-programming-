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
