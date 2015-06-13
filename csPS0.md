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

6. _What are algorithms? Using pseudo code, write an algorithm that will reverse a string._
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
```
 char    1 byte
 short   2 bytes
 int     4 bytes
 float   4 bytes
 long    8 bytes
 doubl   8 bytes
 pointer 8 bytes
 struct  - varies depending on its components, for example a struct with a
           (x,y) coordinate where x and y are both ints would be 8 bytes
```
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
A function is a list of operations for the processor to execute. Every function
has a name, for example 'main'. Functions have at least three benefits:
reduction, reusability, and understandability. They can help us reduce
repetitive typing. They can also be reused in another program or class.
Finally, if there is a bug in numerous places but the problem lies in one
function, fixing that function can fix the problems wherever it is invoked. In
general, less code means less places for bugs to hide, and functions help you
prevent unnecessarily repeating yourself.

9. _Describe how strings are represented in C. What is the null terminator character?_
In C, strings are represented as character arrays containing the characters and
terminated with the null terminator character. The null terminator character is
represented as '\0' or 0 in the ASCII chart. The length of a C string can be
found by searching for the null terminator character. For example, the string
"Hello" would look like this in C representation: ['H','e','l','l','o','\0']

10. _What is an array? How are they represented in C? How are strings and arrays related in C?_
An array is an ordered list of objects that are all of the same size and type.
They are stored as a contiguous block of memory in C. The funny thing is their
semantic representation in C - how they are evaluated in expressions. Within
the local scope, you can have arrays, and use the sizeof operator to find the
size; but outside the local scope the array evaluates the address of its first
member. Therefore, in C arrays can be represented by the pointer to their first
member. Strings and arrays are related in C because strings are nothing more
than null-terminated char arrays.

11. _What does void represent?_
void represents nothing or no type. A function can look like ```void sayHi()```,
which indicates the function returns nothing. Typically, if the parentheses
were empty it would mean the function takes no parameters, but ```void sayHi(void)```
would do the same thing - declare a function that takes nothing and returns nothing.
Finally, we can also create generic data pointers with void as in ```void* p```
where p is a pointer to data of an unknown type (note this cannot be
dereferenced). 

12. _What is argv? How does it work?_
argv in c is the array of arguments being passed into your program from the
command line, while argc is the number of arguments being passed into your
program. Our main function can be defined as either ```int main(int argc, char
**argv)``` or ```int main(int argc, char *argv[])```, in other words, its type
is an array of char* (i.e. it is an array of strings). For example, if we have
a program myadd that took in two argv, then we could run the program with
```myadd 1 2``` and the program would access argv[1] and argv[2] (note argv[0]
is always the name of the program) in order to sum them up and deliver us the
result of 3.

13. _What is a struct and why are they useful? Write a struct that represents
an employee where an employ has a name, department, title and number of years
on the job._ 
A struct is an object that contains several related chunks of data, where
unlike an array the members of the struct do not all have to be the same type
and size. It is useful when you want to hold several chunks of data, or when
you do not care about the ordering of the components as in the example of a
struct Point p.x and p.y. Here is a struct that represents an employee:
```
struct Employee {
    char *name;
    char *department;
    char *title;
    int numberOfYearsOnTheJob;
}
```

14. _What is a memory address?_
Memory addresses is the location in memory where the value for a variable is
stored. To get the address of the variable we use the % operator, and the
string format specifier %p to print out the address - typically in hexademical
format.

15. _What are pointers? How do we use them when programming in C?_
Pointers are variables that store addresses (not values) and can be null. In C,
we use pointers as arrays, strings, and also for optimization. Perhaps you have
an object (perhaps large) that you do not want to copy all the time between
function calls, then you can just share the pointer at the same place in
memory. 

16. _What is memory?_
Memory, at the most basic level, are series of switches that contain one bit of
information and can be turned on and off. Programs typically run on high-speed
primary memory like RAM, while there exist secondary memory which provide
program and data storage. Every single process (i.e., a running program) gets
512GB of virtual memory space. If we were to draw it out, it would look like this:
```
                  512G ---------------------
                              stack
                       ---------------------
                                |
                                v
                                ^
                                |
                       ---------------------
                               heap
                       ---------------------
                          static variables
                       ---------------------
                           program code
                     0 ---------------------
```

17. _How do we ask the operating system for memory using C?_
We ask the operating system to allocate a buffer of memory for us in C using malloc().
When we are done with it, we call the function free() to release the memory and
return it to the heap. The heap refers to a region of memory separate from the
stack which is persistent even after the function ends.

18. _What is a segmentation fault?_
A segmentation fault (segfault) is an error caused by accessing memory that has
either not been assigned by the operating system or that the program is not
allowed to access. This can happen when you have an unintialized variable and
try to access its value.

