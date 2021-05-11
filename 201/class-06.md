 
#### getElementByld()
```
Uses the value of an element's 
id attribute (which should be 
unique within the page). 
```
#### querySelector() 
```
Uses a CSS selector, and returns 
the first matching element. 

You can also select individual 
elements by traversing from one 
element to another within the 
DOM tree (see third column). 
```

#### getElementsByClassName()
``` 
Selects all elements that have 
a specific value for their cl ass 
attribute. 
```
#### getElementsByTagName() 
```
Selects all elements that have the 
specified tag name.
```
#### querySelectorAll() 
```
Uses a CSS selector to select all 
matching elements. 
```


You can move from one element 
node to a related element node. 

#### parentNode 
```
Selects the parent of the current 
element node (which will return 
just one element). 
```
 
#### previousSibling / nextSibling 
```
Selects the previous or next 
sibling from the DOM tree. 
```

#### firstChild / lastChild 
```
Select the first or last child of the 
current element.
```

Several methods let you create 
new nodes, add nodes to a tree, 
and remove nodes from a tree:

1. create Element() 
2. createTextNode() 
3. appendChild() / removeChild() 
This is called DOM manipulation.

#### lets you get or update the value of the class and id attributes.
``` 
hasAttribute() - Checks if an attribute exists.
getAttribute() - Gets its value.
setAttribute() - Updates the value.
removeAttribute() - Removes an attribute.
```

#### getElementsByTagName('h1') 
```
Even though this query only 
returns one element. the method 
still returns a Nodelist because 
of the potential for returning 
more than one element. 
INDEX NUMBER - 0
ElEMENT - <h1> 
```

#### getElementsByTagName('li') 
```
This method returns four 
elements, one for each of the 
<li> elements on the page. 
They appear in the same order 
as they do in the HTMl page. 
INDEX NUMBER - ElEMENT 
0 - <li i d•"one" class="hot"> 
1 - <1 i i d="two" class="hot"> 
2 - <l i id="three" class= "hot"> 
3 - <li id="four"> 
```

#### getElementsByClassName('hot')
``` 
This Nodelist contains only 
three of the <li> elements 
because we are searching for 
elements by the value of their 
class attribute, not tag name. 
INDEX NUMBER - ElEMENT 
O - <li id="one" cl ass="hot"> 
1 - <li id=" two" class="hot"> 
2 - <l i id=" three" class="hot"> 
```
#### querySelectorAll('li[id]')
``` 
This method returns four 
elements, one for each of the 
<li> elements on the page that 
have an id attribute (regardless 
of the values of the id attributes). 
INDEX NUMBER - ElEMENT 
O - <li id="one" class="hot"> 
1 - <li id="two" class="hot"> 
2 - <li id="three" class="hot"> 
3 - <li id="four"> 
```

#### SELECTING ELEMENTS USING CLASS ATTRIBUTES
```
var elements = document .getEl ementsByClassName('hot'); // Find hot items 
if (elements.l ength> 2) {  // If 3 or more are found
  var el = elements[2]; //Select the third one from the Nodelist
  el.className = 'cool'; //Change the value of its class attribute
} 
```

#### SELECTING ELEMENTS BY TAG NAME
```
var elements = document.getElementsByTagName('li'); //Find <li> elements 
if (elements.length> O) { //If 1 or more are found 
  var el = elements[O]; //Select the first one using array syntax
  el.className = 'cool'; //Change the value of the class attribute 
}
```
#### LOOPING THROUGH A NODELIST
```
var hotItems = document.querySelectorAll('li.hot'); // Store Node list in array

if (hot ltems.length > O) { //If it contains items 
  for (var i=O; i<hotltems.length; i++) {  // Loop through each item 
    hotltems[i] .className = 'cool'; // Change value of class attribute
  }
}
```

 

 
 

