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

# Hello World

Simple hello world program to see how it works

`main()` function is reserved in C, All C programm must have 
`main()` function, it's where execution begins 

 - Example :
	```
	int main(int argc, char ** argv ){
		printf("Hello World\n");
		return 0;
	}
	```
 - Explanation :
	- 1. init 
		main function should return, so we use int, it will
	 	return intenger. 

	- 2. (int argc, char ** argv)
		This are use for variable for parameter for
		pass this function, this veriable accesseble 
		inside the body of this function.

	- 3. {} 	
		Begening and Ending of block of code 
		that is body of this function. 

	- 4. return statement 
		exit status of function, if return not define
		then it will use return status of printf()
		funtion

	- 5. ; semicolon 
		it's not optional, it's must 
		all statement in C must be terminated with 
		semicolon  

	- 6. white spaces
		this are optional but we used this for
		indentation and improve readability of
		the code.




