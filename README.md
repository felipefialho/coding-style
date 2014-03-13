My Coding Style
============

> Every line of code should appear to be written by a single person, no matter the number of contributors.

The following document describes the rules of writing in development languages that I use: HTML, CSS and Javascript.

The idea of this repository is to have a place for myself and other developers who participate in my projects able to inform the coding standards used.

Like this is a new document, some rules may not have been applied in old projects.

## Summary
 
1. [Commits] (#commits) 
1. [HTML] (#html) 
1. [CSS] (#css) 
1. [Javascript] (#js) 
1. [License](#license)
1. [References](#references)
 
<a name="commits"></a>
## 1. Commits

For facilitate the contribution of any people in projects, all commit message, pull request title or issue discussion must be in **English**.

Before commit adjusts in project, check if exists one open issue and make references for this issue using '#' in your commit message.

```javascript
// Good
git commit -m "Add placeholder in input #10"

// Bad
git commit -m "Add placeholder in input"
```

<a name="html"></a>
## 2. HTML

The main influence for the HTML rules is the [Code Guide by @mdo](https://github.com/mdo/code-guide).

### HTML Summary

1. [HTML Syntax] (#html-syntax) 
1. [Character encoding] (#html-encoding)
1. [Attribute order] (#html-attribute-order)
1. [Performance] (#html-performance) 
1. [Base Code] (#html-base)

<a name="html-syntax"></a>
### 2.1. HTML Syntax

Use soft tabs with two spaces. You can configure your editor for this. 

```html
<!-- Good -->
<nav class="nav">
  <ul class="nav-menu">
    <li class="nav-item">
      <a class="nav-link">

<!-- Bad-->
<nav class="nav">
      <ul class="nav-menu">
            <li class="nav-item">
                  <a class="nav-link">
```

Always use double quotes.

```html
<!-- Good -->
<div class="main">

<!-- Bad-->
<div class='main'>
```
  
Don't include a `/` in self-closing elements.

```html
<!-- Good -->
<hr>

<!-- Bad-->
<hr />
```

Follow this rule to add comments in HTML.

```html
<!-- This is a good example -->
<!-- /Closing a good example -->
```

<a name="html-encoding"></a>
### 2.2. Character encoding

Always use UTF-8 for character encoding.

```html
<head>
  <meta charset="UTF-8">
</head>
```

<a name="html-attribute-order"></a>
### 2.3. Attribute order

HTML attributes should be in this order for facilitate the reading.

1. `class`
1. `id`, `name`
1. `data-*`
1. `src`, `for`, `type`, `href`
1. `title`, `alt`
1. `aria-*`, `role`

```html
<a class="..." id="..." data-modal="toggle" href="#"> 

<input class="form-control" type="text">

<img class="img-rounded" src="..." alt="...">
```

<a name="html-performance"></a>
### 2.4. Performance

No need to specify a type when including CSS and JavaScript files as `text/css` and `text/javascript`.

```html
<!-- Good -->
<link rel="stylesheet" href="assets/css/style.css" />
<script src="scripts.min.js"></script> 

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
<body>
```

For a better performance, all javascripts files must be at the end of the code. Before closing the `<body>`.

```html
<!-- Good -->
<script src="scripts.min.js"></script>t
</body>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
<body>
```

Always minify the code in projects only in HTML. Task builders like [Grunt](http://gruntjs.com/) leaves this easier.

```html
<!-- Good -->
<html><head>...</head><body><div class="container">...</div></body></html>

<!-- Bad -->
<html>
  <head>
    ...
  </head>
  <body>
    <div class="container">
      ...
    </div>
  </body>
</html>
```

<a name="html-base"></a>
### 2.5. Base Code

The following code is a HTML base for faster start the projects.

```html
<!DOCTYPE html>
<html lang="en">
<head>

<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="format-detection" content="telephone=no">
<meta name="viewport" content="width=device-width">
 
<link rel="shortcut icon" href="assets/img/ico/favicon.ico" />

<!-- SVG Logo --> 
<link rel="logo" type="image/svg" href="../assets/img/logo/logo.svg" />
 
<title></title>

<link rel="stylesheet" href="assets/css/style.css" />
 
</head>
<body>

<!-- Scripts -->
<script src="assets/js/scripts.min.js"></script>

</body>
</html>
```

For give support a olds Internet Explorer... 

```html
<!DOCTYPE html>
<!--[if IE]><![endif]-->
<!--[if IE 7 ]> <html lang="en" class="ie7">    <![endif]-->
<!--[if IE 8 ]>    <html lang="en" class="ie8">    <![endif]-->
<!--[if IE 9 ]>    <html lang="en" class="ie9">    <![endif]-->
<!--[if (gt IE 9)|!(IE)]><!--><html lang="en"><!--<![endif]-->
<head>
...
```

<a name="css"></a>
## 3. CSS
 
The main influences for the CSS rules are [Code Guide by @mdo](https://github.com/mdo/code-guide) and [idiomatic CSS](https://github.com/necolas/idiomatic-css/).

### CSS Summary

1. [CSS Syntax] (#css-syntax) 
1. [Declaration order] (#css-order)
1. [Performance] (#css-performance)
1. [Media query] (#css-media-querie)
1. [Pre-processors] (#css-pre-processors)
1. [Comments] (#css-comments)
1. [Code Example] (#css-code-example)

<a name="css-syntax"></a>
### 3.1. CSS Syntax

Use soft tabs with two spaces. You can configure your editor for this. 

```css
/* Good */
.nav-item {
  display: inline-block;
  margin: 0 5px;
}

/* Bad */
.nav-item {
    display: inline-block;
    margin: 0 5px;
}
```

Always use double quotes.

```css
/* Good */
[type="text"]
[class^="..."]

.nav-item:after {
  content: "";
}

/* Bad */
[type='text']
[class^='...']

.nav-item:after {
  content: '';
}
```

Include a single space before the opening brace of a ruleset.

```css
/* Good */
.header {
  ...
}

/* Bad */
.header{
  ...
}
```

Include a single space after the colon of a declaration.

```css
/* Good */
.header {
  margin-bottom: 20px;
}

/* Bad */
.header{
  margin-bottom:20px;
}
```

Include a semi-colon at the end of the last declaration in a declaration block.

```css
/* Good */
.header {
  margin-bottom: 20px;
}

/* Bad */
.header{
  margin-bottom:20px
}
```

Keep one declaration per line.

```css
/* Good */
.selector-1,
.selector-2,
.selector-3 {
  ...
}

/* Bad */
.selector-1, .selector-2, .selector-3 {
  ...
}
```

Single declarations should remain in one line.

```css
/* Good */
.selector-1 { width: 50%; }

/* Bad */
.selector-1 {
  width: 50%;
}
```

Separate each ruleset by a blank line.

```css
/* Good */
.selector-1 {
  ...
}

.selector-2 {
  ...
}

/* Bad */

.selector-1 {
  ...
}
.selector-2 {
  ...
}
```

Use lowercase and shorthand hex values and avoid specifying units is zero-values.

```css
/* Good */
.selector-1 {
  color: #aaa;
  margin: 0;
}
 
/* Bad */
.selector-1 {
  color: #AAAAAA;
  margin: 0px;
} 
```

<a name="css-order"></a>
### 3.2. Declaration order

The declarations should be added in alphabetical order.

```css
/* Good */
.selector-1 {
  background: #fff;
  border: #333 solid 1px;
  color: #333;
  display: block;
  height: 200px;
  margin: 5px;
  padding: 5px; 
  width: 200px;
}
 
/* Bad */
.selector-1 {
  padding: 5px; 
  height: 200px;
  background: #fff;
  margin: 5px;
  width: 200px;
  color: #333;
  border: #333 solid 1px;
  display: block;
} 
```

<a name="js"></a>
## 4. Javascript
 
<a name="references"></a>
## 5. References

* [Code Guide by @mdo](https://github.com/mdo/code-guide)
* [idiomatic CSS](https://github.com/necolas/idiomatic-css/)
* [idiomatic.js](https://github.com/rwldrn/idiomatic.js/)
* [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style/) 

<a name="license"></a>

## 6. License
 
[MIT License](http://felipefialho.mit-license.org/) © Luiz Felipe Tartarotti Fialho
