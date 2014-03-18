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
1. [HTML Encoding de Caracteres] (#html-encoding)
1. [HTML Ordem dos Atributos] (#html-attribute-order)
1. [HTML Performance] (#html-performance)
1. [HTML Código Base] (#html-base)

<a name="html-syntax"></a>
### 2.1. HTML Sintaxe

Use soft-tabs com dois espaços. Você pode configurar o seu editor dessa forma.

```html
<!-- Bom -->
<nav class="nav">
  <ul class="nav-menu">
    <li class="nav-item">
      <a class="nav-link">

<!-- Ruim -->
<nav class="nav">
      <ul class="nav-menu">
            <li class="nav-item">
                  <a class="nav-link">
```

Sempre use aspas duplas.

```html
<!-- Bom -->
<div class="main">

<!-- Ruim -->
<div class='main'>
```

Não inclua `/` em elementos viúvos.

```html
<!-- Bom -->
<hr>

<!-- Ruim -->
<hr />
```

Separe os blocos usando uma linha em branco e agrupe os elementos internos do bloco.

```html
<!-- Bom -->
<ul class="nav-tabs">
  <li>...</li>
  <li>...</li>
  <li>...</li>
  <li>...</li>
</ul>

<div class="tab-content">
  ...
</div>

<!-- Ruim -->
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
### 2.3. HTML Encoding de Caracteres

Sempre use UTF-8 para encoding de caracteres.

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

Nos includes dos arquivos CSS e Javascript não é necessário especificar o tipo de arquivo como `text/css` e `text/javascript.

```html
<!-- Bom -->
<link rel="stylesheet" href="assets/css/style.css" />
<script src="scripts.min.js"></script>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
<body>
```

Para uma melhor performance, todos os arquivos javascripts devem estar antes de fechar o `<body>`, no fim do documento.

```html
<!-- Bom -->
<script src="scripts.min.js"></script>
</body>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
<body>
```

Quando o projeto usar apenas HTML, sempre minifique o código. Automatizadores de tarefas como o [Grunt](http://gruntjs.com/) tornam isso muito mais fácil.

```html
<!-- Bom -->
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
### 2.6. HTML Código Base

O código a seguir é uma base em HTML para iniciar rápidamente os projetos.

```html
<!DOCTYPE html>
<html lang="en">
<head>

<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="format-detection" content="telephone=no">
<meta name="viewport" content="width=device-width">

<link rel="shortcut icon" href="assets/img/ico/favicon.ico" />
<link rel="logo" type="image/svg" href="../assets/img/logo/logo.svg" />
<link rel="stylesheet" href="assets/css/style.css" />

<title></title>

</head>
<body>

<!-- Scripts -->
<script src="assets/js/scripts.min.js"></script>

</body>
</html>
```

Para fornecer suporte para versões antigas do Internet Explorer...

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

A principal influencia para as regras de CSS são o [Code Guide by @mdo](https://github.com/mdo/code-guide) e o [idiomatic CSS](https://github.com/necolas/idiomatic-css/).

### CSS Sumário

1. [CSS Sintaxe] (#css-syntax)
1. [CSS Ordem de Declaração] (#css-order)
1. [CSS Nome das Classes] (#css-class-name)
1. [CSS Performance] (#css-performance)
1. [Mobile First e Media Queries] (#mobile-first-and-media-queries)
1. [Pre-Processores] (#css-pre-processors)
1. [CSS Comentários] (#css-comments)

<a name="css-syntax"></a>
### 3.1. CSS Sintaxe

Use soft-tabs com dois espaços. Você pode configurar o seu editor dessa forma.

```css
/* Bom */
.nav-item {
  display: inline-block;
  margin: 0 5px;
}

/* Ruim */
.nav-item {
    display: inline-block;
    margin: 0 5px;
}
```

Sempre use aspas duplas.

```css
/* Bom */
[type="text"]
[class^="..."]

.nav-item:after {
  content: "";
}

/* Ruim */
[type='text']
[class^='...']

.nav-item:after {
  content: '';
}
```

Inclua um espaço antes de abrir o `}` da regra.

```css
/* Bom */
.header {
  ...
}

/* Ruim */
.header{
  ...
}
```

Inclua um espaço depois do `:` da declaração.

```css
/* Bom */
.header {
  margin-bottom: 20px;
}

/* Ruim */
.header{
  margin-bottom:20px;
}
```

Inclua um `;` no fim da declaração.

```css
/* Bom */
.header {
  margin-bottom: 20px;
}

/* Ruim */
.header{
  margin-bottom:20px
}
```

Mantenha uma declaração por linha.

```css
/* Bom */
.selector-1,
.selector-2,
.selector-3 {
  ...
}

/* Ruim */
.selector-1, .selector-2, .selector-3 {
  ...
}
```

Declarações únicas devem ficar em uma linha.

```css
/* Bom */
.selector-1 { width: 50%; }

/* Ruim */
.selector-1 {
  width: 50%;
}
```

Separe as regras por uma linha em branco.

```css
/* Bom */
.selector-1 {
  ...
}

.selector-2 {
  ...
}

/* Ruim */
.selector-1 {
  ...
}
.selector-2 {
  ...
}
```

Use caixa-baixa, valores hexadecimais reduzidos e não especifique unidades quando o valor é zero.

```css
/* Bom */
.selector-1 {
  color: #aaa;
  margin: 0;
}

/* Ruim */
.selector-1 {
  color: #AAAAAA;
  margin: 0px;
}
```

<a name="css-order"></a>
### 3.2. CSS Ordem de Declaração

As declarações devem ser adicionadas em ordem alfabética.

```css
/* Bom */
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

/* Ruim */
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
### 3.3. CSS Nome das Classes

Mantenha as classes em caixa-baixa e use hífen para separar os nomes.

```css
/* Bom */
.nav-item { ... }

/* Ruim */
.NavItem { ... }
.nav_item { ... }
```

Hífens servem como uma transação natural entre classes relacionadas. O primeiro nome deve ser baseado no parente imediato da classe que deseja criar.

```css
/* Bom */
.navbar { ... }
.nav { ... }
.nav-item { ... }
.nav-link { ... }

/* Ruim */
.item-nav { ... }
.link-nav { ... }
```

Evite usar nomes muito curtos e sempre use nomes relacionados com a função da classe.

```css
/* Bom */
.btn { ... }
.page-header { ... }
.progress-bar { ... }

/* Ruim */
.s { ... }
.ph { ... }
.block { ... }
```

<a name="css-performance"></a>
### 3.4. CSS Performance

Nunca use IDs.

```css
/* Bom */
.header { ... }
.section { ... }

/* Ruim */
#header { ... }
#section { ... }
```

Não use seletores padrões para regras genéricas. Sempre use classes.

```css
/* Bom */
.form-control { ... }
.header { ... }
.section { ... }

/* Ruim */
input[type="text"] { ... }
header
section
```

Evite elementos aninhados. A preferência é sempre para o uso de classes.

```css
/* Bom */
.navbar { ... }
.nav { ... }
.nav-item { ... }
.nav-link { ... }

/* Ruim */
.navbar ul { ... }
.navbar ul li { ... }
.navbar ul li a { ... }
```

Aninhe somente quando precisar alterar o comportamento de uma classe por interferência de outra. Mantenha um limite de três elementos aninhados.

```css
/* Bom */
.modal-footer .btn { ... }
.progress.active .progress-bar { ... }

/* Ruim */
.modal-btn { ... }
.progress.active .progress-bar .progress-item span { ... }
```

Sempre minifique o código CSS.
Always minify the CSS code. Automatizadores de tarefas como o [Grunt](http://gruntjs.com/) tornam isso muito mais fácil.

```css
<!-- Bom -->
.navbar { ... }.nav { ... }.nav-item { ... }.nav-link { ... }

<!-- Bad -->
.nav-item {
  ...
}
.nav-link {
  ...
}
```

<a name="mobile-first-and-media-queries"></a>
### 3.5 Mobile First and Media Queries

Comece o desenvolvimento usando regras genéricas e adiciona media queries começando com mobile. Compartilho um artigo com mais informações, [CSS Modular com Mobile First](http://www.felipefialho.com/blog/2014/css-modular-com-mobile-first/).

```css
/* Bom */
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

/* Ruim */
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

Mantenha os media queries o mais próximo possível da regra que deseja alterar. Não coloque em documentos separados ou no fim do stylesheet.

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
### 3.6. Pré-Processores

Eu uso pré-processadores em todos os projetos. Atualmente estou usando `LESS`.

Cuidado com a facilidade de aninhar elementos com os pré-processadores. Continue evitando aninhamentos.

```css
/* Bom */
.nav-item { ... }

/* Ruim */
.navbar {
  .nav {
    .nav-item {
      ...
    }
  }
}
```

Forneça nomes genéricos para as variaveis.

```css
/* Bom */
@brand-primary: #049cdb;

/* Ruim */
@color-blue: #049cdb;
```

<a name="css-comments"></a>
### 3.7. CSS Comentários

Todos os comentários devem ser feitos usando a sintaxe do pré-processador em uso.

```js
//
// Seção
// --------------------------------------------------

// Sub-seção
// --------------------------------------------------

//
// Bloco de comentário
//
//

// Comentário simples
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
