# jQuery

jQuery is a Java Script library that has many pre-built methods and objects which simplifies the workflow. In specific, interacting with DOM and making HTTP requests (AJAX).

The plain Java Script in the past was not extensive and robust in the past. jQuery was originally created to make DOM interactions easy. 

It used $ sign for method name. JS allows $ in variable/function/method names. However it was hardly used. jQuery creator used it as a method name.

## Getting jQuery

1. CDN option by including the link from https://releases.jquery.com and cut and paste the link in the html file
   * <script src="https://code.jquery.com/jquery-3.6.0.js" integrity="sha256-H+K7U5CnXl1h5ywQfKtSj8PCmoN9aaq30gDh27Xc0jk=" crossorigin="anonymous"></script>
3. Download .js file of jQuery from official site

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
      <li>Clear up the contents by using clear() method</li>
      <li class='imp'>Start trying out the following code one-by-one and see their effects.</li>
    </ul>
    <p>Note that almost all browsers support jQuery. jQuery code can be written in Java Script file and browsers can run./<p>
  </body>
</html>
```

### Grabbing by selector 

#### Grab the element with h1 tag
```javascript
> var x = $('h1')  // jQuery way
> var x = document.getElementsByTagName('h1') / document.querySelector('h1')   // Vanilla JS way
```

#### Grab all elements with li tag
```javascript
> var y = $('li') // jQuery way
> var y = document.getElementsByTagName('li') / document.querySelectorAll('li')  // Vanilla JS way
```

#### Grab the first element with li tag
```javascript
> var yFirst = $('li').eq(0)   // jQuery way
> var yFirst = document.getElementsByTagName('li')[0] / document.querySelector('li')  // Vanilla JS
```

#### Grab the last element with li tag
```javascript
> var yLast = $('li').eq(-1)    // jQuery way
> var yLast = document.getElementsByTagName('li')[4]  // Vanilla JS way
```

#### Grab the element by  id 'para1'
```javascript
> var z = $('#para1').eq(-1)   // jQuery way
> var z = document.getElementsById('para1') / document.querySelector('#para1')  // Vanilla JS way
```

#### Grab the element with class 'imp'
```javascript
> var z = $('.imp').eq(-1)   // jQuery way
> var z = document.getElementsByClassName('imp') / document.querySelector('.imp')  // Vanilla JS way
```

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








