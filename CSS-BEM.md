# CSS: Block Element Modifier

<!-- MarkdownTOC -->

- [Articles](#articles)
- [Naming Conventions](#naming-conventions)
- [Basic Ideas](#basic-ideas)
    - [Example: Mix & Match](#example-mix--match)
    - [Example: Open & Closed](#example-open--closed)
- [Details](#details)
    - [Names for Modifiers](#names-for-modifiers)
    - [Modifier vs Mix](#modifier-vs-mix)

<!-- /MarkdownTOC -->


## Articles

- [CSS / Methodology / BEM](https://en.bem.info/methodology/css/)
    - 中文介绍：[BEM | Summer。桑莫。夏天](https://cythilya.github.io/2018/05/22/bem/)
- [Semantic UI](https://semantic-ui.com/)
- [Maintainable CSS with BEM ⋆ Mark McDonnell](https://www.integralist.co.uk/posts/bem/)
- [MaintainableCSS - an approach to writing modular, scalable and maintainable CSS | By Adam Silver](https://maintainablecss.com/chapters/introduction/)
    - 中文总结：[可維護的 CSS - 弦而時習之](https://blog.frost.tw/posts/2017/03/05/Talk-about-maintainable-css/)


## Naming Conventions

Considering both [Naming convention / Methodology / BEM](https://en.bem.info/methodology/naming-convention/) and [Naming - BEM](http://getbem.com/naming/), I use the following:

```
block-name__elem-name_mod-name--mod-val
```

- General
    - All lowercase letters.
    - Words are separated by a hyphen (`-`).
- Block name defines the namespace for its elements and modifiers.
- Element name is separated by a double underscore (`__`).
- Modifier name is separated by a single underscore (`_`).
    - Modifier value is by a double hyphen (`--`).
    - For boolean modifiers, the value is not included in the name.

Use this pic as example,

![](http://getbem.com/assets/github_captions.jpg)

```css
/* Blocks */
.logo{ ; }
.input{ ; }
.menu{ ; }
.button{ ; }

/* Elements */
.menu__item{ ; }

/* Modifiers */
.menu__item_state--active{ border-bottom: 3px solid green; }
.input_size--big{ font-size: 1.5em; }
.button_state--success{ color: white; background: green; }
```

## Basic Ideas

1. No wrappers.
1. No group selectors.
1. No elements of elements.
1. `id` is for links and links only.
1. [Everything is a `class`](https://en.bem.info/methodology/css/#combining-a-tag-and-a-class-in-a-selector) (but you should try to keep the HTML semantic for sanity's sake).
1. Include base [block name alongside modifier and element names](https://en.bem.info/methodology/faq/#why-include-the-block-name-in-modifier-and-element-names).
1. [Mix and much](https://en.bem.info/methodology/css/#external-geometry-and-positioning).
1. [Open for extension by modifiers, closed for changes](https://en.bem.info/methodology/css/#openclosed-principle).

### Example: Mix & Match

> The `button` block doesn't specify any margin, so it can easily be reused anywhere.
> 
> ```html
> <header class="header">
>     <button class="button header__button">...</button>
> </header>
> ```
> 
> ```css
> .header{ ; }
> .button {
>     font-family: 'Arial', sans-serif;
>     text-align: center;
>     border: 1px solid black; /* Frame */
> }
> .header__button {
>     margin: 30px; /* Padding */
>     position: relative;
> }
> ```

### Example: Open & Closed

> Good code:
> 
> ```html
> <button class="button">...</button>
> <div class="content">
>     <button class="button button_size--small">...</button>
> </div>
> ```
> 
> ```css
> .button {
>     font-family: 'Arial', sans-serif;
>     text-align: center;
>     font-size: 11px;
>     line-height: 20px;
> }
> 
> .button_size--small {
>     font-size: 13px;
>     line-height: 24px;
> }
> ```

\-

> Bad code 1: you should not modify by context
> 
> ```css
> .button {
>     font-family: 'Arial', sans-serif;
>     text-align: center;
>     font-size: 11px;
>     line-height: 20px;
> }
> 
> .content .button {
>     font-size: 13px;
>     line-height: 24px;
> }
> ```

> Bad code 2: you should not modify the original class directly
> 
> ```css
> .button {
>     font-family: 'Arial', sans-serif;
>     text-align: center;
>     font-size: 13px;
>     line-height: 24px;
> }
> ```


## Details

### Names for Modifiers

According to [How to choose a name for a modifier?](https://en.bem.info/methodology/faq/#how-to-choose-a-name-for-a-modifier):

> Good code: informative
> 
> ```html
> <button class="button button_view--action">...</button>
> ```

\-

> Bad code: what are you talking about>
> 
> ```html
> <button class="button button_background--yellow">...</button>
> ```

### Modifier vs Mix

According to [A modifier or a mix: which one should I create? / FAQ / Methodology / BEM](https://en.bem.info/methodology/faq/#why-not-create-wrapper-blocks),

- Use modifier if the implementation is reusable.
- Use mix if the implementation is context-specific.
