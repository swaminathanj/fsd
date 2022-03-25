# jQuery

jQuery is a Java Script library that has many pre-built methods and objects which simplifies the workflow. In specific, interacting with DOM and making HTTP requests (AJAX).

The plain Java Script in the past was not extensive and robust in the past. jQuery was originally created to make DOM interactions easy. 

It used $ sign for method name. JS allows $ in variable/function/method names. However it was hardly used. jQuery creator used it as a method name.

## Getting jQuery

1. CDN option by including the link from https://releases.jquery.com and cut and paste the link in the html file
   * <script src="https://code.jquery.com/jquery-3.6.0.js" integrity="sha256-H+K7U5CnXl1h5ywQfKtSj8PCmoN9aaq30gDh27Xc0jk=" crossorigin="anonymous"></script>
2. Download .js file of jQuery from official site

## Examples of differences between vanilla java script and jQuery

### Grabbing all 'p' tags

``` javascript
var paras = document.querySelectorAll('p')  // vanilla

var paras = $('p')  // jQuery
```

### Edit the styling of certain variable

``` javascript
x.style.padding = '20px';  // vanilla

$(x).css('padding', '20px');  // jQuery
```

## Interacting with DOM using jQuery

You can workout on the console to see the effect. It will be easy to learn. Later you can write the code in separte file.

Let's take a sample html code to play with.

``` html
<html>
  <head>
    <title>Playing with jQuery</title>
  </head>
  <body>
    <h1>Playing with jQuery in console</h1>
    <p id='para1'>First try these commands in console to see the immediate effect. Once you get the grasp, you can write the script in separate file according to the requirement.</p>
    <ul>
      <li class='imp'>Open this html page in browser</li>
      <li class='imp'>Right click and select Inspect</li>
      <li class='imp'>Move to console tab</li>
      <li> Clear up the contents by using clear() method</li>
      <li class='imp'>Start trying out the following code one-by-one and see their effects.</li>
    </ul>
    <p id='para2'>Note that almost all browsers support jQuery. jQuery code can be written in Java Script file and browsers can run./<p>
    
    <h2>Add a text box and a submit button</h2>
    Note that both the text box and the submit button are constructed from input tag.
    <input type="text">
    <input type="submit">
  </body>
</html>
```

### 1. Grabbing by selector 

#### Grab the element with h1 tag
```javascript
var x = $('h1')  // jQuery way

var x = document.getElementsByTagName('h1') / document.querySelector('h1')   // Vanilla JS way
```

#### Grab all elements with li tag
```javascript
var y = $('li') // jQuery way

var y = document.getElementsByTagName('li') / document.querySelectorAll('li')  // Vanilla JS way
```

#### Grab the first element with li tag
```javascript
var yFirst = $('li').eq(0)   // jQuery way

var yFirst = document.getElementsByTagName('li')[0] / document.querySelector('li')  // Vanilla JS way
```

#### Grab the last element with li tag
```javascript
var yLast = $('li').eq(-1)    // jQuery way

var yLast = document.getElementsByTagName('li')[4]  // Vanilla JS way
```

#### Grab the element by id 'para1'
```javascript
var z = $('#para1')   // jQuery way

var z = document.getElementsById('para1') / document.querySelector('#para1')  // Vanilla JS way
```

#### Grab the elements with class 'imp'
```javascript
var w = $('.imp')   // jQuery way

var w = document.getElementsByClassName('imp') / document.querySelectorAll('.imp')  // Vanilla JS way
```

### 2. Methods to view and update the content

#### Get the text content
``` javascript
$('h1').text()  // jQuery way

document.getElementByTagName('h1').textContent  // Vanilla JS way
```

#### Set/Change the text content
``` javascript
$('h1').text('Heading  Changed')  // jQuery way

document.getElementByTagName('h1').textContent = 'Heading Changed'  // Vanilla JS way
```

#### Get the html content
``` javascript
$('h1').html()  // jQuery way

var x = document.getElementByTagName('h1').innerHTML  // Vanilla JS way
```

#### Set/Change the html content
``` javascript
$('h1').html('<em>Italicized Heading</em>')  // jQuery way

var x = document.getElementByTagName('h1').innerHTML = '<em>Italicized Heading</em>' // Vanilla JS way
```

#### Add before an element
``` javascript
$('#para1').before('<h2>A sub-heading added before the paragraph</h2>')  // jQuery way
```

#### Add after an element
``` javascript
$('#para2').after('<h2>A sub-heading added after the paragraph.</h2>')  // jQuery way
```

### 3. Applying styles

#### Applying a single style to an element
``` javascript
$('h1').css('color','blue')
$('li').eq(2).css('color','blue')
```

#### Applying a single style to many elements
``` javascript
$('.imp').css('color','red')
```

#### Applying multiple styles to an element
``` javascript
var sty = {
  'color' : 'red',
  'background' : 'yellow',
  'border' : '20px solid blue'
}
$('h1').css(sty)
```

### 4. Changing attributes

#### Set id of an element

``` javascript
$('h1').attr('id','hdng1')  // Set the attribute
$('h1')attr('id')           // Check whether it is set correctly
$('#hdng1').text()          // Check if the id attribute can be used to access the content
```

### 5. Handling Mouse Events

#### Click event using click function
```javascript
$('h1').click(function() {
  alert("Heading 1 clicked")
})
```

#### Click event using on function
```javascript
$('h1').on('click', function() {
  alert("Heading 1 clicked")
})
```

#### Double-click event using dblclick function
```javascript
$('h1').dblclick(function() {
  alert("Heading 1 double clicked")
})
```

