Meu Estilo de Código
============

> "Toda linha de código deve parecer que foi escrita por uma única pessoa, não importa a quantidade de contribuidores." - Provérbio Chinês

O documento a seguir descreve as regras de escrita nas linguagens de desenvolvimento que utilizo: HTML, CSS e Javascript.

A ideia desse repositório é ter um local para que eu e outros desenvolvedores que participem dos meus projetos conseguirem se informar dos padrões de códigos usados.

Como este é um novo documento, algumas regras podem não ter sido aplicadas em projetos antigos.

Este é um documento vivo e mudanças podem acontecer a qualquer momento.

## Sumário

1. [Commits] (#commits)
1. [HTML] (#html)
1. [CSS] (#css)
1. [Javascript] (#js)
1. [Referências](#references)
1. [Traduções](#translations)
1. [Licença](#license)

<a name="commits"></a>
## 1. Commits

Para facilitar a contribuição de qualquer pessoa nos projetos, todas as mensagens de commit, pull requests ou discussões devem ser em **Inglês**.

Antes de commitar ajustes no projeto, verifique se existe uma issue aberta e faça referência a ela usando '#' na sua mensagem de commit.

```javascript
// Bom
git commit -m "Add placeholder in input #10"

// Ruim
git commit -m "Add placeholder in input"
```

<a name="html"></a>
## 2. HTML

A principal influencia das regras de HTML é o [Code Guide by @mdo](https://github.com/mdo/code-guide).

### HTML Sumário

1. [HTML Sintaxe] (#html-syntax)
1. [HTML Comentários] (#html-comments)
1. [HTML Encoding de Caractéres] (#html-encoding)
1. [HTML Ordem dos Atributos] (#html-attribute-order)
1. [HTML Performance] (#html-performance)
1. [HTML Código Base] (#html-base)

<a name="html-syntax"></a>
### 2.1. HTML Sintaxe

Use soft-tabs com dois espaços. Você pode configurar o seu editor dessa forma.

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

Sempre use aspas duplas.

```html
<!-- Good -->
<div class="main">

<!-- Bad-->
<div class='main'>
```

Não inclua `/` em elementos viúvos.

```html
<!-- Good -->
<hr>

<!-- Bad-->
<hr />
```

Separe os blocos usando uma linha em branco e agrupe os elementos internos do bloco.

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
### 2.2. HTML Comentários

Siga esta regra para adicionar comentários no HTML

```html
<!-- Este é um bom exemplo -->
<!-- /Fechando um bom exemplo -->
```

<a name="html-encoding"></a>
### 2.3. HTML Encoding de Caractéres

Sempre use UTF-8 para encoding de caractéres.

```html
<head>
  <meta charset="UTF-8">
</head>
```

<a name="html-attribute-order"></a>
### 2.4. HTML Ordem dos Atributos

Os atributos do HTML devem estar na seguinte ordem para facilitar a leitura.

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

### CSS Sumário

1. [CSS Syntax] (#css-syntax)
1. [CSS Declaration Order] (#css-order)
1. [CSS Class Name] (#css-class-name)
1. [CSS Performance] (#css-performance)
1. [Mobile First and Media Queries] (#mobile-first-and-media-queries)
1. [Pre-Processors] (#css-pre-processors)
1. [CSS Comments] (#css-comments)

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
### 3.2. CSS Declaration Order

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
### 3.3. CSS Class Name

Keep classes lowercase and use dashes.

```css
/* Good */
.nav-item { ... }

/* Bad */
.NavItem { ... }
.nav_item { ... }
```

Dashes serve as natural breaks in related class. Prefix classes based on the closest parent or base class.

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
### 3.4. CSS Performance

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

Avoid nesting elements, the preference is always to use classes.

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

<a name="mobile-first-and-media-queries"></a>
### 3.5 Mobile First and Media Queries

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

<a name="css-pre-processors"></a>
### 3.6. Pre-Processors

I use pre-processors in all projects. Today I use `LESS`.

Warning with nesting rules of pre-processors. Continue keep without nesting.

```css
/* Good */
.nav-item { ... }

/* Bad */
.navbar {
  .nav {
    .nav-item {
      ...
    }
  }
}
```

Provide generic names with variables.

```css
/* Good */
@brand-primary: #049cdb;

/* Bad */
@color-blue: #049cdb;
```

<a name="css-comments"></a>
### 3.7. CSS Comments

All comments must be made using the syntax of the preprocessor in use.

```js
//
// Section
// --------------------------------------------------

// Sub-section
// --------------------------------------------------

//
// Commentary block
//
//

// Commentary
```

<a name="js"></a>
## 4. Javascript

<a name="references"></a>
## 5. Referências

* [Code Guide by @mdo](https://github.com/mdo/code-guide)
* [idiomatic CSS](https://github.com/necolas/idiomatic-css/)
* [idiomatic.js](https://github.com/rwldrn/idiomatic.js/)
* [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style/)

<a name="translations"></a>
## 6. Traduções

* [English](/)

<a name="license"></a>
## 7. Licença

[MIT License](http://felipefialho.mit-license.org/) © Luiz Felipe Tartarotti Fialho
