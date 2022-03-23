# jQuery

jQuery is a Java Script library that has many pre-built methods and objects which simplifies the workflow. In specific, interacting with DOM and making HTTP requests (AJAX).

The plain Java Script in the past was not extensive and robust in the past. jQuery was originally created to make DOM interactions easy. 

It used $ sign for method name. JS allows $ in variable/function/method names. However it was hardly used. jQuery creator used it as a method name.

## Getting jQuery

1. CDN option by including the link
2. Download .js file of jQuery from official site and use it

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