#### Double-click event using on function
```javascript
$('h1').on('dblclick', function() {
  alert("Heading 1 double clicked")
})
```

#### Mouse-enter event using mouseevent function
```javascript
$('#para1').mouseenter(function() {
  alert("Mouse hovering over paragraph 1")
})
```

#### Mouse-enter event using on function
```javascript
$('#para1').on('mouseenter', function() {
  alert("Mouse hovering over paragraph 1")
})
```

#### Mouse-leave event using mouseout function
```javascript
$('#para1').mouseleave(function() {
  alert("Mouse out of paragraph 1")
})
```

#### Mouse-leave event using on function
```javascript
$('#para1').on('mouseleave', function() {
  alert("Mouse out of paragraph 1")
})
```

#### Mouse-down event using mousedown function
```javascript
$('#para1').mousedown(function() {
  alert("Mouse out of paragraph 1")
})
```

#### Mouse-leave event using on function
```javascript
$('#para1').mouseup(function() {
  alert("Mouse out of paragraph 1")
})
```

### 6. Toggling classes

DOESN'T SEEM TO BE WORKING FOR SOME REASON

#### Adding two classes to an element

Let's define a two classes *first* and *second* and set the respective styles. This should be done in css file.

```css
.first {
  'color' : 'blue',
  'background' : 'red'
}

.second {
  'color' : 'red',
  'background' : 'blue'
}
```

Let's now define two functions that will apply the *first* and *second* classes to h1 element when h1 element is clicked and double-clicked respectively. Note the applying the class implies applying the styles defined above.

``` javascript
function firstClass() {
  $('h1').removeClass('second')
  $('h1').addClass('first')
}

function secondClass() {
  $('h1').removeClass('first')
  $('h1').addClass('second')
}

$('h1').on('click', firstClass)
$('h1').on('dblclick', secondClass)
```

### 7. Handling Keyboard events

#### Keypress event (Any key pressed)
```javascript
$('input').eq(0).keypress(function() { 
  $('h1').css('color', 'blue') 
})
```
* $('input').eq(0).keypress(function(event) { console.log(event) } )

#### Keypress event (Enter key pressed)
```javascript
$('input').eq(0).keypress(function(event) { 
  if (event.which === 13) {    // ASCII value of Enter key is 13
    $('li').eq(0).color('color', 'red')) 
  } 
})
```

### 8. Getting and Setting values to textbox

### Setting value to textbox
```javascript
$('input').eq(0).val('New text')  // Changes the text box value to 'New text'
```

### Display value in textbox
```javascript
alert( $('input').eq(0).val() )   // Display the text box value using alert box
```

### 9. Special effects on textbox

DOESN'T SEEM TO BE WORKING FOR SOME REASON

#### Fade out the content
```javascript
$('input').eq(1).on('click', function(event) { 
  $('.container').fadeOut(3000) 
})
```

#### Slide the content upwards
```javascript
$('input').eq(1).on('click', function(event) { 
  $('.container').slideUp(3000) 
})
```

### 10. The importance of document ready function

First try this. Refresh the html page. Observe what is displayed in the alert box and whether heading changed.
```javascript
  var x = $('h1')
  alert(x.text())
  x.text("Changed heading")
```

Then try this. Refresh the html page. Observe what is displayed in the alert box and whether heading changed.
```javascript
$(document).ready(function() {
  var x = $('h1')
  alert(x.text())
  x.text("Changed heading")
})
```

What difference do you find? Does this clarify the use of *document ready* function?

### Rough work

* $('h1')
* $('li')
* var x = $('h1')
* x.css('color', 'red')
* x.css('background', 'blue')
* var y = { <br>
    'color': 'blue', <br>
    'background' : 'yellow', <br>
    'border' : ' 20px solid red' <br>
  }
* y
* x.css(y)
* var z = $('li')
* z
* z.css('color', 'blue')  // Changes all list items to blue
* z.eq(0).css('color', 'red')  // Applies to first list item
* z.eq(-1).css('color', 'orange')  // Applies to last list item
* $('h1').text()  // Displays the heading 1 text - equivalent to .textContent
* $('h1').text("New text")  // Changes the heading 1 text 
* $('h1').html()  // Displays the html of h1
* $('h1').html("&langle;strong&rangle;New text&langle;/strong&rangle;")  // Makes the heading 1 bold
* $('input').eq(1).attr('type','checkbox')  // Changes button to checkbox
* $('input').eq(0).val('New text')  // Changes the text box value to 'New text'
* $('h1').addClass('first')  // adds h1 item to first class, first is a class in CSS file
* $('h1').removeClass('first')  // removes h1 item from first class, first is a class in CSS file
* $('h1').toggleClass('first')  // adds and removes first class alternately when called
* $('h1').click(function(){ alert('h1 was clicked') })
* $('h1').click(function(){ console.log('An li was clicked') })
* $('h1').click(function(){ $('this').text('Heading 1 changed') })
* $('input').eq(0).keypress(function() { $('h3').toggleClass('first') } )
* $('input').eq(0).keypress(function(event) { console.log(event) } )
* $('input').eq(0).keypress(function(event) { if (event.which === 13) { $('h3').toggleClass('first') } } )
* $(h1).on('dblclick', function() { $this.toggleClass('first') } )
* $(h1).on('mouseenter', function() { $this.toggleClass('first') } )
* $('input').eq(1).on('click', function(event) { $('.container').fadeOut(3000) } } )
* $('input').eq(1).on('click', function(event) { $('.container').slideUp(3000) } } )
