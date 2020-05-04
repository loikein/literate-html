# CSS: Main Style

<!-- MarkdownTOC -->

- [`@font-face`](#font-face)
- [`html` and `body`](#html-and-body)
    - [Background](#background)
    - [Font Size](#font-size)
    - [Font Face](#font-face-1)
    - [Vertical Scroll, Not Horizontal Scroll](#vertical-scroll-not-horizontal-scroll)
    - [Dark Mode](#dark-mode)
- [Top `header`](#top-header)
    - [Gradient Accent Colour](#gradient-accent-colour)
- [`main`](#main)
    - [`a` & `button`](#a--button)
- [Top `footer`](#top-footer)

<!-- /MarkdownTOC -->

The best part, really.

usage:

```html
<link rel="stylesheet" type="text/css" href="./style.css">
```

## `@font-face`

If you use [Google Fonts](https://fonts.google.com/), this is pretty easy.

Let's say I want to use Roboto 300 & 700, and my website only contains English. Add them, and take a look at the `Embed` tab:

```
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;700&display=swap" rel="stylesheet">
```

Copy the link in browser and take a look at the contents. All we need is the `/* latin */` parts:

```css
@font-face {
	font-family: 'Roboto';
	font-style: normal;
	font-weight: 300;
	font-display: swap;
	src: local('Roboto Light'), local('Roboto-Light'), url(https://fonts.gstatic.com/s/roboto/v20/KFOlCnqEu92Fr1MmSU5fBBc4AMP6lQ.woff2) format('woff2');
	unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
}

@font-face {
	font-family: 'Roboto';
	font-style: normal;
	font-weight: 700;
	font-display: swap;
	src: local('Roboto Bold'), local('Roboto-Bold'), url(https://fonts.gstatic.com/s/roboto/v20/KFOlCnqEu92Fr1MmWUlfBBc4AMP6lQ.woff2) format('woff2');
	unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
}
```

## `html` and `body`

[HTML vs Body in CSS | CSS-Tricks](https://css-tricks.com/html-vs-body-in-css/) ([中文翻译 by CSSPod](https://csspod.com/html-vs-body-in-css/))

### Background

[You should write `background`](https://stackoverflow.com/questions/10205464/what-is-the-difference-between-background-and-background-color) even if you only use solid colour.

Also, [you probably want to put the background in `body` tag](https://css-tricks.com/just-one-of-those-weird-things-about-css-background-on-body/).

```css
html {
	background: #F5F4F2;
}
```

### Font Size

You should not use `px` to set font sizes because it overwrites the browser settings that are very useful for people with non-perfect vision (such as me).

Instead, [the `rem` method](https://snook.ca/archives/html_and_css/font-size-with-rem) is very cool:

```css
html {
	font-size:62.5%; /* make 1rem = 10px */
}

body { font-size: 1.4rem; } /* =14px */
h1   { font-size: 2.4rem; } /* =24px */
```

### Font Face

```css
body {
	font-family: 'Roboto', sans-serif;
}

.regular { font-weight: 300; }
.bold { font-weight: 700; }
```

### Vertical Scroll, Not Horizontal Scroll

According to [html - why body overflow not working? - Stack Overflow](https://stackoverflow.com/questions/41506456/why-body-overflow-not-working), the best practice for `overflow` settings is to apply them to both `<html>` and `<body>`.

```css
html, body {
	overflow-y: auto;
	overflow-x: hidden;

	/* Safari compatibility */
	-webkit-overflow-scrolling: touch;

	/* only necessary when there is something overflowing */
	height: 100%;
	transform: translate(0, 0);
}
```

### Dark Mode

If you use variable for all colours, this will be [really easy](https://css-tricks.com/dark-modes-with-css/), and it switches automatically.

```css
html {
    --black: #222;
    --white: #F5F4F2;
    --whiter: #FFFFFF;
    --link: #E47D7D;
    --link_hover: #0079DA;
}

@media (prefers-color-scheme: dark) {
    html {
        --black: #F5F4F2;
        --white: #222;
        --whiter: #606060;
    }
}
```

If you want the user to be able to control the theme, [that's also possible in theory](https://dev.to/oahehc/how-to-enable-dark-mode-on-your-website-with-pure-css-ake), although I have not succeeded on my machine.  

<small class="side-note">The `+` selector only works for sibling elements.</small>

## Top `header`

### Gradient Accent Colour

Credit: [css - Border Position - Stack Overflow](https://stackoverflow.com/a/33943462/10668706)

```css
.top-header {
    position: relative;
    text-align: center; /* if this, then left: 0; is necessary */
    border-bottom: 1px solid lightgray;
    padding: 1rem;
    background: white;
}

/* all lines are necessary (why?) */
/* set all 5px's to different values for thicker or thinner lines*/

.fancy-header {
    border-top: 5px solid transparent;
}

.fancy-header::before {
    background: linear-gradient(120deg, rgba(0,121,218,1) 0%, rgba(228,125,125,1) 100%);
    content: '';
    position: absolute;
    width: 100%;
    height: 5px;
    top: -5px;
    left: 0; /* can remove if no text-align */
}
```


## `main`

### `a` & `button`

This article give great interactive examples for the different states: [When do the :hover, :focus, and :active pseudo-classes apply?](https://bitsofco.de/when-do-the-hover-focus-and-active-pseudo-classes-apply/)

For buttons: [css - What is the difference between :focus and :active? - Stack Overflow](https://stackoverflow.com/questions/1677990/what-is-the-difference-between-focus-and-active)

```css
.link-fancy {
    color: pink;
}

.link-fancy:hover,
.link-fancy:focus {
    color: blue;
}
```

## Top `footer`

