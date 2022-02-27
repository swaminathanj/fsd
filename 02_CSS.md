# Cascading Style Sheets

## Introduction
* Why CSS?
* External, Internal, Inline
* Syntax
  - Selector { property1: value; property2: value; }
  - Example: p { color: blue; text-align: center; }
  
## CSS Selectors
* The **element** selector
  - p { color: blue; text-align: center; }
* The **id** selector
  - <p id="first">This is used to demonstrate id selector.</p>
  - #first { text-align: right; }
*  The **class** selector
  - <p class="group">This is used to demonstrate class selector.</p>
  - <p class="group">Unline id, same class name can be used to select multiple elements.</p>
  - .group { color: blue; }
* Multi class selector
  - Same html element can be part of multiple classes
  - <p class="first second">This is used to demonstrate class selector.</p>
  - .first { color: blue; }
  - .second { text-align: center; }
