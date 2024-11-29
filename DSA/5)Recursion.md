Application 
	used in Dynamic Programing , backtracking ,Divide and Conquer (merge, quick sort )
# Operations That Can Be Performed Using Recursion

- **Mathematical Operations**:
  - Factorial calculation
  - Fibonacci sequence
  - Power of a number
  - Greatest Common Divisor (GCD)

- **Divide and Conquer Algorithms**:
  - Binary search
  - Merge sort
  - Quick sort

- **Tree and Graph Traversal**:
  - Binary tree traversal (in-order, pre-order, post-order)
  - Depth-First Search (DFS)

- **Backtracking Problems**:
  - N-Queens problem
  - Sudoku solver
  - Subset generation
  - Permutations and combinations

- **Dynamic Programming**:
  - Solving overlapping subproblems
  - Memorization techniques

- **String Operations**:
  - Palindrome checking
  - String reversal
  - Pattern matching

# General things about recursion
### What is base case in recursion

In a recursive program, the solution to the base case is provided and the solution of bigger problem is expressed in terms of smaller problems.

```cpp
int fact(int n)  
{  
    if (n < = 1) // base case  
        return 1;  
    else      
        return n*fact(n-1);      
}
```

I think base case provide exception and end condition. i.e when to stop calling the function again and again

![[Pasted image 20241023090015.png]]

### Why Stack Overflow error occurs in recursion?

If the base case is not reached or not defined, then the stack overflow problem may arise. Let us take an example to understand this.

```cpp
int fact(int n)  
{  
    // wrong base case (it may cause  
    // stack overflow).  
    if (n == 100)   
        return 1;  
  
    else  
        return n*fact(n-1);  
}
```
If fact(10) is called, it will call fact(9), fact(8), fact(7), and so on but the number will never reach 100. So, the base case is not reached. If the memory is exhausted by these functions on the stack, it will cause a stack overflow error.

### How memory is allocated to different function calls in recursion?

When any function is called from main(), the memory is allocated to it on stack. A recursive function calls itself, the memory for the called function is allocated on top of memory allocated to the calling function and a different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues. Let us take the example of how recursion works by taking a simple function:

```cpp
void printFun(int test){  
  
    if (test < 1)  
        return;  
  
    else{  
        print test;  
        printFun(test-1);    // statement 2  
        print test;  
        return;  
    }  
}  
// Calling function printFun()  
int test = 3;  
printFun(test);
```
****Output****

:

3 2 1 1 2 3  

When

****printFun(3)****

is called from main(), memory is allocated to

****printFun(3)****

and a local variable test is initialized to 3 and statement 1 to 4 are pushed on the stack as shown in below diagram. It first prints ‘3’. In statement 2,

****printFun(2)****

is called and memory is allocated to

****printFun(2)****

and a local variable test is initialized to 2 and statements 1 to 4 are pushed in the stack. Similarly,

****printFun(2)****

calls

****printFun(1)****

and

****printFun(1)****

calls

****printFun(0)****

****printFun(0)****

goes to if statement and it returns to

****printFun(1)****

. Remaining statements of

****printFun(1)****

are executed and it returns to

****printFun(2)****

and so on. In the output, values from 3 to 1 are printed and then 1 to 3 are printed. The memory stack has been shown in below diagram.

![recursion](https://media.geeksforgeeks.org/wp-content/cdn-uploads/recursion.jpg)


### Advantages and disadvantages of recursion
**Disadvantage* of Recursion**
: Note that both recursive and iterative programs have the same problem-solving powers, i.e., every recursive program can be written iteratively and vice versa. Recursive program has greater space requirements than iterative program as all functions will remain in the stack until the base case is reached. A recursive program also has greater time requirements because of function calls and return overhead.
**Advantages of Recursion**
: Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals, Tower of Hanoi, etc. For such problems, it is preferred to write recursive code. We can write such codes also iteratively with the help of the stack data structure

## Tail recursion
As we read before, that recursion is defined when a function invokes/calls itself.  
  
**Tail Recursion**: A recursive function is said to be following Tail Recursion if it invokes itself at the end of the function. That is, if all of the statements are executed before the function invokes itself then it is said to be following Tail Recursion

```cpp
// This is a Tail Recursion
void printN(int N){
    if(N==0)
        return;
    else
        cout<<N<<" ";
    printN(N-1);
}
```

# Types of problems

## Basic Problem on recur
