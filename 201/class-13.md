# Local Storage


Storing objects into local memory can be done in a few easy steps. Declaring a new variable and assigning the JSON to stringify method to convert the object, in this case, an array, into a stringy.

```js
var stringyPotatoCollection = JSON.stringify(Potato.collection);
localStorage.setItem('storedPotatoes', stringyPotatoCollection);
```

After stringifying your array you can then collect the information from storage with the getItem built-in method. Parsing the information from JSON into a language Javascript can understand comes after that. Finally, you are free to manipulate the data.

```js
var stringyPotatoesFromStorage = localStorage.getItem('storedPotatoes');
var potatoesFromStorage = JSON.parse(stringyPotatoesFromStorage);
console.log('potatoes from storage: ', potatoesFromStorage);
```
