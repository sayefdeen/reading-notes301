# Read02 : Pair Programming jQuery.

[Home](https://sayefdeen.github.io/reading-notes301/)

## jQuery

jQuery offers a somple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.

jQuery is a JavaScript file that you include in your web pages, it lets you find elements using CSS-style selectors and then do something with the element using jQuery methods.

```javascript
$("li.hot");
```

This selector `$` it means `document` object in javascript you can use any CSS selector inside the beackets ().

- jQuery selectors perform a similar task to traditional DOM queries, but the syntax is much simpler.

- You can store the jQuery object in a variablem just as you can with DOM nodes.

- You can jQuery methods and properties to maipulate the DOM nodes that you selected.

You can get jQuery by using its CDN from this [website](https://code.jquery.com/), or you can download it as a file and include it in your project.

### Why do we use jQuery?

jQuery dosen't do anything you cannot achive with pure JavaScript. It is just a JavaScript file but estimates show it has been used on over a quarter of the sites on the web, because it makes coding simpler.

jQuery's motto is "Write less, do more" because it allows you to achieve the same goals but in fewer lines of code than you would need to write with plain javaScript.

1. Simple Selector

   - Are much faster at selecting elements.
   - Can be a lot more accurate about which elements to select.
   - Often require a lot less code than older DOM methods.
   - Are already used by most frot-end developers

2. Common Tasks in less code
3. Cross-Browsers compatibility

### jQuery selection.

When you select one or more elements, a jQuery onject is returned, it is also known as a matched set or a jquery selection.

- Single selection : if a selector returns one element, the jQuery object containes a reference to just one element node `$('ul')`

- Multiple selection : if a selector returns several elements, the jQuery object contains references to each element. `$('li')` this object contains a list of all li elements in the HTML DOM.

### methods used to Get/Set informations.

- Get Information : if a jQuery selection holds more than one element, and a method is used to get information form the selected elements, it will retrieve infromation from only the first elements in the matched set.
  `$('li').html()` this code will select all `<li>` elements, then it will return the frist element information.

`var content = $('li').html();`

- Set information : if a jQuery selection holds more than one element, and a method is used to set information form the selected elements, all the elements will change there content to the new one.

`$('li').html('Updated');` this code will change all `<li>` content to the string 'Updated'.

### Looping.

In jQuery, when a selector return multiple elements, you can update all of them using the one method, There is no need to use a loop.
`$('li em').addClass('seasonal')`; This code will add a class called seasonal to all `<em>` elements inside `<li>` element.

### Methods.

- `.html()` : This methode get/set a content into the element this content could include HTML.

- `.text()` same as `.html()` but you can only include text.

- `.replaceWith()` : this method replaces every element in a matched set with new content.

- `.remove()` : This method remove all elements in the mathced set.

- `.before()` : This method insertes content before the selected element.

- `.after()` : This method insertes content after the selected element.

- `.prepend()` : This method inserts content inside the selected element after the opening tag.

- `.append()` : This method inserts content inside the selected element before the closing tag.

- `.attr()` : This method can get or set a specified attribute and its value.

- `.removeAttr()` : This method removes a specified attribute(and its value).

- `addClass()` : This method adds a new value to the existing value of the class attribute.

- `.removeClass()` : This method removes a value from the class attribute leaving ant other class names within that attribute intact.

- `.css()` : This method can get of set any CSS properties.
