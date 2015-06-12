## Codestars - Problem Set 0

Please submit your completed problem set as a Word document and copy a Dropbox
link to this document for our review. The deadline to submit your answers to
this problem set is **July 12th, 2015 at 11:59 PM**.

All questions presented below will be based on the readings and videos lectures
assigned below. You are to watch the assigned videos and complete the assigned
readings in order to answer the questions presented in the quiz. We recommend
that you take detailed notes as you complete the video lectures and readings as
this will help you reinforce your learning. 

### Pre-work Part I: C, Programming and Computer Science
Watch the video lectures for weeks 0 - 5 of Harvard’s CS50 course. While
watching these lectures you are to also read chapters 1 - 12 of Objective-C
Programming, The Big Nerd Ranch Guide, as it covers a lot of the same material
covered in the CS50 lectures. During this phase of the pre-work you will learn
about programming, the C programming language and Computer Science basics that
will help you develop a solid foundation that will help you become a strong
developer.

### Pre-work Part II: Objective-C
Read chapters 13 - 30 of Objective-C Programming, The Big Nerd Ranch Guide.
During this portion of the pre-work you gain a solid understanding of the
Objective-C programming language, which is used to build both iOS and OS X
applications. An important note on how to work through this material: You are
advised to begin working on this curriculum as soon as possible and not to wait
until the last minute to work through the work. During the actual course you
will be expected to spend a minimum of two hours a day working on assignments
outside of class so you should use this opportunity to get into this habit. 

### Links to Pre-work Material 
Harvard CS50: https://cs50.harvard.edu/lectures
Objective-C Programming, The Big Nerd Ranch Guide:
https://www.bignerdranch.com/documents/objective-c-prereading-assignment.pdf

### Basic Information 
Full Name: Nina Baculinao
Email address: nb2406@columbia.edu

### Programming Basics 
1. _To the best of your ability, describe the difference between programming and computer science._ 
Computer science is the theoretical study of what computation is and what
computers can do; it’s concerned with runtime complexity, NP-hard/complete
problem classification, compilers, etc. Programming is writing programs that do
what they have been designed to do and can be maintained. Let’s call computer
science "the science of computation": running some algorithm, or set of
instructions, on inputs, to produce some output, or solution.
2. _What is binary?_
Computers only understand zeroes and ones, an alphabet called binary. While
humans use decimal, which has 10 digits 0-9, computers only understand binary,
which has two digits, 0 and 1. With just two digits, we can still represent
almost every possible piece of information. Binary represents numbers in the
same pattern, but using powers of 2 instead of powers of 10 that decimal uses.
3. _What are bits?_
Bits (binary digits) are the smallest unit of storage in a computer, storing
data of a 0 or 1.
4. _What are bytes?_
Bytes are a unit of data that are eight binary digits long; typically at the
smallest scale in the computer, we group information in bits and bytes.
5. _What is ASCII?_
ASCII (American Standard Code for Information Interchange) is an encoding by
which each alphabetic, numeric or special character is mapped to a 7-bit binary
number. There are only 128 possible characters defined in ASCII, though Unicode
exists as an effort to include a more international encoding standard for use
with different languages and writing systems.
6. _What are algorithms?_
Using pseudo code, write an algorithm that will reverse a string.
Algorithms are just a step-by-step set of operations to be performed in
calculations or other problem-solving exercises, typically by a computer.
Note: Pseudocode is written similarly to Python, but wouldn not actually work
this cleanly since strings are immutable in Python

```python
for (idx = 0; idx != len(str)/2; i++):
    temp = str[idx]
    str[idx] = str[len(str)-idx-1]
    str[len(str)-idx-1] = temp
```

7. _What does it mean to compile your code? Describe how a compiler works._ 
Compiling your code is the act of translating your source code written in a
high-level programming language such as C, Java, Python, etc. into the native
machine code of your computer. A compiler is a program that translates the
source code for another program from a programing language into executable
code. A compiler is a computer program (or set of programs) that transforms
source code written in a programming language (the source language) into
another computer language (the target language, often having a binary form
known as object code). The most common reason for wanting to transform source
code is to create an executable program. In short, a compiler converts a
program from a human-readable format into a machine-readable instructions.
Every compiler is written to process source files in a particular language. 

