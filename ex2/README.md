#Formatted Printing

#Exmaple
```
#include<stdio.h>

int main(int argc, char *argv[])
{
	int age = 23;
	float height = 5.7;

	printf("I am %d years old.\n",age);
	printf("I am %0.f inches tall.\n", height);

	return 0;
}
```

# Code Break Down
  1. including header file stdio.h telling compiler that you are going to use standard input/output functions. one of thos is printf
  2. define integer variable age to 23
  3. define floate variable height to 5.7
  4. then we use printf function to print age and height 
  
