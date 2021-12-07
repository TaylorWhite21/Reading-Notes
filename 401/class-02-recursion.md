# Recursion

Recursion is when a function calls itself directly or indirectly.

[Towers of Hanoi](https://www.geeksforgeeks.org/c-program-for-tower-of-hanoi/) is an example of a problem that can be solved using recursion.

### Example of recursive version 
 - This is possible because the factorial of a number is one less that itself(n-1).

Problem: Solve factorial(4) recursively.

```
int factorial (int n)
{
  if (n == 1) return 1;
  else
  return n*factorial(n-1);
}
```
 - When the code is ran, once it reaches the second return, it calls itself again but now 'n' is equal to (n-1), so you would get a different answer each time.

A further explanation for this is when a main program is run and asked to figure out factorial 4 is, it needs to know what factorial 3 is. To know what factorial 3 is, it needs to know what factorial 2 is. Once it reaches factorial 1 the if statement becomes truthy and returns 1.

Once 1 is returned, 2 now knows that it is 2 * the factorial(which is one). Then can multiply by 2 to make 6. It then sends that to factorial 4 which multiplys by factorial 3's reult of 6 totalling 24.
