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

***





