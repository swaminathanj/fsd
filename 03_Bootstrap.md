# Bootstrap

* A front-end framework for developing **mobile-first** for websites. 
  - You code goes inside the framework, referred to as inversion of control. Unlike library where you bring the library code into yours.
  - You can add your code to the framework in pre-defined ways, but the framework code in itself is not modifiable.
* It includes **pre-developed components**.
  - You don't have to write lot of CSS or JS code which enables faster development.
  - By default, some features are implemented. Even if you didn't add anything, something will show-up.
* It comes with **responsive 12 column** CSS grid system for layouts. 
* Bootstrap 5 is the current version.

Bootstrap 5 important changes:
* Does not use jQuery
* Jumbotron component not supported
* New components added: Offcanvas and Accordion

The most important thing to learn is: how to reference the documentation. You don't have to memorize. The documentation is very easy with lots of examples. Go to [Get Bootstrap](https://getbootstrap.com/)

## Working with Bootstrap
Two ways to work with Bootstrap.
1. Content Delivery Network (CDN) - Copy the CDN Link to the HTML file. [Getting Started](https://getbootstrap.com/docs/5.1/getting-started/introduction/) has the link to be included in the HTML page.
2. Download to local machine, save the on a folder and link to that. Do this only if you don't have access to the internet.

## Start with the starter template
* The template and the associated explanation is available in the [Getting Started](https://getbootstrap.com/docs/5.1/getting-started/introduction/) page.
* Note that the default font for Bootstrap is Sans Serif (as evident from Hello World) and not the browser default Times New Roman. 

## Display class
The **display** class is used for headings. Note that the class changes the way each element looks even though it is h1 tag for all.

```html
<h1 class="display-1">Display 1 heading</h1>
<h1 class="display-2">Display 2 heading</h1>
<h1 class="display-5">Display 5 heading</h1>
<p class="display-6">Display 5 heading</p>
```

### Responsive Web Design

```html
<div class="container">
  <div class="row">
    <div class="col-3- col-6- boxy">ONE</div>
    <div class="col-3- col-6- boxy">TWO</div>
    <div class="col-3- col-6- boxy">THREE</div>
    <div class="col-3- col-6- boxy">FOUR</div>
  </div>
</div>
```
