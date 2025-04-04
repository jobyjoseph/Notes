# Complete Intro to Web Dev v3

## Introduction

- What this course about
- Targeting audience
- Self introduction
- Mindset to take this course

## Tools

- IDE
  - Visual Studio Code
  - Sublime Text
- Browser
  - Chrome
  - Firefox
  - Others
- Online editor
  - CodePen

## What is HTML

HTML stands for HyperText Markup Language. It provides the structure and content.

[Start with bare content]

[Add structure to content]

## What is CSS

CSS stands for Cascading StyleSheets. It styles the website.

[Apply color to content]

## What is JavaScript

JavaScript is a programming language that brings interactivity to web site. Browsers can run JavaScript.

## HTML

### Tags

HTML Rendering Engine.

```html
<h1>This is a heading 1</h1>
<h2>This is a heading 2</h2>
<h3>This is a heading 3</h3>
<h4>This is a heading 4</h4>
<h5>This is a heading 5</h5>
<h6>This is a heading 6</h6>
```

#### Nesting tags

```html
<div>
  <h1>Hello</h1>
</div>
```

Recently opened tag must be closed first.

### Common Tags

```html
<h1>Heading 1</h1>
<div>Division</div>
<p>Paragraph</p>
<span>Emphasize inline text</span>
```

Ordered lists:

```html
<ol>
  <li>First</li>
  <li>Second</li>
  <li>Third</li>
</ol>
```

Unordered lists:

```html
<ul>
  <li>First</li>
  <li>Second</li>
  <li>Third</li>
</ul>
```

```html
<button>Click Me!</button>
```

```html
<img src="image.png" alt="This is an image" />
```

### Input & Form Tags

Browser input

```html
<input type="text" />
```

```html
<textarea></textarea>
```

```html
<select>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

Inputs are wrapped inside a form.

```html
<form></form>
```

### Tables

```html
<table>
  <tbody>
    <tr>
      <td>0,0</td>
      <td>0,1</td>
    </tr>
    <tr>
      <td>1,0</td>
      <td>1,1</td>
    </tr>
  </tbody>
</table>
```

Comments

```html
<!-- Comment here -->
```

### Attributes, Classes and IDs

Attributes are key-value pairs that define a tag. Based on the tag, the supported attributes changes.

```html
<input type="text" /> <img src="image1.png" />
```

> In HTML, if it does not understand anything, it will ignore that. No error is thrown.

Classes are specific attributes that apply styles to tags.

IDs are unique in a page. IDs can be used to put a link to particular part of the page.
