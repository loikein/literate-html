# CSS: Main Style

<!-- MarkdownTOC -->

- [`@font-face`](#font-face)
- [`html` and `body`](#html-and-body)
	- [Background](#background)
	- [Font Size](#font-size)
	- [Font Face](#font-face-1)
	- [Stop Safari from Horizontal Scrolling](#stop-safari-from-horizontal-scrolling)
- [`header` and `footer`](#header-and-footer)
- [`main`](#main)

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
	background: #222;
}
```

### Font Size

[The `rem` method](https://snook.ca/archives/html_and_css/font-size-with-rem) is very cool. 

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
	font-display: swap;
}

.regular { font-weight: 300; }
.bold { font-weight: 700; }
```

### Stop Safari from Horizontal Scrolling

```css
html, body {
	/* these must be in both tags */
	overflow-x: hidden;
	height: 100%;
	transform: translate3d(0,0,0);
}
```

## `header` and `footer`

## `main`

