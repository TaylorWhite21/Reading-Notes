# React and Forms

# [React Docs - Forms](https://reactjs.org/docs/forms.html)

1. What is a ‘Controlled Component’?
    - It renders form elements and controls them by keeping the data in the components state.
    <p>&nbsp;</p>
2. Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
    - You should wait until they submit the form because they may have entered the information wrong.
    <p>&nbsp;</p>
3. How do we target what the user is entering if we have an event handler on an input field?
    ``` 
     event.target.name
    ```


1. Why would we use a ternary operator?
    - To make code smaller and more readable

2. Rewrite the following statement using a ternary statement:
```
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
  ```
    - x===y ? console.log(true) : console.log(false)
