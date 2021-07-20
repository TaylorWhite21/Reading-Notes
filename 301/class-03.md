# Passing Functions as Props

## Lists and Keys

[React Docs - lists and keys](https://reactjs.org/docs/lists-and-keys.html)

1. What does .map() return?
    - .map returns an array of the results
    <p>&nbsp;</p>
2. If I want to loop through an array and display each value in JSX, how do I do that in React?
    - Use the map function, return an <li> element for each item, and assign the array of elements to a variable.
    <p>&nbsp;</p>
3. Each list item needs a unique "key".

4. What is the purpose of a key?
    - A key is needed when creating lists of elements to identify which items have changed.
    <p>&nbsp;</p>


## Spread Operator

1. What is the spread operator?
    - A spread operator is an ellipsis of three dots "..." to expand ano bject into the list of arguments.  
    <p>&nbsp;</p>
2. List 4 things that the spread operator can do.
    1. Copy an array
    2. Use math functions
    3. Add and item to a list
    4. Combining objects
<p>&nbsp;</p>

3. Give an example of using the spread operator to combine two arrays.

    let pokemon = ['Pikachu', 'Snorlax' , 'Mewtwo']
    
    let morePokemon = [...pokemon]
    console.log(morePokemon)
    ```
    Returns 'Pikachu', 'Snorlax' , 'Mewtwo'
    ```
    pokemon[0] = 'Raichu'  
    console.log(...[...pokemon,'...',...morePokemon])
    ```
    Returns 'Pikachu', 'Snorlax' , 'Mewtwo', 'Raichu'
    ```
4. Give an example of using the spread operator to add a new item to an array.
```
    const fewFruit = ['🍏','🍊','🍌']
    const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
    console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]
```
5. Give an example of using the spread operator to combine two objects into one.
```
const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂
```

Code examples sourced from [How to Use the Spread Operator (…) in JavaScript](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)

## [How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)


1. In the video, what is the first step that the developer does to pass functions between components?
    - Create a function where the state is.
2. In your own words, what does the increment function do?
    - Increment increases a count by the chosen amount.
3. How can you pass a method from a parent component into a child component?
    - this.(*method name*)
4. How does the child component invoke a method that was passed to it from a parent component?
    - this.props.(*method name*)

## Things I want to know more about
