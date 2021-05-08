# Class-01

## Basic HTML Layout
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

Each HTML document has a basic layout. This includes the necessary tags neccessary to have a complete simple document.

```html
<!DOCTYPE html>
```
This line tells the browser that there is an HTML document coming so that it can prepare for it.

```html
<html lang="en">
```
The HTML language tag sets the document's language. In this case, the language is set to English.

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
```
The \<head> tag includes all of your meta data for the website which can include description tags and keywords to help search engines find your page. 
The \<title> tag lets you name your website and shows the name on the tab above your window.

```html
<body>
  
</body>
```
The \<body> tag follows the head tag and contains the bulk of the pages information. Your \<nav> and \<header> tags can usually be found in here along with \<p> and \<ul> tags.

```html
</html>
```
Finally, the final \</html> tag closes the HTML document so that there are no open tags or errors.

## JavaScript in your HTML
```html
</head>
<body>
  
  <script></script>
  
</body>
</html>
```
JavaScript can be added to you document with the \<script> tag. 

```html
<script> Insert code here </script>
```
This line can be added either inside the \<head> tag or better used inside the \<body> tag to ensure your CSS properties are still intact.

```html
<script src="app.js"></script>
```
Adding an external JavaScript file like \"app.js" is the most common practice way to add JavaScript to your HTML document.