8. _What is the new line character? How does it work?_
In Unix systems, the newline character is represented by the escape
sequence ```\n```; in Windows system it is represented by two characters ```\n\r```
(where \r is carriage return, originating from the need to manually push the
cartridge back into a starting position in the days of typewriters). If we were
writing a printf() statement in a C program, we include a newline character
when we want output to continue on a new line. When we see a text file, we see
it as a series of lines, and can enter a line break by pressing the Return or
Enter key. The special character that is inserted into the text file is the
newline character, either \n or \r\n depending on the system. When we open a
text file in, for example a C program, we typically read/scan the file line by
line, using the newlines to find out where an old line ends and a new one
begins.

9. _What is the terminal or command line? How can we use it as developers?_
The terminal / command-line interface is a user interface that we can use to
interact with our computer’s operating system and execute various programs.
It’s a more concise and powerful way we can control our computer compared to
the standard graphical user interface (which includes the application icons,
mouse cursor, and all the other intuitive graphics we see when we boot up a
modern a computer). As developers, we can use the command-line just about
anything under the sun involving our computer. We can write programs in vim,
run programs with the appropriate compilers and build commands, navigate our
file systems and change permissions, use the various command-line tools like
cat, check our IP address, connect to other machines using netcat, control
version control for our files using git commands, change our system
preferences, and so on. 

### The C Programming Language 
1. _What are header files and what are they used for? Write an example of how
you would use a header file below._
 Header files are files that end with .h where you can include the declaration
/ protype / signature of  functions defined in a .c file with the same prefix.
It is used during the compiling phase, before linking. A typical header file
would look like this. 

main.c

```c
#include <stdio.h> 
#include "myadd.h"  
    int main(int argc, char **argv) {   
        printf("The sum is: %d \n", add(1, 2));   
        return 0; 
    }
```

```c
myadd.c
#include "myadd.h" 
int add(int x, int y) {     
    return x + y; 
}
```

2. _List the different types used in C along with their size. What’s the
difference between int, float and double?_
 char    1 byte
 short   2 bytes
 int     4 bytes
 float   4 bytes
 long    8 bytes
 doubl   8 bytes
 pointer 8 bytes
 struct  - varies depending on its components, for example a struct with a
           (x,y) coordinate where x and y are both ints would be 8 bytes
Also note that these sizes can vary system to system; I verified the sizes on
my system for these different types with sizeof(). As the name suggests, int
only stores integers, and because it is 4 bytes (or 32 bits), it can store
values in the [-2^31, 2^31-1] range. On the other hand, floats and doubles
store floating point numbers (i.e. real number encoded with the IE 754
standard) where a float is a single precision floating type, and a double is a
double precision floating type. Since floats are 32 bits, this gives us 23 bits
for the significand, 8 bits for exponent and 1 sign bit; while the 64-bit
double gives us double the precision, which translates to 52 bits of
significand, 11 bits of exponent and 1 sign bit. 
3. _What are variables? How might we use them in our program?_
Variables are named identifiers associated with a chunk of stored data. We use
variable names in our programs as a way to reference stored values, for example
in mathematical computation we can store, access, change and keep track of
pre-computed values. By separating the name and value, we can also reassign new
values for the old variable. Typically, functions dealing with variables can be
split into accessor or mutator functions – as the name hints, we can either
access the stored values or change the stored values.
4. _How do we declare variables in C?_
Since C is a static type, variable declaration looks like this: ```[type] [name] =
[value or expression]```. For example we can assign a float type variable the name
wight and value of 14.2 using: ```float weight = 14.2```. After the declaration you
can just refer to the variable by its name without its type. We can also simply
declare an uninitalized variable and define / assign it a value later: ```[type]
[name]```, e.g. ```float weight;```
5. _How do we create strings in C?_
You can store a literal string in a type char * variable as in char *myString = "Here is a string";
6. _What is a char*?_
A char * is a pointer to a char variable, which can be treated like a char
array that can represent a string.
7. _Write a simple if/else statement in C._
```c
if (rank == 1) {
    printf("You won!");
} else {
    printf("You almost won…");
}
```
8. _Explain what functions are and they help us write better code?_
Functions are 
9. _Describe how strings are represented in C. What is the null terminator character?_
10. _What is an array? How are they represented in C? How are strings and arrays related in C?_
11. _What does void represent?_
12. _What is argv? How does it work?_
13. _What is a struct and why are they useful? Write a struct that represents
an employee where an employ has a name, department, title and number of years
on the job._ 
14. _What is a memory address?_
15. _What are pointers? How do we use them when programming in C?_
16. _What is memory?_
17. _How do we ask the operating system for memory using C?_
18. _What is a segmentation fault?_
19. _Describe what a memory leak is. How can we avoid them?_
20. _What does it mean to pass-by-reference?_
21. _What is the difference between the stack and the heap? How does C use these
data structures to perform memory management? You should explain, step-bystep,
the process and key functions used in C to accomplish this._

