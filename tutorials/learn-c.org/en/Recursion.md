Tutorial
--------
 
Recursion occurs when a function contains within it a call to itself. Recursion can result in very neat, elegant code that is intuitive to follow. It can also result in a very large amount of memory being used if the recursion gets too deep.
 
Common examples of where recursion is used :
 
* Walking recursive data structures such as linked lists, binary trees, etc.
* Exploring possible scenarios in games such as chess
 
Recursion always consists of two main parts. A terminating case that indicates when the recursion will finish and a call to itself that must make progress towards the terminating case.
 
For example, this function will perform multiplication by recursively adding :

    #include <stdio.h>

    unsigned int multiply(unsigned int x, unsigned int y)
    {
        if (x == 1)
        {
            /* Terminating case */
            return y;
        }
        else if (x > 1)
        {
            /* Recursive step */
            return y + multiply(x-1, y);
        }
 
        /* Catch scenario when x is zero */
        return 0;
    }

    int main() {
        printf("3 times 5 is %d", multiply(3, 5));
        return 0;
    }
 
Exercise
--------
 
Define a new function called `factorial()` that will compute the factorial by recursive multiplication (5! = 5 x 4 x 3 x 2 x 1). Note that by convention, the factorial of 0 is equal to 1 (0! = 1).
 
Tutorial Code
-------------

    #include <stdio.h>

    int main() {
        /* testing code */
        printf("0! = %i\n", factorial(0));
        printf("1! = %i\n", factorial(1));
        printf("3! = %i\n", factorial(3));
        printf("5! = %i\n", factorial(5));
    }
    
    /* define your function here (don't forget to declare it) */

Expected Output
---------------

    0! = 1
    1! = 1
    3! = 6
    5! = 120

Solution
--------

    #include <stdio.h>

    int factorial(int number);

    int main() {
        /* testing code */
        printf("0! = %i\n", factorial(0));
        printf("1! = %i\n", factorial(1));
        printf("3! = %i\n", factorial(3));
        printf("5! = %i\n", factorial(5));
    }

    int factorial(int number) {
        if (number > 1) {
            return number * factorial(number-1);
        }
        else {
	           return 1;
        }
    }
    
Exercise
--------
 
Define a new function called `fib(int n)` that will compute the fibonacci number at the passed index to the function by recursive addition. Note that the fibonacci sequence starts like this 0,1,1,2,3,5,8... Which basicly adds the previous two numbers to get the next number so first we add 0+1 to get the third index number and then 1+1 we will get the fourth index number and so on.
 
Tutorial Code
-------------

int main(){
  /*Testing the function and printing the results*/
  printf("fib of(0) is %d\n", fib(0));
  printf("fib of(1) is %d\n", fib(1));
  printf("fib of(2) is %d\n", fib(2));
  printf("fib of(3) is %d\n", fib(3));
  printf("fib of(4) is %d\n", fib(4));
  printf("fib of(5) is %d\n", fib(5));
  printf("fib of(6) is %d\n", fib(6));
  printf("fib of(7) is %d\n", fib(7));
  printf("fib of(8) is %d\n", fib(8));
  printf("fib of(9) is %d\n", fib(9));
}

Expected Output
---------------

    	fib of(0) is 0
	fib of(1) is 1
	fib of(2) is 1
	fib of(3) is 2
	fib of(4) is 3
	fib of(5) is 5
	fib of(6) is 8
	fib of(7) is 13
	fib of(8) is 21
	fib of(9) is 34


Solution
--------

#include <stdio.h>

int fib(int n){
  /*base case or sometimes callled stopping condition*/
  /*if the index is below zero return 0*/
  if(n<=0)
    return 0;
  /*and the other base case is when the index is 1 return 1*/
  else if (n==1){
    return 1;
  }
  /*otherwise compute the sum of the previous two numbers */
  else
    return fib(n-1)+fib(n-2);
}

int main(){
  /*Testing code*/
  printf("fib of(0) is %d\n", fib(0));
  printf("fib of(1) is %d\n", fib(1));
  printf("fib of(2) is %d\n", fib(2));
  printf("fib of(3) is %d\n", fib(3));
  printf("fib of(4) is %d\n", fib(4));
  printf("fib of(5) is %d\n", fib(5));
  printf("fib of(6) is %d\n", fib(6));
  printf("fib of(7) is %d\n", fib(7));
  printf("fib of(8) is %d\n", fib(8));
  printf("fib of(9) is %d\n", fib(9));
}
