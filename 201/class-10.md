# class 10
## Javascript Debugging

There are many tools to help you debug your code when it goes wrong or even if you anticipate trouble. Once such tool that is a very good place to start looking for errors is at the browser developer tools. Below is an example of Chrome's built in browser developer tools. 
![](https://developers.google.com/web/tools/chrome-devtools/javascript/imgs/line-of-code-breakpoint.png)

It may also be helpful to use `console.log()` to test inputs or variables within your code. This can help you discover broken code that isn't passing data or smaller errors that can use this type of trace method to catch the bug.

Javascript has ways of handling debugging throw conditional statements known as try catch blocks.

```js
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "is empty";
    if(isNaN(x)) throw "is not a number";
    x = Number(x);
    if(x > 10) throw "is too high";
    if(x < 5) throw "is too low";
  }
  catch(err) {
    message.innerHTML = "Error: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
} 
```
