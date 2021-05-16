# 07 HTML Table JS Constructor Functions

### Creating an object literal using a function
You can create an object literal using a function and calling it with a new variable call of the function while passing in the parameters.
```js
function makePotato(name, minPotatos, maxPotatos, averagePotatos){
  var newPotato = {
    name : name,
    minPotatos : minPotatos,
    maxPotatos : maxPotatos,
    averagePotatos : averagePotatos,
    
    getHourlyPotatos: getHourlyPotatos,
    getPotatoSum : getPotatpSum,
    renderToPage : renderToPage,
    dailyTotalPotatos : dailyTotalPotatos
  }
  return newPotatos;
}
```
New variable instantiation with parameters.
```js
var potatoPotato = makePotato('Russett', 2, 18, 4);
```
You can also create constructor functions that act the same way however is purpose-built by JavaScript.
```js
function Potato(name, minPotato, maxPotato, averagePotato) {
  this.name = name;
  this.minPotato = minPotato;
  this.maxPotato = maxPotato;
  this.averagePotato = averagePotato;
}
```
This created the Constructor which is designed to take in parameters and construct an object around it.
The constructor can still use function calls with ***Prototypes***.
```js
Potato.prototype.renderPotato = renderPotato;
```
this will access a `function renderPotato(){}` and apply a new instance to the new object.
Objects are instantiated by assigning a new constructor such as: 
```js
var morePotatos = new Potato('Russett', 2, 17, 4);
```
