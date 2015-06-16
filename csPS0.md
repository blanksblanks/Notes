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
Computer science is the theoretical study ("science") of what computation is and what
computers can do; it’s concerned with runtime complexity, NP-hard/complete
problem classification, compilers, etc. Programming is writing programs that do
what they have been designed to do and can be maintained. Both involve running some
algorithm, or set of instructions, on inputs, to produce some output.

2. _What is binary?_
Computers only understand zeroes and ones, an alphabet called binary. While
humans use decimal, which has 10 digits 0-9, computers only understand binary,
which has two digits, 0 and 1. With just two digits, we can still represent
almost every possible piece of information. Binary represents numbers in the
same pattern, but using powers of 2 instead of powers of 10 that decimal uses.
For instance, the number 2 can be represented in 4-bit form as 0010.

3. _What are bits?_
Bits (binary digits) are the smallest unit of storage in a computer, storing
data of a 0 or 1. With just 4 bits, we can represent 2^4 = 16 unique tokens.
If we were representing an unsigned int with 4 bits, the numbers could range
from 0 to 16. If we were representing positive and negative numbers with 4
bits using two's complement, we could represent the number range -8 - 7. 

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
If we implement a string as a list with indices 0-n where n is the string
length-1, for example 'hello' would be represented as:
```
[h][e][l][l][o]
 0  1  2  3  4
```
then this pseudocode can be used to reverse a string:
```
set index (of string) to 0
set length to length of string
while index < length/2:
(i.e. until we reach the middle of the string)
    swap the letter at the index and the letter at length - 1 - index
    (i.e. swap first letter and last letter)
    increment index (i.e. move on to the next letter)
```
More code-like pseudocode would look like below. Note it's written in Python
syntax but this code block would not run as Python strings are immutable.
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
could look like this.
adder.h
```c
#ifndef __MYADD_H__
#define __MYADD_H__
int add(int a, int b);
#endif
```
From our main.c, we can ```#include "adder.h"```, so the compiler can look at
the header file and know that a function called add exists. Then we can invoke
this method in our main file with ```int x = add(1, 2);```. As long as the
return type and argument types match, the compiler won't complain, so header
files are a useful way of sharing functions across files and error-checking.
Interestingly, if we don't actually implement the add function in adder.c, then
errors will only arise during the linking phase - for the compiler, knowing the
header declarations match the invocation in main.c would be enough.

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
data structures to perform memory management? You should explain, step-by-step,
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
In Objective-C, methods are object functions that are triggered by a message.

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
retain count of each object, and when an owner no longer needs an object, it
sends the message release or autorelease (release decremeent the retain count
immediately, while autorelease causes the message relrese to be sent when the
autorelease pool is drained), and when an object has a retain count of 0 i.e.
does not have any owners, it is deallocated (sent the message dealloc). So even
though it is automatically managed for you, the basic flow of alloc init and
dealloc in Objective-C is the same pattern of malloc and free in C memory
management. 

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
In C, we can create arrays in a number of ways. Since Objective-C is built on
top of C, all the C methods for array creation - using pointers and pointer
arithmetic or [] array notation works. Objective-C also introduces the NSArray
and NSMutableArray classes. The NSArray class creates an immutable array with
contents that cannot change without requesting new array. However, it can only
store objects, which means we need boxing for primitives (i.e. if we have a
float it needs to be converted into an NSNumber). NSMutableArray is a mutable
subclass of NSArray that can extend or shrink arrays, though some of its
methods may not be as efficient as a NSArray. While both NSArray and
NSMutableArray brings lots of high level functionality and methods, boxing can
be expensive, for graphics for example.

9. _Explain what properties are._
Properties is a convenience provided by Apple to simplify writing accessor
methods for a class. With a property, we can declare both the setter and getter
methods for a variable in one line. The syntax ```@property float
heightInMeters``` in the .h file and ```@synthesize heightInMeters``` in the .m
file essentially tell the compiler to synthesize default accessor methods based
on each @property declaration, so we do not have to manually write the same
repetive methods ```-(float) heightInMeters``` and ```-(void)
setHeightInMeters:(float)meters``` for each property - @property and
@synthesize do it for us! 