19. _Describe what a memory leak is. How can we avoid them?_
A memory leak happens when you have allocated some memory but forgot to free
it, which is a resource leak that can impair performance. We can avoid them by
keeping track of all the variables that are allocated on the heap, and freeing
every single one of them.

20. _What does it mean to pass-by-reference?_
Pass-by-reference means to supply an address reference and the function puts
the data there. It stands in contrast to passing by value, which would copy new
data.

21. _What is the difference between the stack and the heap? How does C use these
data structures to perform memory management? You should explain, step-bystep,
the process and key functions used in C to accomplish this._
While the stack is a special region in your RAM that stores temporary variables
created by each function, and when the function exits, all the variables are
popped off the stack and lost forever. On the other hand, the heap is also a
special region in your RAM, but when the function exits the heap variables
remain until it is deleted by the programming; in other words, unlike stack
memory, heap memory is not managed for you, and you have to allocate space and
free it yourself. In multi-threaded applications, there is a different stack
for each thread, but different threads will share the heap. Another big
difference is that the stack is fixed in size, while the operating system can
add more memory to the heap, so the heap does not have a limit on memory size,
though it does suffer relatively slower access. As mentioned before, C
automatically handles memory for your stack variables, but C requires the
programmer to manually malloc() and free() heap variables. 


### Objective-C
1. _What are classes, what are objects? How are the two related?_
An object is like a struct in that it holds data, but it also contains
functions that act upon that data. A class is a specific type of object which
acts like a blueprint; it includes data, methods and instance variables where
an object of this type stores its data. You ask a class to create an object of
its type for you on the heap, and the result object is an instance of that class. 

2. _What are methods?_
In Objective-C, methods are functions that are triggered by a message.

3. _What are the difference between class methods and instance methods?_
Syntatically, class method begins with + while instance methods begin with -.
Class methods can be called on classes without needing an instance, for example
```[NSString stringWithString:@"Hello World"];```. Instance methods can only be
invoked on an instance of a class, for example ```[myStringInstance length]```.

4. _What does it mean to send a message in Objective-C? Give an example of how this works._
To invoke a function of an object, we send a message to the object. A function
that is triggeredby a message is more properly known as a method. The
message-sending syntax in Objective-C is a little unusual compared to other
programming languages in that it uses square brackets. An example of a message
could be ```[Person sayHello]``` where Person is the object you are sending a
message to and sayHello is the method you are calling.

5. _What are alloc and init? What are they used for? What C functions do they remind you of?_
alloc is a class method that returns a pointer to a new object that needs to be
initialized. init is the message that is sent to the new object in order to
initialize it. They are used to create objects in Objective-C, as in
```[[NSDate alloc] init];```. alloc and init are similar to malloc(), though we
do not have to worry about free() thanks to ARC.

6. _How does memory management work in Objective-C? How does it differ and/or
resemble memory management in C?_
Unlike C, Objective-C does not require manual memory management. It does not
use garbage collection like C# either. Instead, it uses a reference-counting
environment that tracks how many places are using an object. As long as there
is at least one reference to the object, the Objective-C runtime makes sure the
object will reside in memory. Automatic Reference Counting (ARC) is a recent
development in Objective-C (since Xcode 4.2), and prior to that we had to
manage ownership counting and memory management manually. Manual reference
counting is still available if you choose to turn off ARC. ARC manages the
owner count of each object, and when an object does not have any owners, it is
deallocated (sent the message dealloc). So even though it is automatically
managed for you, the basic flow of alloc init and dealloc in Objective-C is the
same pattern of malloc and free in C memory management.

7. _What is NSString? How is it different from a regular C string?_
NSString is an immutable Objective-C string class which is like an a glorified
C array with a ton of useful methods in its class definition. Unlike a C
string, we cannot change individual characters, and NSString will allocate a
new string for each change. Even if you assign the new string to the same
variable, new stirngs will still be generated behind the scenes. Some of its
useful methods include:
```
-(NSUInteger) length
-(unichar)characterAtIndex:(NSUInteger)theIndex
+(id)stringWithFormat:(NSString *)format ...
-(NSString *)stringByAppendingString:(NSString *)aString 
-(NSString *)stringByAppendingFormat:(NSString *)format ...
-(NSString *)lowercaseString
-(NSString *)substringWithRange:(NSRange)aRange
-(NSRange)rangeOfString:(NSString *)aString
-(NSString *)stringByReplacingOccurancesOfString:(NSString *)target withString:(NSString *)replacement
```

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
Weak means that you don't want to have control over the object's lifetime. The
object is only "alive" because another object holds a strong reference to
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

### Problem Solving

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
