My Coding Style
============

> "Every line of code should appear to be written by a single person, no matter the number of contributors." - Chinese Proverb.

The following document describes the rules of writing in development languages that I use: HTML, CSS and JavaScript.

The idea of this repository is not to be a complete code guide. Only to have a place for myself and other developers who participate in my projects able to inform the coding standards used.

As this is a new document, some rules may not have been applied in old projects.

This is a live document and changes can occur at any time.

## Summary

1. [Commits](#commits)
1. [HTML](#html)
1. [Jade](#jade)
1. [CSS](#css) 
1. [CSS Preprocessors](#css-preprocessors) 
1. [Javascript](#js)
1. [Boilerplate](#boilerplate) 
1. [References](#references)
1. [Translations](#translations)
1. [License](#license)

<a name="commits"></a>
## 1. Commits

For facilitate the contribution of any people in projects, all commit messages, pull request title or issues discussion must be in **English**.

Before commit adjusts in project, check if exists an open issue and make references for this issue using '#' in your commit message.

```javascript
// Good
git commit -m "Add placeholder on input #10"

// Bad
git commit -m "Add placeholder on input"
```

<a name="html"></a>
## 2. HTML

The main influence for the HTML rules is the [Code Guide by @mdo](https://github.com/mdo/code-guide).

### HTML Summary

1. [HTML Syntax](#html-syntax)
1. [HTML Comments](#html-comments)
1. [HTML Character Encoding](#html-encoding)
1. [HTML Attribute Order](#html-attribute-order)
1. [HTML Performance](#html-performance)
1. [HTML Base Code](#html-base)

<a name="html-syntax"></a>
### 2.1. HTML Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```html
<!-- Good -->
<nav class="navbar">
  <ul class="nav">
    <li class="nav-item">
      <a class="nav-link">

<!-- Bad-->
<nav class="navbar">
      <ul class="nav">
            <li class="nav-item">
                  <a class="nav-link">
```

Always use double quotes.

```html
<!-- Good -->
<main class="main">

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

Separate block element by a blank line and agroup the inners block elements.

```html
<!-- Good -->
<ul class="nav-tabs">
  <li>...</li>
  <li>...</li>
  <li>...</li>
  <li>...</li>
</ul>

<div class="tab-content">
  ...
</div>

<!-- Bad-->
<ul class="nav-tabs">

  <li>...</li>

  <li>...</li>

  <li>...</li>

  <li>...</li>

</ul>
<div class="tab-content">
  ...
</div>
```

<a name="html-comments"></a>
### 2.2. HTML Comments

Follow this rule to add comments in HTML.

```html
<!-- This is a good example -->
<!-- /Closing a good example -->
```

<a name="html-encoding"></a>
### 2.3. HTML Character Encoding

Always use UTF-8 for character encoding.

```html
<head>
  <meta charset="UTF-8">
</head>
```

<a name="html-attribute-order"></a>
### 2.4. HTML Attribute Order

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
### 2.5. HTML Performance

No need to specify a type when including CSS and JavaScript files as `text/css` and `text/javascript`.

```html
<!-- Good -->
<link rel="stylesheet" href="assets/css/style.css">
<script src="scripts.min.js"></script>

<!-- Bad -->
<link rel="stylesheet" href="assets/css/style.css" type="text/css">
<script src="scripts.min.js" type="text/javascript"></script>
</head>
<body>
```

For a better performance, all JavaScripts files must be at the end of the code. Before closing the `<body>`.

```html
<!-- Good -->
<script src="scripts.min.js"></script>
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
### 2.6. HTML Base Code

The following code is a HTML base for faster start the projects.

```html
<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="utf-8">
<meta name="format-detection" content="telephone=no">
<meta name="viewport" content="width=device-width">

<link rel="shortcut icon" href="assets/ico/favicon.ico">
<link rel="logo" type="image/svg" href="assets/img/logo/logo.svg">
<link rel="stylesheet" href="assets/css/style.css">

<title></title>

</head>
<body>

<!-- Scripts -->
<script src="js/scripts.min.js"></script>

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

<a name="jade"></a>
## 3. Jade

Currently using Jade like template engine.

### Jade Summary

1. [Jade Syntax](#jade-syntax)
1. [Jade Comments](#jade-comments) 
1. [Jade Base Code](#jade-base)

<a name="jade-syntax"></a>
### 3.1. Jade Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```javascript
//- Good
nav.navbar
  ul.nav
    li.nav-item
      a.nav-link

//- Bad
nav.navbar
    ul.nav
        li.nav-item
            a.nav-link
```

Always use single quotes.

```javascript
//- Good
button.btn(data-toggle='collapse')

//- Bad
button.btn(data-toggle="collapse")
```
 
Insert the title of block, separate block element by a **two** blanks lines and agroup the inners block elements.

```javascript
//- Good
 
//- Header
//- ===================================
header.header(role='banner')
  a.logo(href='#', role='logo')


//- Main
//- ===================================
main.main(role='main')
  section.content
 
//- Bad
header.header(role='banner')
  a.logo(href='#', role='logo') 
main.main(role='main') 
  section.content
```

<a name="jade-comments"></a>
### 3.2. Jade Comments

Follow this rule to add comments in Jade.

```javascript
//- This is a good example 

// This is a bad example 
```

The comments using `//-` not is compiled on final code.
  
<a name="jade-base"></a>
### 3.3. Jade Base Code

The following code is a Jade for faster start the projects.

```javascript
doctype html
html(lang='en')
  head 
    meta(charset='utf-8')
    meta(name='description', content='')
    meta(name='viewport', content='width=device-width, initial-scale=1')
    meta(name='format-detection', content='telephone=no')

    //- Title
    //- ===================================
    title The project title here

    //- Favicon and SVG logo
    //- ===================================
    link(rel='shortcut icon', href='ico/favicon.ico')  
    link(rel='logo', type='image/svg', href='svg/logo/logo.svg')

    //- Stylesheet and fonts
    //- ===================================
    link(href='css/style.css', rel='stylesheet')  

  body 
 
    //- Scripts
    //- ===================================
    script(src='js/scripts.min.js') 
```
 

<a name="css"></a>
## 4. CSS

The main influences for the CSS rules are [Code Guide by @mdo](https://github.com/mdo/code-guide) and [idiomatic CSS](https://github.com/necolas/idiomatic-css/).

### CSS Summary

1. [CSS Syntax](#css-syntax)
1. [CSS Declaration Order](#css-order)
1. [CSS Class Name](#css-class-name)
1. [CSS Performance](#css-performance)
1. [CSS Media Queries](#css-media-queries) 

<a name="css-syntax"></a>
### 4.1. CSS Syntax

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

Include a single space before the opening bracket of a ruleset.

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

Use lowercase, shorthand hex values and avoid specifying units is zero-values.

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
### 4.2. CSS Declaration Order

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

<a name="css-class-name"></a>
### 4.3. CSS Class Name

Keep class lowercase and use dashes.

```css
/* Good */
.nav-item { ... }

/* Bad */
.NavItem { ... }
.nav_item { ... }
```

Dashes serve as natural breaks in related class. Prefix class based on the closest parent or base class.

```css
/* Good */
.navbar { ... }
.nav { ... }
.nav-item { ... }
.nav-link { ... }

/* Bad */
.item-nav { ... }
.link-nav { ... }
```

Avoid giving too short names for class and always choose meaningful names that provide the class function.

```css
/* Good */
.btn { ... }
.page-header { ... }
.progress-bar { ... }

/* Bad */
.s { ... }
.ph { ... }
.block { ... }
```

<a name="css-performance"></a>
### 4.4. CSS Performance

Never use IDs.

```css
/* Good */
.header { ... }
.section { ... }

/* Bad */
#header { ... }
#section { ... }
```

Do not use selectors standards for not generic rules, always preferably for class.

```css
/* Good */
.form-control { ... }
.header { ... }
.section { ... }

/* Bad */
input[type="text"] { ... }
header
section
```

Avoid nesting elements, the preference is always to use class.

```css
/* Good */
.navbar { ... }
.nav { ... }
.nav-item { ... }
.nav-link { ... }

/* Bad */
.navbar ul { ... }
.navbar ul li { ... }
.navbar ul li a { ... }
```

Nest only when need change the class comportament with interference for other class. Keep the nested on max of three elements.

```css
/* Good */
.modal-footer .btn { ... }
.progress.active .progress-bar { ... }

/* Bad */
.modal-btn { ... }
.progress.active .progress-bar .progress-item span { ... }
```

Always minify the CSS code. Task builders like [Grunt](http://gruntjs.com/) leaves this easier.

```css
<!-- Good -->
.navbar { ... }.nav { ... }.nav-item { ... }.nav-link { ... }

<!-- Bad -->
.nav-item {
  ...
}
.nav-link {
  ...
}
```

<a name="css-media-queries"></a>
### 4.5 CSS Media Queries

Start the development with generic rules with and add media queries with mobile first.

```css
/* Good */
.navbar {
  margin-bottom: 20px;
}

@media (min-width: 480px) {
  .navbar {
    padding: 10px;
  }
}

@media (min-width: 768px) {
  .navbar {
    position: absolute;
    top: 0;
    left: 0;
  }
}

@media (min-width: 992px) {
  .navbar {
    position: fixed;
  }
}

/* Bad */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
}

@media (max-width: 767px) {
  .navbar {
    position: static;
    padding: 10px;
  }
}

```

Keep the media queries as close to their relevant rule sets whenever possible. Don't bundle them all in a separate stylesheet or at the end of the document.

```css
.navbar { ... }
.nav { ... }
.nav-item { ... }

@media (min-width: 480px) {
  .navbar { ... }
  .nav { ... }
  .nav-item { ... }
}
```

<a name="css-preprocessors"></a>
## 5. CSS Preprocessors

I use pre-processors in all projects. Today I use **Stylus**, but some projects use `LESS`.

### CSS Preprocessors Summary

1. [CSS Preprocessors Syntax](#preprocessors-syntax)  
1. [CSS Preprocessors Performance](#preprocessors-performance) 
1. [CSS Preprocessors Media Queries](#preprocessors-media-queries) 
1. [CSS Preprocessors Comments](#preprocessors-comments)


<a name="preprocessors-syntax"></a>
### 5.1. CSS Preprocessors Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```css
// Good
.nav-item 
  display inline-block  

// Bad
.nav-item 
    display inline-block  
```

Do not use semi-colons, commas or brackets

```css
// Good
.header 
  position fixed
  top 0
  right 0
  left 0

// Bad
.header {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
}
``` 

Keep one declaration per line.

```css
// Good
.selector-1,
.selector-2,
.selector-3 
  ...
 

// Bad
.selector-1, .selector-2, .selector-3 
  ... 
``` 

Separate nested ruleset by a blank line and blocks ruleset by a double blank line.

```css
// Good
.navbar 
  margin 0 0 20px

  li 
    display inline-block


.nav 
  display block

  li 
    float left


// Bad
.navbar 
  margin 0 0 20px 
  li 
    display inline-block 
.nav 
  display block 
  li 
    float left
``` 

Use **$** for the variables.

```css
// Good
$gray-darker  = #111
$gray-dark    = #393C45
$gray         = #555
$gray-light   = #aaa
$gray-lighter = #ECF1F5
$gray-white   = #fbfbfb
```

<a name="preprocessors-performance"></a>
### 5.2. CSS Preprocessors Performance

Warning with nesting rules of preprocessors. Continue keep without nesting.

```css
// Good
.nav-item 
  ...

// Bad
.navbar 
  .nav 
    .nav-item 
      ... 
```

**Do not use @extends**, [always use mixins](http://csswizardry.com/2016/02/mixins-better-for-performance/).

```css
reset(arg = '')
  
  if (arg == list) 
    margin 0
    padding-left 0
    list-style none
    
  if (arg == form)  
    background 0
    border 0
    padding 0

.nav
  reset(list)

.btn
  reset(form)
```
 
<a name="preprocessors-media-queries"></a>
### 5.3. CSS Preprocessors Media Queries

Provide the media queries rules inside the element.

```css 
.navbar 
  position absolute
  top 5px
  z-index 5
   
  @media (min-width $screen-sm) 
    position fixed
    margin-right $space-sm
  
  @media (min-width $screen-md)  
    right 0 
    top 10px 
```
 
<a name="preprocessors-comments"></a>
### 5.4. CSS Preprocessors Comments

Provide one summary on header of files.

```css 
//  
// Variables
//
// 1. Colors
// 2. Spaces 
// 3. Media Queries 
// 4. Typography
//
// ===============================================================

// 
// 1. Colors
// --------------------------------------------------

...

// 
// 2. Spaces
// --------------------------------------------------

...
```

For main element. 

```css  
// 
// 1. Header
// -------------------------------------------------- 
... 
```

For children elements. 

```css   
// 1.1 Header Item
// -------------------------------------------------- 
...
```

For generic comments

```css   
// Simple comment

// Block
// Comment
...
``` 

<a name="js"></a>
## 6. JavaScript

The main influences for the JavaScript rules are [idiomatic.js](https://github.com/rwldrn/idiomatic.js/) and [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style/).

### JavaScript Summary

1. [Javascript Syntax](#js-syntax)
1. [Javascript Variables](#js-variables)
1. [Javascript Performance](#js-performance)
1. [Javascript and HTML5 Data Attributes](#js-data-attributes)
1. [Javascript Comments](#js-comments)

<a name="js-syntax"></a>
### 6.1. JavaScript Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```js
// Good
while (condition) {
  statements
}

// Bad
while (condition) {
    statements
}
```

Always use semicolons.

```js
// Good
var me = $(this);
test();

// Bad
var me = $(this)
test()
```

Always use single quotes.

```js
// Good
var string = '<p class="foo">Lorem Ipsum</p>';
var noteClick = me.attr('data-note');

// Bad
var string = "<p class='foo'>Lorem Ipsum</p>";
var noteClick = me.attr("data-note");
```

Keep `else` in the same line of closure of the `if`.

```js
// Good
if ( true ) {
  ...
} else {
  ...
}

// Bad
if ( true ) {
  ...
}
else {
  ...
}
```

Add spaces between operators.

```js
// Good
for (i = 0; i < 10; i++) {
  ...
}

// Bad
for (i=0;i<10;i++) {
  ...
}
```

Never add a space between the keyword function and the function name.

```js
// Good
foo(function() {
  ...
});

// Bad
foo ( function () {
  ...
});
```

Add spaces outside parentheses `()` but avoid it inside.

```js
// Good
if (condition) {
  statement
}

// Bad
if( condition ){
  statement
}
```

For conditionals always use curly brackets `{}`.

```js
// Good
if (condition) {
  statement
} else if (condition) {
  statement
} else {
  statement
}

// Bad
if (condition) statement;
else if (condition) statement;
else statement;
```

For strict equality checks `===` should be used in favor of `==`.

```js
// Good
if (foo === 'foo') {
  statement
}

// Bad
if (foo == 'foo') {
  statement
}
```

<a name="js-variables"></a>
### 6.2. JavaScript Variables

All variables should be declared before used.

```js
// Good
var me = $(this);
var noteClick = me.attr('data-note');
notes[noteClick].play();

// Bad
notes[noteClick].play();
var me = $(this);
var noteClick = me.attr('data-note');
```

Always use `var` to declare variables.

```js
// Good
var me = $(this);

// Bad
me = $(this);
```

<a name="js-performance"></a>
### 6.3. JavaScript Performance

Use [JSHint](http://www.jshint.com/) to detect errors and potential problems.

Always minify and concat the JavaScript code. Task builders like [Grunt](http://gruntjs.com/) leaves this easier.

<a name="js-data-attributes"></a>
### 6.4. JavaScript and HTML5 Data Attributes

Avoid using classes to start in a JavaScript interaction. To do so, use ***HTML5 Data Attributes***.

```js
// Good
$('[data-toggle="tab"]');

// Bad
$('.tab');
```

This approach makes the classes are only responsible for styling.

Thus elements that share the same style, but do not have the same interaction, may function separately.

<a name="js-comments"></a>
### 6.5. JavaScript Comments

A single line above the code that is commented.

```js
// Good
// Good example of comment
var me = $(this);

// Bad
var me = $(this); // Bad example of comment
```

<a name="boilerplate"></a>
## 7. Boilerplate

I have a boilerplate using this coding style. 

<p>
  <img src="https://cloud.githubusercontent.com/assets/3603793/14390922/a999424c-fd8f-11e5-8fbb-ab908a1d4740.png" width="100">
</p>

It's call [Kratos Boilerplate](https://github.com/LFeh/kratos-boilerplate).

<a name="references"></a>
## 8. References

* [Code Guide by @mdo](https://github.com/mdo/code-guide)
* [idiomatic CSS](https://github.com/necolas/idiomatic-css/)
* [idiomatic.js](https://github.com/rwldrn/idiomatic.js/)
* [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style/)
* [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

<a name="translations"></a>
## 9. Translations

* [Português (Brasil)](/translations/pt-BR/)
* [Russian (by Vbifonixor)](https://github.com/vbifonixor/coding-style)

<a name="license"></a>
## 10. License

[MIT License](http://felipefialho.mit-license.org/) © Luiz Felipe Tartarotti Fialho
