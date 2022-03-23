# jQuery

jQuery is a Java Script library that has many pre-built methods and objects which simplifies the workflow. In specific, interacting with DOM and making HTTP requests (AJAX).

The plain Java Script in the past was not extensive and robust in the past. jQuery was originally created to make DOM interactions easy. 

It used $ sign for method name. JS allows $ in variable/function/method names. However it was hardly used. jQuery creator used it as a method name.

## Getting jQuery

1. CDN option by including the link from https://code.jquery.com and cut and paste the link in the html file
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

You can workout on the console too.

* $('h1')
* $('li')
* var x = $('h1')
* x.css('color', 'red')
* x.css('background', 'blue')
* var y = { <br>
    'color': 'blue', <br>
    'background' : 'yellow', <br>
    'border' : ' 20px solid red'
  }
* y
* x.css(y)






