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

The main influence for the HTML rules is the [Code Guide by @mdo](https://github.com/mdo/code-guide)

### HTML Summary

1. [Syntax] (#syntax) 
1. [Character encoding] (#encoding)
1. [Attribute order] (#attribute)
1. [Performance] (#html-performance)
1. [Old Browsers] (#old-browsers)
1. [Base Code] (#html-base)

<a name="syntax"></a>
### 2.1. Syntax

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

Always use double quotes

```html
<!-- Good -->
<div class="main">

<!-- Bad-->
<div class='main'>
```
  
Don't include a `/` in self-closing elements

```html
<!-- Good -->
<hr>

<!-- Bad-->
<hr />
```

Follow this rule to add comments in HTML

```html
<!-- This is a good example -->
<!-- /Closing a good example -->
```

<a name="encoding"></a>
### 2.2. Character encoding

Always use UTF-8 for character encoding

```html
<head>
  <meta charset="UTF-8">
</head>
```

<a name="attribute"></a>
### 2.3. Attribute order

HTML attributes should be in this order for facilitate the reading

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

No need to specify a type when including CSS and JavaScript files as `text/css` and `text/javascript`

```html
<!-- Good -->
<link rel="stylesheet" href="assets/css/style.css" />
<script src="scripts.min.js"></script> 

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
<body>
```

For a better performance, all javascripts files must be at the end of the code. Before closing the `<body>`

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
### 2.5. Base Code

The following code is a HTML base for faster start the projects

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

<a name="js"></a>
## 4. Javascript
 
<a name="references"></a>
## 5. References

* [Code Guide by @mdo](https://github.com/mdo/code-guide)
* [idiomatic.css](https://github.com/necolas/idiomatic-css/)
* [idiomatic.js](https://github.com/rwldrn/idiomatic.js/)
* [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style/) 

<a name="license"></a>

## 6. License
 
[MIT License](http://felipefialho.mit-license.org/) © Luiz Felipe Tartarotti Fialho
