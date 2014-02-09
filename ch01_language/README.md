Study C Programming at Home by Rahul Patil 
Date : Sat Feb  8 15:14:21 IST 2014

# Comments

Comment is introduce by // sign

 - Examples :

	- `// single line comment` 

	- `/* multiline 
	   comment */`

 - Information :
	- /* comment */ is old style and // is new style
	- // is boroed from c++ and added in c99 standard
	
***

# Hello World

Simple hello world program to see how it works

`main()` function is reserved in C, All C programm must have 
`main()` function, it's where execution begins 

 - Example :
````
	int main(int argc, char ** argv ){
		printf("Hello World\n");
		return 0;
	}
````
 - Explanation :
 
	1. `init` 	
		* main function should return, so we use int, it will
	 	  return intenger. 

	2. `(int argc, char ** argv)`

		* This are use for variable for parameter for
		  pass this function, this veriable accesseble 
		  inside the body of this function.

	3. `{}` 	
		* Begening and Ending of block of code 
		  that is body of this function. 

	4. `return` statement 
		* exit status of function, if return not define
		  then it will use return status of printf()
		  funtion

	5. `;` semicolon 
		* it's not optional, it's must 
		  all statement in C must be terminated with 
		  semicolon  

	6. white spaces
		* this are optional but we used this for
		  indentation and improve readability of
		  the code.

***
# IDENTYFIER 

 - It's an token for recognize your variables or function
   We can use ACSI Representable, ISO Latin alpabet 
   both A-Z and a-z

 - it may not begin with number
	
 - Identifier may not conflict with reseverd keyword
   43 keyword reserve in C like for,while,do etc

 - It's case sensetive 
	
 - Identifer start with single underscore is used for 
   `_private_indentifier`

 - Double and more initial underscore for system level
   use example  `__system_use_only`

***
# VARIABLES
 - Variables is strongly typed in C
 - It should declare with it's type 
 - It should declare before it use
 - Examples : 
    - `int i; //this is undefine var` 
    - `int i = 0; //define var`
 - Scope :
    - Variables available in same block where they declare 
 
***

# STDOUT STDERR

`printf()` commonly used for stdout, but if you want to send stderror 
to stdout, then you can use `fprintf()` function 

 - Examples :
    - `fprintf(stdout, "Hello World\n");`
    - `fprintf(stderr, "Error: file not found\n");`
    
 - Information 
    - stdout is buffured and stderror not get bufferd in *nix systems
      so it can be possible that stdout display 1st than stderror 

***
# STDIN

User input for console base application `fgets()` function commonly used. 

 - Example :
````
	#include <stdio.h>
	
	enum { max_string = 127 };
	static char string[max_string + 1 ] = "";
	
	int main(){

		printf("Enter a String: "); 
		fgets(string, max_string, stdin);
		printf("The string is %s\n",string);
		return 0;
	}
````	
  - Information :
     - Previously mostly uses `gets()`, but not it's old, use `fgets()`
       instead of `gets()`
     - There is another function called `scanf()` and the difference is 
        - `fgets()` can read from any open file, but `scanf()` only reads standard input.
        - `fgets()` reads 'a line of text' from a file; `scanf()` can be used for that but also handles conversions from string to built in numeric types.

***
# Pointers 

 - Definition: 
    - A pointer is a variable containing the address of another variable
 - Why use ?
    - Pointers allow you to refer to the same space in memory from multiple locations. This means that you can update memory in one location and the change can be seen from another location in your program. You will also save space by being able to share components in your data structures.
    - You should use pointers any place where you need to obtain and pass around the address to a specific spot in memory. You can also use pointers to navigate arrays:
    - An array is a block of contiguous memory that has been allocated with a specific type. The name of the array contains the value of the starting spot of the array. When you add 1, that takes you to the second spot. This allows you to write loops that increment a pointer that slides down the array without having an explicit counter for use in accessing the array.
    - Pointers are useful where you require high performance and/or compact memory footprint.

### To understand Pointers, we first need to understand how variables works

when you declare variable is typed and named location in memory 

Example : `int x;`

It's declare variable and associate with name `x` and memory is allocated of size of integer data type 

`x = 1;`  

then we place value 1 in memory location associate with the integer variable `x`

`int y = x;`

this is both declaration and assignment, memory is allocated of size of int and 
value from variable `x` copied into the variable name `y` .

Now `y` contains separate integer in the separate memory location of the same value. 


C syntax gives to the ability to create a variable that is pointer to the value.

`int *ip;`

thsi is pointer declaration the variable `ip`  is of the type pointer to int,
here is memory is allocated size of pointer and type int, it's refer to intenger pointer. 

`ip = &x;`

this is address of access placed in pointer variable named `ip` , the `&` is called reference operator.
so this statement assign the address of `x` to integer pointer `ip`. 
integer pointer `ip` now points to integer variable `x` 

`int y = *ip`
this statement copy the value pointed by `ip` which currently points to the integer varialbe `x` to the 
integer varialbe `y`

***

# Array

 - Declaring array : 
     -  `type array_name[size_of_array]`
	 
 - Example : 
     - `int ia[5];` 
		- this declare the arrays of integer with size of 5 
	 - `ia[0] = 1;`
		- the first element always start from zero, this assign value `1` to 
		  the first element of the arrays
	 - `int *ip = ia;`
		- this declares the integer pointer and assigns the address of the arrays 
		- we don't need to use `&` to assign arrays address 
	 - `*ip = 2;`
		- this assign the value 2 to first element of array i.e `ia[0]`
	 - `++ip;`
		- we can increment pointer and it will point to second element of the array 
		- so after `++ip;` and `*ip = 3;` this will assign value 3 in third element of array
	 - `*(++ip) = 4;`
		- this is common technique in C. here will increment the pointer and using it same time. 
		- it's an short-cut of previous two steps 
		

 - Example 
 
	- `char s[] = { 's','t','r','i','n','g', 0 };`
	    - We don't have define size of array  i.e `s[]` 
		- Traditional string in C and C++ uses null terminator(i.e `0` ) to indicate the end of the string . 
	-  `char s[] = "string"; `
		- also we can define array as above 
		
 - Example loop through array 
 
````
#include <stdio.h>

int main(){

	char s[] = "string";
	int i;
	for ( i=0; s[i] != 0; ++i ) {
		printf("this is char %s\n", s[i] );
	}
	return 0;
}

````
		
 - Example loop through array using array pointer 
 
````
#include <stdio.h>

int main(){

	char s[] = "string";
	char *cp = s;
	for ( *cp; *cp; ++cp ) {
	
		printf("this is char %c\n", *cp );
	
	}
	return 0;
}

```` 
	
	 