10. _What are instance variables?_
Instance variables are as the name suggests variables that belond to a certain
instance. Sometimes instance variables are primitive types, but are more
commonly pointers to other objects, so an object instance variables normally
points ot another objects and describes a realtionship to them. Object instance
variables can fall into three categories: a) object-type attributes: a pointer
to a simple value-like object like an NSString or an NSNumber b) to-one
relationships: a pointer to a single complex object, c) to-many relationships:
a pointer to an instance of a collection class, like an NSMutableArray

11. _Explain what self is._
self is a pointer to the object that is running the method, and we use it when
an object wants to send a message to itself (i.e. call its own method). For
instance, if we were making a game we could send the message ```[self
updateScore]```.

12. _How does inheritance work in Objective-C?_
In Objective-C inheritance, all objects either directly or indirectly are a
subclass of NSObject. All subclasses inherit allthe instance variables and
methods from its superclass. For example, NSArray is a subclass of NSObject,
and NSMutableArray is a subclass of NSArray. Therefore every instance of
NSMutableArray will have the instance variables and methods defined in itself,
in NSArray, and in NSObject.

13. _How do we override methods?_
When a message is sent, the search for the method of that name starts at the
object class and goes up the inheritance hierarchy, where the first
implementation is found is the one executed. Therefore, you can override
inherited methods simply by reimplementing it with your desired definition in
your new class. For example, if Employee inherits from Person, then you can
override a method by reimplementing it in your Employee class, and that
override the inherited method by the same name.

14. _Explain the "super" keyword._
The super directive means that the search for the method of that name starts at
the superclass rather than the class calling it, and use the implementation of
the superclass for that method. For example you can say ```[super
bodyMassIndex]``` in the Employee class, and it will run the bodyMassIndex
method from the Person class it is inheritng from. 

15. _Explain the inheritance hierarchy._
The inheritance hierarchy works as I described in q13 - when a message is sent,
the search for the method of the name starts at the object class, goes up to
its superclass, goes up the superclass of its superclass, and so on up the
inheritance hierarchy until it finds the first implementation of that method
and executes it. In short, the inheritance hierarchy starts at the base class,
and moves up the superclasses level by level. For example: Employee : Person :
NSObject.

16. _What are strong references?_
Strong means that you own the object that you will reference with this
property/variable. The compiler will make sure that any objects that you assign to
this property will not be destroyed as long as you point it with a strong
reference.

17. _What are weak references?_
A weak reference is a pointer that does not imply ownership. In other words,
weak means that you don't want to have control over the object's lifetime. The
object is only "alive" because another object holds a strong reference to
it. Once that is no longer the case, the object will be destroyed, and the
weak property will be set to nil. Weak references can help us fix retain cycle
issues. In a parent-child relationship, the general rule for preventing retain
cycles is that the parent owns the child, but the child should not own the
parent.

18. _What are some ways that we can prevent memory leaks?_
To find memory leaks in our program, we can use Instruments, the Apple
profiling tool, to monitor what is happening behind the scenes with our code
and the system during runtime. Instruments has a profiling instrument called
Leaks and Cycles which can show us what objects are still living on the heap
after the program runs or look for retain cycles respectively. We can preevent
memory leaks by using strong and weak references appropriately if we are (as we
usually are) using ARC. The chapters on Callbacks and Blocks in The Big Nerd
Ranch Guide to Objective-C Programming detail other tips for memory management
when using callbacks and blocks. For callbacks, there are three key rules to keep
in mind: a) notification centers do not own their observers; b) objects  do not own
their delegates or data sources, c) objects do not own their targets. In terms of
blocks, the block keeps a strong reference to any object it references, so any
objects referred to by the block are guaranteed to live as long as the block itself
- to avoid retain cycles and circular references, we can declare a __weak pointer
outside the block and reference the pointer within this block instead.

19. _What are immutable objects in Objective-C? Name some immutable objects._
Immutable objects are objects that cannot have their values changed. Immutable
objects include NSArray, NSString, NSSet, NSDictionary, NSAttributedString,
NSData, NSCharacterSet, NSIndexSet and NSURLRequest. Immutable objects exist
for at least two reasons, because you want to protect the data and disallow
people from changing it, and the next reason is performance: an immutable
object never needs to be copied. 

20. _What is the difference between an NSSet and an NSMutableSet?_
NSSet is an unordered collection of objects with unique elements, optimized for
memeber checking. So is NSMutableSet, which is a subclass of NSSet and inherits
all its methods, but in addition NSMutableSet has addition methods to change
the set, such as addObject, removeObject, and unionSet (to combine with another
set).

