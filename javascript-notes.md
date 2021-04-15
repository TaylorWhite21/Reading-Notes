# JavaScript Notes

- JavaScript - JavaScript is a scripting or programming language that allows you to implement complex features on web pages — every time a web page does more than just sit there and display static information for you to look at — displaying timely content updates, interactive maps, animated 2D/3D graphics, scrolling video jukeboxes, etc. — you can bet that JavaScript is probably involved. It is the third layer of the layer cake of standard web technologies, two of which (HTML and CSS) we have covered in much more detail in other parts of the Learning Area.
- conditionals - if statements
- operators - assignment operator, strict equal, +, -
- data types
    - number - 42
    - true or false
    - string - "42" "fourty-two" "" "any content mostly"
- variable - assigning variables
before you can use a variable, you need to announce that you want to use it. This involves creating the variable and giving it a name. Programmers say that you declare the variable

```
var today = new Date();
var hourNow = today.getHours();
var greeting;

if (hourNow > 18)
{
    greeting = 'Good Evening!';
}
else if (hourNow > 12)
{
    greeting = 'Good afternoon!';
}
else if (hourNow > 0)
{
    greeting = 'Good morning!';
}
else
{
    greeting = 'Welcome!';
}

document.write('<h3>' + greeting + '</h3>');
```