### Objective-C
1. _What are classes, what are objects? How are the two related?_

2. _What are methods?_

3. _What are the difference between class methods and instance methods?_

4. _What does it mean to send a message in Objective-C? Give an example of how this works._
5. _What are alloc and init? What are they used for? What C functions do they remind you of?_
6. _How does memory management work in Objective-C? How does it differ and/or
resemble memory management in C?_
7. _What is NSString? How is it different from a regular C string?_

8. _Name some ways that we can create arrays in Objective-C? How is this
different from how we create arrays in C?_

9. _Explain what properties are._
10. _What are instance variables?_
11. _Explain what self is._
12. _How does inheritance work in Objective-C?_
13. _How do we override methods?_
14. _Explain the "super" keyword._
15. _Explain the inheritance hierarchy._
16. _What are strong references?_
Strong means that you own the object that you will reference with this
property/variable. Compiler will make sure that any objects that you assign to
this property will not be destroyed as long as you point it with a strong
reference.
17. _What are weak references?_
Weak means that you dont want to have control over the object's lifetime. The
object is only "ali    ve" because another object holds a strong reference to
it. Once that is no longer the case, the object will be destroyed, and the
weak property will be set to nill.
18. _What are some ways that we can prevent memory leaks?_
19. _What are immutable objects in Objective-C? Name some immutable objects._
20. _What is the difference between an NSSet and an NSMutableSet?_
21. _What is the difference between NSDictionary and NSMutable Dictionary?_
22. _What are #import and #include used for?_
23. _What are global variables?_
24. _Explain what a callback is. How might callbacks be useful?_
25. _Explain what a block is, what would we use one for?_
26. _What are protocols? What do we use them for?_
Protocols declare methods that can be implemented by any class. Used to provide
a way for classes to share the same method and property declarations without
inheriting them.

Problem Solving

1) _Write a function that cubes the sum of three numbers and returns the
result. Please complete this problem using C._

Compile with ```$ gcc sumcubed.c -o sumcubed```
Run with  ```$ ./sumcubed```

The program asks the user to input three numbers when the program runs (not as command-line arguments).

```c
//
// sumcubed.c
// 
// Cube the sum of three numbers and return the results
//

#include <stdio.h>

int sumcubed(int a, int b, int c) {
    int d = a + b + c;
    return d * d * d;
}

int main (int argc, char **argv) {
    int x, y, z;
    printf("Three numbers, please:  ");
    scanf("%d%d%d", &x, &y, &z);
    int result = sumcubed(x, y, z);
    printf("Result:  %d\n", result);
    return 0;
}
```

2) _If we list all the natural numbers below 10 that are multiples of 3 or 5,
we get 3, 5, 6 and 9. The sum of these multiples is 23. Find the sum of all the
multiples of 3 or 5 below 1000. Please complete this problem using C._

Compile with ```$ gcc multsummed.c -o multsummed```
Run with  ```$ ./multsummed```

