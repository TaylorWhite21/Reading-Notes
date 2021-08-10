## [Understanding the JavaScript Call Stack](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/)  

1. What is a ‘call’?
    - A call is the order in which code is executed.

2. How many ‘calls’ can happen at once?
    - Only one call can happen at a time.
3. What does LIFO mean?
    - Last in, First Out - it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

4. Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

```
    function firstFunction(){
  throw new Error('Stack Trace Error');
}

function secondFunction(){
  firstFunction();
}

function thirdFunction(){
  secondFunction();
}

thirdFunction();
```
5. What causes a Stack Overflow?
    - This occurs when there is a function that calls itself.

## [JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

1. What is a ‘refrence error’?
    - Occurs when a variable is trying to be used without being declared.  
2. What is a ‘syntax error’?
    - Occurs when there is code that cannot be parsed due to syntax. 
3. What is a ‘range error’?
    - Occurs when you try to manipulate an object and give it an invalid length. 
4. What is a ‘type error’?
    - Occurs when the types that are being used are incompatible. e.g. Trying to access an undefined variable.
5. What is a breakpoint?
    - Makes a program stop at the designated point.  
6. What does the word ‘debugger’ do in your code?
    - It sets a breakpoint at its location.

