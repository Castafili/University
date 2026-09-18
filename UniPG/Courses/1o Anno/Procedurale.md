---
date: 16/03/26
tags:
  - UniPG
  - proc
---
# Variables

| Variable Type | Purpose                         | Size        |
| ------------- | ------------------------------- | ----------- |
| int           | whole numbers                   | 4 bytes     |
| float         | single-precision decimal number | 4 bytes     |
| double        | double-precision decimal number | 8 bytes     |
| char          | single character                | 1 byte      |
| char[]        | array of characters             | size varies |
| bool          | true or false                   | 1 Byte      |
>[!INFO] bool requires <stdbool.h>

## Format specifier

It's a token that begins with %, followed by a character that specifies the data type (int, float, double) and optional modifiers (*width, precision, flags*).

| Variable Type | Format Specifier |
| ------------- | ---------------- |
| int           | %d               |
| float         | %f               |
| double        | %lf              |
| character     | %c               |
| string        | %s               |
### Width
```c
printf("%04d\n",num1);
```
Output: 
```c
0001
```

### Precision
```c
float price1 = 19.99;
float price2 = 1.50;
float price3 = 9.99;

printf("%.2f\n", price1);
printf("%f\n", price2);
printf("%.1f\n", price3);
```
Output:
```c
19.99
1.500000 // C adds 6 digits after the decimal
10.0 // Value rounds up
```

---
# Arithmetic operators

```c
int x = 2;
int y = 3;
int z = 0;

z = x + y;

printf("%d", z); // Output 5

z = x - y;

printf("%d", z); // Output -1

z = x * y;

printf("%d", z); // Output 6

z = x / y;

printf("%d", z); // Output 0, can't divide by an integers
---
	int x = 2;
	float y = 3;
	float z = 0;
	
	z = x / y;
	
	printf("%f", z); // Output 0.666667

---
	int x = 10;
	int y = 3;
	int z = 0;
	
	z = x % y;
	
	printf("%d", z); // Output 1 (remainder of 1)
	
	
	x++;
	printf("%d", x); // Output 11
	
	x--;
	printf("%d", x); // Output 9
	
	
	x = x+2 == x+=2 // And this with all operations
	
	printf("%d", x); // Output 12

```

---

# User input

```c
#include <stdio.h>
#include <string.h>

int age = 0;
float gpa  = 0.0f; // f if it's a float, not needed for doubles
char grade = '\0'; //Clears character
char name[30] = ""; // Empty strings still with 30bytes allocated

printf("Enter your age: ");
scanf("%d", &age);

printf("Enter your gpa: ");
scanf("%f", &gpa);

printf("Enter your grade: ");
scanf(" %c", &grade); // The space is a shortcut that clears the input buffer

/* printf("Enter your full name: ");
scanf("%s", &name); scanf stops reading after spaces so it wont get your last name. so we use fgets: file get string*/

getchar(); // Clears buffer since we dont have the " %c"
printf("Enter your full name: ");
fgets(name, sizeof(name), stdin); // We put the variable, the size of name (with sizeof() if the size changes we dont have to change it here), stdin (standard input)
name[strlen(name) - 1] = '\0'; // With fgets when we send the input with enter we also send a \n character that gets into the buffer, with this method (requires the second #include) we change that last character from a \n to a\0

```
Output:
```c
Enter your age: ___ //Space for user input
Enter your gpa: ___
Enter your grade: ___
Enter your full name: ___
```

---

# if statements

These statements execute code if a condition is true and DON'T execute it if it's false

```c
int age = 70;

if(age >= 18){
	printf("You are an adult");
}
else if(age >= 65){
	printf("You are a senior");
}
else if(age < 0){
	printf("You haven't been born yet");
}
else{
	printf("You are a child");
}
```
Output:
```c
You are an adult //If statements are read top to bottom and the first if is true
```

So the way to make it display what we want is to change the order:

```c
int age = 70;

if(age >= 65){
	printf("You are a senior");
}
else if(age >= 18){
	printf("You are an adult");
}
else if(age < 0){
	printf("You haven't been born yet");
}
else{
	printf("You are a child");
}
```
Output:
```c
You are a senior
```

### Strings

```c
#include <stdio.h>
#include <string.h>

int main() {
	char name[50] = " ";
	
	printf("Enter your name: ");
	fgets(name, sizeof(name), stdin);
	name[strlen(name) - 1] = '\0';
	
	if(strlen(name) == 0){
		printf("You did not enter your name");
	}
	else{
		printf("Hello %s", name);
	}
	
	return 0;
}
```

---
# Switches

>[!INFO] Switches
>Alternative to using many if-else statements. More efficient w/ fixed integer values

```c 

int dayOfWeek = 0;
printf("Enter a day of the week (1-7): ");
scanf("%d", &dayOfWeek);

// If the value of "dayOfWeek" matches with the case then it executes that case

// The break is needed to stop the switch to keep going forward and to "break out" of the switch

// Characters can also be used in place of integers: case 'M'

switch(dayOfWeek){
	case 1:
		printf("It is Monday");
		break;
	case 2:
		printf("It is Tuesday");
		break;
	case 3:
		printf("It is Wednesday");
		break;
	case 4:
		printf("It is Thursday");
		break;
	case 5:
		printf("It is Friday");
		break;
	case 6:
		printf("It is Saturday");
		break;
	case 7:
		printf("It is Sunday");
		break;	
	default:
		printf("Please only enter a number 1-7");
}




return 0;

```

