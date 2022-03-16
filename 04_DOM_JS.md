# Document Object Model (DOM)

HTML DOM is constructed as a tree of objects.

document
* html
  * head
    * title
      * "My First Page"
  * body
    * h1
      * "Section 1"
    * p
      * "This is a paragraph."
    * ul
      * li
        * "First item"
      * li
        * "Second item"

## Viewing DOM

Browser (any page)
* Right-click 
  - Inspect
    - Console
      > clear() <br>
      > document   // Can see the DOM <br>
      > console.dir(document)  // Can see as Java Script objects - properties and their values
    
## How to grab the objects in DOM?

- Grabbing large groups of elements (eg. head, body)
- Grabbing specific HTML elements (eg. id, class)

### Important document attributes

> document.URL <br>
> document.body <br>
> document.head <br>
> document.links <br>

### Methods for grabbing elements of DOM
> document.getElementById() - Returns the element with the id <br>
> document.getElementByClassName() - Returns the list of all elements belonging to a class <br>
> document.getElementsByTagName() - Returns the list of all elements with the tag <br>
> document.querySelector() - returns the first object matching the CSS style selector <br>
> document.querySelectorAll() - returns all object matching the CSS style selector <br>

Note: For querySelector() and querySelectorAll() you have to give # for id selector (#myid), . for class selector (.myclass).

## How to interact and affect DOM objects using JS?

> var myheader = document.querySelector("h1") <br>
> myheader <br>
> myheader.style.color = 'red'


### Random color changer in JS

```html
function getRandomColor() {
  var letters = "0123456789ABCDEF";
  var color = "#";
  for (var i=0; i<6; i++) {
    color += letters[Math.floor(Math.random()*16)];
  }
  return color;
}

function changeHeaderColor() {
  colorInput = getRandomColor();
  header.style.color = colorInput;  
}

// Now perform the action over intervals (milliseconds)
setInterval("changeHeaderColor()",500)
```

## Changing Text, HTML content and Attributes with DOM

> myvar.textContent - This returns the text <br>
> myvar.innerHTML - This returns the actual HTML <br>
> myvar.getAttribute() - Returns the original attributed <br>
> myvar.setAttribute() - Allows to set an attribute

// special refers to an id for an element. You have to refer to html to know this

> var special = document.querySelector("#special") <br>
> special  // Returns the html element with special id <br>
> var specialA = special.querySelector("a") <br>
> specialA  // Returns the html element with anchor tag <br>
> specialA.getAttribute("href") <br>
> specialA.setAttribute("href", "https://www.amazon.com")


## DOM Events
  - The above show how to specify the interaction with DOM beforehand. Sometimes we only want to interact with DOM when events happen 
  - There are many events such as hover, click, drag, double click, etc. Check Mozilla Developer Network for exhaustive list.
  - Achieved by adding an Event Listener. The javascript will be listening for event to occur and execute a function if that happens.
  - An example

```js
var head = document.querySelector('h1')
head.addEventListener("click", changeColor)
```

```html
<body>
  <h1 id="one">Hover over me</h1>
  <h1 id="two">Click me</h1>
  <h1 id="three">Double click me</h1>
</body>
<script src="script.js">
```

```js
var headOne = document.querySelector("#one")
var headTwo = document.querySelector("#two")
var headThree = document.querySelector("#three")

console.log("Connected")  // Can remove this statement after checking in browser
headOne.addEventListener('mouseover', function(){
  headOne.textCpntent = "Mouse currently over";
  headOne.style.colr = 'red';
})

headOne.addEventListener('mouseout', function(){
  headOne.textCpntent = "Hover over me";
  headOne.style.colr = 'black';
})

headTwo.addEventListener('click', function(){
  headTwo.textCpntent = "I was clicked";
  headTwo.style.colr = 'blue';
})

headThree.addEventListener('dblclick', function(){
  headThree.textCpntent = "I was double clicked";
  headThree.style.colr = 'green';
})
```