```c
//
// multsummed.c
//
// Find the sum of all the multiples of 3 or 5 below 1000
//

#include <stdio.h>

int multsummed(int limit) {
    int sum = 0;
    for (int i = 0; i < limit; i++) {
        if (i%3 == 0 || i%5 == 0)
            sum += i;
        // printf("%d %d\n", i, sum);
    }
    return sum;
}

int main(int argc, char **argv) {
    int result = multsummed(1000);
    printf("Result  %d\n", result); 
    return 0;
}
```

3) _Write a short program that reverses a string using Objective-C._

Three methods:
a) using char * and swapping the contents of the array indices
b) saving characterAtIndex as a NSString and replaceCharactersInRange for
NSMutableString version of string
c) declaring reversedString as NSMutableString type and appending the
characters from the original string backwards (by finding substring in the
range of original string's length - reversed string's length - 1

```objective-c
- (NSString *)reverseString1:(NSString *)aString {
    aString = [NSString stringWithFormat:@"%@", aString];
    NSUInteger length = [aString length];
    unichar *buffer = calloc(length, sizeof(unichar));
    [aString getCharacters:buffer range:NSMakeRange(0, length)];
    for (NSUInteger idx = 0; idx != length/2; idx++) {
        unichar temp = buffer[idx];
        buffer[idx] = buffer[length-idx-1];
        buffer[length-idx-1] = temp;
    }
    NSString *result = [NSString stringWithCharacters:buffer length:length];
    free(buffer);
    return result;
}

- (NSString *)reverseString2:(NSString *)aString {
    NSMutableString *mString = [NSMutableString stringWithFormat:@"%@", aString];
    NSUInteger length = [mString length];
    for (NSUInteger idx = 0; idx != length/2; idx++) {
        NSString *leftChar = [NSString stringWithFormat:@"%c", [mString characterAtIndex:idx]];
        NSString *rightChar = [NSString stringWithFormat:@"%c", [mString characterAtIndex:length-idx-1]];
        [mString replaceCharactersInRange:NSMakeRange(idx,1) withString:rightChar];
        [mString replaceCharactersInRange:NSMakeRange(length-idx-1,1) withString:leftChar];
    }
    return mString;
}

- (NSString *)reverseString3:(NSString *)aString {
    aString = [NSString stringWithFormat:@"%@", aString];
    NSMutableString *reversedString = [NSMutableString new];
    while ([aString length] != [reversedString length]) {
        NSRange range = NSMakeRange([aString length] -[reversedString length]-1, 1);
        [reversedString appendString: [aString substringWithRange:range]];
    }
    return reversedString;
}
```

4) _In Objective-C write a simple class that represents a student. A student
should have a first name, a last name, a major and a year (freshman, senior,
etc.). Your student class should have two methods. One that allows the student
to state his or her name and another that will allow the student to greet a
person given a name._

```objective-c
//
//  Student.h
//  CodestarsPS0
//
//  Created by Nina Baculinao on 6/8/15.
//  Copyright (c) 2015 Nina Baculinao. All rights reserved.
//

#import <Foundation/Foundation.h>

@interface Student : NSObject

@property (strong, nonatomic) NSString *firstName;
@property (strong, nonatomic) NSString *lastName;
@property (strong, nonatomic) NSString *major;
@property (strong, nonatomic) NSString *year;

- (id)initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName year:(NSString *)aYear andMajor:(NSString *)aMajor;
- (void)sayName;
- (void)sayHelloTo:(NSString *)name;

@end

//
//  Student.m
//  CodestarsPS0
//
//  Created by Nina Baculinao on 6/8/15.
//  Copyright (c) 2015 Nina Baculinao. All rights reserved.
//

#import "Student.h"

@implementation Student

//@synthesize firstName;
//@synthesize lastName;

- (instancetype) initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName year:(NSString *)aYear andMajor:(NSString *)aMajor {
    self = [super init];
    if (self) {
        _firstName = aFirstName;
        _lastName = aLastName;
        _year = aYear;
        _major = aMajor;
    }
    return self;
}

- (void)sayName {
    NSLog(@"%@: My name is %@ %@", _firstName, _firstName, _lastName);
}

- (void)sayHelloTo:(NSString *)name {
    NSLog(@"%@: Hello %@", _firstName, name);
}


@end

```