---
# Logical operators

>[!INFO] Used to combine or modify boolean expressions.
>- && = AND (Both conditions **NEED** to be true)
>- || = OR (Only one condition **NEEDS** to be true)
>- ! = NOT

```c

int temp = 10000;

if(temp > 0 && temp < 30) {
	pirntf("The temperature is GOOD");
}
else{
	printf("The temperature is BAD");
}
```
Output:
```c
The temperature is BAD
```

---

# Functions

>[!INFO] A reusable section of code that can be invoked "called". Arguments can be sent to a function so that it can use them.

Example of task **WITHOUT** function:
```c
int main() {
	 
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday dear [name]!");
	printf("\nHappy birthday to you!");
	printf("\nYou are [age] years old!\n");
	
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday dear [name]!");
	printf("\nHappy birthday to you!");
	printf("\nYou are [age] years old!\n");
	
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday dear [name]!");
	printf("\nHappy birthday to you!");
	printf("\nYou are [age] years old!\n");
	
	return 0;
}
```
Output:
```c
Happy birthday to you!
Happy birthday to you!
Happy birthday dear [name]!
Happy birthday to you!
You are [age] years old!

Happy birthday to you!
Happy birthday to you!
Happy birthday dear [name]!
Happy birthday to you!
You are [age] years old!

Happy birthday to you!
Happy birthday to you!
Happy birthday dear [name]!
Happy birthday to you!
You are [age] years old!
```

In coding we try not to repeat ourselves

Example of task **WITH** function:
```c
void happyBirthday(){
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday dear [name]!");
	printf("\nHappy birthday to you!");
	printf("\nYou are [age] years old!\n");
}

int main() {
	 
	 happyBirthday();
	 happyBirthday();
	 happyBirthday();
	 
	return 0;
}	
```
Output:
```c
Happy birthday to you!
Happy birthday to you!
Happy birthday dear [name]!
Happy birthday to you!
You are [age] years old!

Happy birthday to you!
Happy birthday to you!
Happy birthday dear [name]!
Happy birthday to you!
You are [age] years old!

Happy birthday to you!
Happy birthday to you!
Happy birthday dear [name]!
Happy birthday to you!
You are [age] years old!
```

#### Arguments

```c

void happyBirthday(char name[], int age){
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday dear %s!", name);
	printf("\nHappy birthday to you!");
	printf("\nYou are %d years old!\n", age);
}

int main() {
	 
	 char name[] = "Bro";
	 int age = 25;
	 
	 happyBirthday(name, age); // We pass them as arguments so the function knows what "name" and "age" are. Order DOES matter
	 
	return 0;
}	
```
Output:
```c
Happy birthday to you!
Happy birthday to you!
Happy birthday dear Bro!
Happy birthday to you!
You are 25 years old!
```


#### User Input

```c
#include <stdio.h>
#include <string.h>

void happyBirthday(char name[], int age){
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday to you!");
	printf("\nHappy birthday dear %s!", name);
	printf("\nHappy birthday to you!");
	printf("\nYou are %d years old!\n", age);
}

int main() {
	 
	 char name[50] = """;
	 int age = 0;
	 
	 printf("Enter your name: ");
	 fgets(name, sizeof(name), stdin);
	 name[strlen(namr) - 1] = '\0';
	 
	 printf("Enter your age: ");
	 scanf("%d", &age);
	 
	 happyBirthday(name, age); // We pass them as arguments so the function knows what "name" and "age" are. Order DOES matter
	 
	return 0;
}	
```
Output:
```c
Enter your name: Filippo
Enter your age: 20

Happy birthday to you!
Happy birthday to you!
Happy birthday dear Filippo!
Happy birthday to you!
You are 20 years old!
```

---

# Return

>[!INFO] Returns a value back to where you call a function

```c
#include <stdio.h>

int cube(in num){
	return num * num * num
}

int square(int num){

	int result = num * num;
	
	return result;
}

int main() {
	
	int x = cube(2);
	int y = cube(3);
	int z = cube(4);
	
	printf("%d\n", x);
	printf("%d\n", y);
	printf("%d\n", z);
	
	return 0;
}
```
Output:
```c
8
27
64
```

Age check example:

```c
#include <stdio.h>
#include <stdbool.h>

bool ageCheck(int age){
	
	if(age >= 18){
		return true;
	}
	else{
		return false;
	}
}

int main() {
	
	int age = 21;
	
	if(ageCheck(age)){
		printf("You may sign up");
	}
	else{
		printf("You msut be 18+ to sign up");
	}
	
	return 0;
}
```
Output:
```c
You may sign up
```

---




https://youtu.be/xND0t1pr3KY?t=8106

Source: [[Programmazione Procedurale]]

---
Created: 