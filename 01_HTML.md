# Hyper Text Markup Language (HTML)

## A basic bare-bones HTML page

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
  <body>
    
  </body>
</html>
```

## Different levels of headings

Heading tags are used inside &lt;body&gt; section.

```html
<h1>First level heading</h1>

<h2>Second level heading</h2>

<h3>Third level heading</h3>

<h4>Fourth level heading</h4>
```

## Writing text and formatting

These tags are used within &lt;body&gt; section.

```html
<p>Free flowing paragraph text are enclosed within the paragraph tag. You use <br /> for line break. Adding bullets can be done using <ul> and <li> tags as shown below.</p>
<ul>
  <li>This is how you make the <strong>text bold</strong>.</li> 
  <li>This is how you make the <emph>text italic</emph>.</li>
  <li>The underlining is not so simple.</li>
</ul>

<p style="color:red">Any part of the <span style="color:blue">text can be made blue</span> by enclosing them within span tag and using the style attribute.
In fact, the entire paragraph can be set to red color by using style attribute of the paragraph tag.
You can also <span style="text-decoration: underline";>underline text</span> using style tag.</p>

<p>You can also create numbered bullets by using ol and li tags.</p>
<ol>
  <li>ol refers to ordered list</li>
  <li>li refers to list item</li>
  <li>ul refers to unordered list</li>
  <li>You can also have nested lists.
    <ul>
      <li>This is first sub-item of the fourth item</li>
      <li style="color: cyan">The subitem can be colored in a similar way.</li>
    </ul>
  </li>
</ol>

<p>This is how text can be converted to <sup>superscript</sup> and <sub>subscript</sub>. <br /> 
The equation of a circle can be written as x<sup>2</sup> + y<sup>2</sup> = r<sup>2</sup>.
```

## User Interface

These tags are used within &lt;body&gt; section.

```html
<label>Label</label>
<input type="text">
<input type="password">
<button>Button</button>
<select> </select>
<select>
  <option>Value 1</option>
  <option>Value 2</option>
</select>
<br />
<input type="radio">
<label>option 1</label>
<input type="checkbox">
<label>option 1</label>
```

