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
### 2.1 Syntax

Use soft tabs with two spaces. You can configure your editor for this. 

```javascript
// Good
<nav class="nav">
  <ul class="nav-menu">
    <li class="nav-item">
      <a class="nav-link">

// Bad
<nav class="nav">
      <ul class="nav-menu">
            <li class="nav-item">
                  <a class="nav-link">
```

Always use double quotes

```javascript
// Good
<div class="main">

// Bad
<div class='main'>
```
  
Don't include a `/` in self-closing elements

```javascript
// Good
<hr>

// Bad
<hr />
```

<a name="encoding"></a>
### 2.2 Character encoding

Always use UTF-8 for character encoding

```html
<head>
  <meta charset="UTF-8">
</head>
```

<a name="attribute"></a>
### 2.3 Attribute order

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

<img src="..." alt="...">
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
