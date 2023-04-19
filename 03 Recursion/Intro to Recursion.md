# Introduction to Recursion

## What is recursion?
Recursion is a technique in programming where a function calls itself repeatedly until a certain condition is met.

Think of it like solving a puzzle. When ou have a big puzzle with many pieces, it's easiest if you solve it by breaking it down into smaller puzzles. You group pieces together into small groups, and then those groups start accumulating into something bigger. If you keep solving these smaller puzzles, eventually you will have solved the entire big puzzle.

Recursion works in a similar way. A function is like a puzzle, and you want to solve it by breaking it down into smaller problems that are similar to the original problem. You start by solving one small problem, and then move on to solving another small problem. If you keep solving these smaller problems, eventually you will solve the original problem.

For example, let's say you want to write a program that calculates the factorial of a number. The factorial of a number is the product of all positive integers up to and including that number. We can use recursion to solve this problem by breaking it down into smaller problems.

### Example
```
#include <iostream>
using namespace std;

int factorial(int num) {
  if (num == 0) 
  {
    return 1;
  }
  return num * factorial(num-1);
}

int main() {
  int result = factorial(3);
  cout << result;
  return 0;
}
```

### Output
```
6
```

### Visualization
![image](https://user-images.githubusercontent.com/111817058/232958410-5044204c-b636-480a-95cb-d0ea7ded314d.png)

### What is a base case?
In C++ recursion, the base case is a condition that defines when the recursive function should stop calling itself and return a result. In other words, it is the simplest case that does not require further recursion. The base case is an essential component of a recursive function because without it, the function would keep calling itself indefinitely, resulting in an infinite loop. The base case in the above example is ```if (num == 0)```.

## Exercises
**1.** Explain recursion.

**2.** Write a recursive function that prints the even numbers from 1 to n. n is any number passed to the function.

**3.** Write a C++ function that takes two integers base and exp as input and returns base raised to the power of exp using recursion. For example, if base is 2 and exp is 3, the function should return 2 * 2 * 2 = 8.

**4.** Write a recursive function that calculates the greatest common divisor (GCD) of two numbers a and b.
