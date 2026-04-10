# C Programming

In the following code block we have a number of components to discuss. They are as follows:

> /**/ - this acts as a multi line comment, and everything within its bounds is ignored by the compiler
> 

> #include - this tells the C preprocessor to copy the content of the file into the file it is used in. In this instance it is placing the content of the stdio.h file into the main file
> 

> In C if you leave the function parameters empty, the compiler assumes the function takes any number of unspecified arguments so when you call the function it won’t enforce any checks. This is risky so void is used to explicity state that it takes no arguments;.
> 

```c
/*
Simple program to output Hello World to the terminal
*/
#include <stdio.h>

int main(void){
printf("Hello World");
}
```

Note: The C compiler transforms the source code into machine code which is pure binary(0 an  1s)

## Building with gcc

```c
gcc -o output main.c
```

gcc - the command to initiate the compilation

-o - the flag that tells gcc what the name of the binary should be 

main.c - the source code you are compiling

## Memory

For the sake of understanding lets think of memory as an array of bytes.

Bytes are 8 bits

Each of these bytes can be indexed given its an array, and indexing is done via its memory address

```c
[0x3A, 0xFF, 0x00, 0x7C, 0x12]
```

## Variables

As we’ve correctly identified memory as an array of bytes which are accessible via indexing we need to address another problem. 

Since working directly with raw addresses is difficult for humans, programming languages introduce variables as symbolic names that refer to locations in memory, allowing us to work with values instead of raw addresses.

```c
int age = 21;
```

When you don’t initialize variables their value is indeterminate and should not be assumed to equal 0

```c
/*
pi doesn't evaluate to 0, but some undetermined value
*/
float pi;
```

## Ternary Operator

In C we have the ternary operator ‘?’: it is used as a shorthand version of if-else statement.

The conditional must come before the ternary operator and then the statement to be evaluated comes after that and then a column that precedes the statement that evaluates in case the conditional is false.

```c
float mark = 95;
char* score = mark>80 ? "A" : "Not A";
```

## Sizeof Operator

The sizeof operator is meant to return the number of bytes needed to store a certain datatype.

Be mindful because it returns a type of “size_t” and not an int.

Size_t is used to represent size in bytes of any object in memory on a given system

## Functions

Functions are blocks of statements that can be executed without retyping all the statements 

The first line that contains int add_ages is the function definition

Functions must have their return type and their name specified in their definition as well as their parameters

Parameters are local variables that arguement values are copied into

```c
int add_ages(int myage, int hisage) {
		return myage + hisage;
}
```

### Function Prototype

Typically you cannot call a function if the compiler has not seen its definition.

The following code will give an error as at the time the functin return_age() is called it has not been defined.

```c
int main(void) {

int x = return_age();

int return_age() {
return 21;
}
}
```

However there are ways around this, imagine you have the function definition in another file, how do we let the compiler know not to throw an error?

We use function prototypes - these are function declarations (just the return type and the parameters) then use the function and the define it .

```c
int main(void){
int return_age(char* student);

int student_age = return_age("Brigidi");

int return_age(char* student) {
return 21;
}
}
```

## Pointers

Remember how we spoke about how memory can be understood as an array of bytes, where each byte can be accessed by some number/index which is understood as the memory address.

Though the topic of pointers is often assoicated with Armageddon, it is quite simple really.

A pointer is simply a variable that holds a memory address

# Gotchas!

1. Initialized variables that are used may bring about undetermined behavior because as we noted they do not always resolve to 0
2. Expressions evaluate to their assignment, so if we have y=5 in an if() it will execute as True
3. Scoping - inner scopes can access variables in the outer scopes but the reverse is not True
4. Integer Underflow - unsigned integers cannot be negative so if they go below 0 expect integer underflow
5. Integer Overflow - signed integers cannot go below or above a certain number so when you add to them they might overflow and the 1 bit will wrap around and turn all bits to 0 except the most significant bit resulting in a large negative number