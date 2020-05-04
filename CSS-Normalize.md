# CSS: [Normalize](https://github.com/sindresorhus/modern-normalize)

<!-- MarkdownTOC -->

- [Box Related](#box-related)
    - [Box Model](#box-model)
    - [Margin](#margin)
- [Position Related](#position-related)
    - [Position](#position)
    - [Alignment](#alignment)
    - [Bottom & Top](#bottom--top)
- [Words Related](#words-related)
    - [Tab Size](#tab-size)
    - [Line Height](#line-height)
    - [Font Weight](#font-weight)
    - [Font Size](#font-size)

<!-- /MarkdownTOC -->

WIP.

Explain to myself one line by one line.

usage:

```html
<link rel="stylesheet" type="text/css" href="./modern-normalize.css">
```

## Box Related

### Box Model

According to [Don't inherit box-sizing by default by jamiebuilds · Pull Request #37](https://github.com/sindresorhus/modern-normalize/pull/37), the following is better than [Universal Box Sizing with Inheritance](https://css-tricks.com/box-sizing/):

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

### Margin

```css
body {
    margin: 0;
}

button,
input,
optgroup,
select,
textarea {
    margin: 0;
}
```

## Position Related

### Position

```css
sub,
sup {
    position: relative;
    vertical-align: baseline;
}
```

### Alignment

### Bottom & Top

According to [bottom - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom), 

- `position: absolute;` or `position: fixed;`
    - `bottom` sets the distance between the element's bottom edge and the bottom edge of its parent.
- `position: relative;`
    - the bottom property specifies the distance the element's bottom edge is moved above its normal position.
- `position: sticky;`
    - the bottom property is used to compute the sticky-constraint rectangle.
- `position: static;`
    - bottom property has no effect.


```css
sub {
    bottom: -0.25em;
}

sup {
    top: -0.5em;
}
```

## Words Related

### Tab Size

4 rather than 8 does look better, although some renderers automatically translate tabs into spaces, making this fix obsolete.

```css
:root {
    -moz-tab-size: 4;
    tab-size: 4;
}
```

### Line Height

According to [1.4.8 Visual Presentation - Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/2008/REC-WCAG20-20081211/#visual-audio-contrast-visual-presentation), line height should be at least 1.5, so you should not solely rely on normalisation here.

```css
html {
    line-height: 1.15;
}

sub,
sup {
    line-height: 0;
}

button,
input,
optgroup,
select,
textarea {
    line-height: 1.15;
}
```

### Font Weight

```css
b,
strong {
    font-weight: bolder;
}
```

### Font Size

```css
code,
kbd,
samp,
pre {
    font-size: 1em; /* 2 */
}

small {
    font-size: 80%;
}

sub,
sup {
    font-size: 75%;
}
```