21. _What is the difference between NSDictionary and NSMutable Dictionary?_
Similar to the difference between NSSet and NSMutableSet, NSMutableDictionary
is a mutable subclass of NSDictionary, which allows you to add key-value
objects or delete them from the collection. NSDictionary and
NSMutableDictionary are essentially associative arrays with unordered
associations of key-value pairs. Interestingly, the keys and values can be any
object, so we can even, say map string commands to functions.

22. _What are #import and #include used for?_
#include and #import request that the preprocessor read a file and add it to
its output. #import ensures that the preprocessor only includes a file once.
#include allows you to include the same file many times, and is generally used
by C programmers, while Objective-C programmers tend to use #import. If the
header file you with to include is located in your project directory your wrap
the filename in "", while angle brackets indicate the header is in one of the
standard locations that the preprocessor knows about.

23. _What are global variables?_
Global variables are constant variables that can be used outside its local
scope, in a global scope, in other classes. You declare a global variable in
the .h file as in ```extern NSString const *NSLocaleCurrencyCode;``` and
defined in the .m file as in ```NSString const *NSLocaleCurrencyCode =
@"currency";```. Since this is part of the Foundation Framework, so long as you
import the Foundation Framework you can directly reference this global variable
NSLocaleCurrencyCode.

24. _Explain what a callback is. How might callbacks be useful?_
Callbacks allow other objects to call methods in response to events.
A callback in iOS is when NSRunLoop, which is waiting for an event to happen,
sends a message to another object when the event appens. There are three types
of callbacks: a) target-action: when x happens, send this message (action) to
this object (target), b) helper objects: when x happens, send a message to this
helper object (usually a delegate or data source) that conforms to your
protocol, c) notifications: when x happens, post a notification to the
notification center, and center forwards it to your object. The first kind is
useful for event-driven programming, allowing us to set up the program in a
cleaner way that separates the Model, View and Controller so users can click on
any element on the UI, like a button, and the appropriate object will be sent a
message. Callbacks is a useful mechanism for injecting behavior into
frameworks, because we could use the UIButton, which already has inherited the
concept of doing x when it is pressed - all we have to do is define what x is,
instead of define a whole new class. Asynchronous callbacks, like the example
of fetching data from a web server, are also very useful, because if we fetched
data synchronously, the function would block the main thread while waiting for
all the data to arrive, causing the UI to become unresponsive. By using
NSURLConnection aynchronously, we can start fetching and await callback as the
data arrives or fetch fails. Additionally, asynchronous callbacks can notify us
if the webserver wants credentials like a user name and password. In short,
target-action is useful for sending one callback to one object. Helper objects
are useful for sending an assortment of callbacks to one object. Notification
callbacks are useful in situations when the callback needs to go to multiple
objects (subscribers).

25. _Explain what a block is, what would we use one for?_
An Objective-C block is a chunk of code like a C function that can be passed
around as data. Blocks are like anonymous functions, closures or lambda
functions, and accomplish what function pointers in C do in an easier way to
read (for example they can be defined inline). They let you pass arbitrary
statements between objects, as you would data. As blocks are implemented as
closures, that means they also have to access to non-local variables, i.e.
outside the block itself (copied over as const variables like a snapshot,
though we can override the const copy behavior with a __block storage modifier
to capture the variable by reference rather than value). The syntax for
declaring a block variable looks a lot like C function pointers with a return
type, the name of the block variable (prefixed by a ^) and comma-delimited data
types for the arguments of the block, as in ```void (^devowelizer)(id,
NSUInteger, BOOL*)```. The data type for such a block would be void (^)(id,
NSUInteger, BOOL*). Blocks are useful as parameters for methods like NSArray's
enumerateObjectsUsingBlock or NSNotificationCenter's
addObserverForName:object:queue:usingBlock: or asynchronous data requestion
functions that will execute different blocks of code depending on whether the
outcome was 'success' or 'failure'. 

26. _What are protocols? What do we use them for?_
Protocols declare methods that can be implemented by any class. For example,
NSURLConnection has a list of method declarations (a protocol) that the helper
object can implement. Protocols are used to provide a way for classes to
share the same method and property declarations without inheriting them.
Protocols contain optional and required methods, and optional methods; so if an
object is to fulfill a certain role, like the data source of a UITableView
class, it must implement the required methods from the protocol.

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
