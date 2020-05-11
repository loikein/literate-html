# HTML: Accessibility

<!-- MarkdownTOC -->

- [Semantic HTML](#semantic-html)
- [`lang`](#lang)
- [Meaningful Tab Order](#meaningful-tab-order)
- [`img`](#img)
- [`a`](#a)
    - [`target` vs `rel`](#target-vs-rel)
    - [`title`](#title)
- [`table`: `caption` & `scope`](#table-caption--scope)
- [`form`](#form)
- [Skip Navigation & Other Accessibility Links](#skip-navigation--other-accessibility-links)
- [`accesskey`](#accesskey)
- [Accessibility Statement](#accessibility-statement)

<!-- /MarkdownTOC -->

Main refs:

- [Dive Into Accessibility](https://web.archive.org/web/20110927131211/http://diveintoaccessibility.org/) ([中文翻译](http://dia.z6i.org/)), refreshed according to HTML5.
- [Home | 18F Accessibility Guide](https://accessibility.18f.gov/)
- [Front-end development | Accessibility for Teams](https://accessibility.digital.gov/front-end/getting-started/)
- [HTML: A good basis for accessibility - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML) ([中文版本](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility/HTML:%E4%B8%BA%E5%8F%AF%E8%AE%BF%E9%97%AE%E6%80%A7%E6%8F%90%E4%BE%9B%E4%B8%80%E4%B8%AA%E8%89%AF%E5%A5%BD%E7%9A%84%E5%9F%BA%E7%A1%80))
- [How to Meet WCAG (Quickref Reference)](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#meaningful-sequence)
- [How I do an accessibility check -- A11ycasts #11 - YouTube](https://www.youtube.com/watch?v=cOmehxAU_4s&feature=youtu.be)

## Semantic HTML

…is the principle.

## `lang`

You should specify the language of every document, as well as every element that is using different languages. This helps screen reader users, as well as those who need translation to read your document.

For example:

```html
<html lang="en">
    ...
    <blockquote lang="de">
    ...
    </blockquote>
```

## Meaningful Tab Order

- Usually this can be achieved by write the `html` document [in a similar order as how it should be presented](https://www.w3.org/WAI/WCAG21/Techniques/general/G59).
- You should [not set positive `tabindex`](https://developer.paciellogroup.com/blog/2014/08/using-the-tabindex-attribute/) unless 100% sure, and never do so if you are building some [components that would be used by others](https://adrianroselli.com/2014/11/dont-use-tabindex-greater-than-0.html).
- It is a good idea to assign a group of elements the same `tabindex`, [as in the Example 3 here](https://www.w3.org/WAI/WCAG21/Techniques/html/H4.html). Combined with point 2, this means most of the time you would be writing `tabindex="0"`.

## `img`

Every `<img>` should have an `alt`, and [no title](https://developer.paciellogroup.com/blog/2013/01/using-the-html-title-attribute-updated/).

```html
<img src="smiley.jpeg" alt="a smiley face">
```

If some image is there solely for aesthetic reasons, it should have an empty alt.

```html
<img src="fancy-hr.png" alt="">
```

<!-- 
```html
<img src="smiley.jpeg" alt="a smiley face" title="Smiley face of John Smith">
```
 -->

## `a`

### `target` vs `rel`

- Do not use `target="_blank"`
- Do use `rel="noopener noreferrer"`

### `title`

You should give `title` to every link that is discriptive enough about what it points to.

For example:

```html
<!-- this link does not need title -->
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title"
   rel="noopener noreferrer">
    title - HTML: Hypertext Markup Language | MDN
</a>

<!-- this link needs a title -->
Let us talk about 
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title"
   title="reference page of title attribute on MDN"
   rel="noopener noreferrer">
    title
</a>.
```


## `table`: `caption` & `scope`

Every `<table>` should have a `<caption>` that specifies the contents.

```html
<table>
    <caption>Types of Capsule Coffee</caption>
    <tr>
        <td> </td>
        <th scope="col">Normal</th>
        <th scope="col">Decaf</th>
    </tr>
    <tr>
        <th scope="row">Aluminium</th>
        <td>OK</td>
        <td>OK</td>
    </tr>
    <tr>
        <th scope="row">Paper</th>
        <td>No</td>
        <td>OK</td>
    </tr>
</table>
```

## `form`

WIP

Ref: 

- [Forms | UX design | Accessibility for Teams](https://accessibility.digital.gov/ux/forms/)
- [Forms | Visual design | Accessibility for Teams](https://accessibility.digital.gov/visual-design/forms/)

## Skip Navigation & Other Accessibility Links

Ref: [2.4.1 Bypass Blocks - Guideline 2.4 Navigable - How to Meet WCAG (Quickref Reference)](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#bypass-blocks)

- Every document should include a [skip navigation button](https://webaim.org/techniques/skipnav/).
- You can hide the accessibility links using CSS. See [CSS Accessibility](./CSS-accessibility.md#hidden-accessibility-links).


## `accesskey`

There is no [universal standards](https://www.standardaccesskeys.com/SAK2014/#spec), but you probably want to [point `accesskey`'s to the number keys](https://www.sitepoint.com/community/t/access-keys-is-there-a-standard/51430).

> UK Government recommendation for access keys:
> 
> * S - Skip navigation
> * 1 - Home page
> * 2 - What's new
> * 3 - Site map
> * 4 - Search
> * 5 - Frequently Asked Questions (FAQ)
> * 6 - Help
> * 7 - Complaints procedure
> * 8 - Terms and conditions
> * 9 - Feedback form
> * 0 - Access key details

So you should at least have:

```html
<a href="index.html" 
   accesskey="1">Home</a>
<a href="accessibility_statement.html" 
   accesskey="0">Accessibility Statement</a>
```

## Accessibility Statement

You have come so far. Write that damn statement to let users know they can do it.

Example: (to be added)
