# CSS: Accessibility

<!-- MarkdownTOC -->

- [`:focus`](#focus)
- [`a`](#a)
    - [`:hover`](#hover)
    - [`:visited`](#visited)
- [Hidden Accessibility Links](#hidden-accessibility-links)

<!-- /MarkdownTOC -->


Main refs:

- [Dive Into Accessibility](https://web.archive.org/web/20110927131211/http://diveintoaccessibility.org/) ([中文翻译](http://dia.z6i.org/)), refreshed according to CSS3.
- [CSS and JavaScript accessibility best practices - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript) ([中文翻译](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility/CSS%E5%92%8CJavaScript))
- [WebAIM: Accessible CSS](https://webaim.org/techniques/css/)
- [Visual design | Accessibility for Teams](https://accessibility.digital.gov/visual-design/getting-started/)
- [Styling form controls with CSS, revisited | 456 Berea Street](https://www.456bereastreet.com/archive/200701/styling_form_controls_with_css_revisited/)

## `:focus`

- `:focus` is [not only for links](https://www.w3.org/WAI/WCAG21/Techniques/css/C15).
- When necessary, consider [using JavaScript](https://www.w3.org/WAI/WCAG21/Techniques/client-side-script/SCR31.html) to make things `focus`-able.

Here's an example that I adapted from [Inclusive Design Principles](https://inclusivedesignprinciples.org/). Put it below styles for `html` and `body`, above everything else.

```css
:focus:not([tabindex="-1"]) {
  outline: 3px solid orange;
  outline-offset: 3px;
  border: 0;
}
```

## `a`

Add at least 1 more style in addition to colour should be there.  
(E.g., the link style of GitHub markdown is bad.)

Good example: 

```css
.link--fancy {
    text-decoration: none;
    color: blue;
    border-bottom: 1px solid var(--theme-color-1);
}
```

### `:hover`



### `:visited`

I argue for the case that <u>style for `:visited` should be positioned after `:focus`</u>, since those who need the reminding function of `:visited` will still need it when the link is `:focus`-ed.  




## Hidden Accessibility Links

Here's an example that I adapted from what Google does:

```html
<body>
<section class="a11y-links">
    <a class="a11y-links__link" tabindex="0" href="#article-title">Skip to main content</a>
    <a class="a11y-links__link" tabindex="0" href="#accessibility-statement">Accessibility statement</a>
</section>
…
```

```css
.a11y-links {
    align-items: center;
    background-color:  var(--white);
    box-shadow:0 0px 1.3px rgba(0, 0, 0, 0.184),
                0 0px 5.1px rgba(0, 0, 0, 0.198),
                0 0px 20px rgba(0, 0, 0, 0.2);
    margin: 10rem auto 0 0;
    position: absolute;
    z-index: 1000;
}

.a11y-links__link:not(:focus) {
    clip: rect(1px,1px,1px,1px);
    position: absolute;
    padding: 0;
}

.a11y-links__link {
    /* style when focused */
    cursor: pointer;
    display: inline-block;
    margin: 1em;
}
```

