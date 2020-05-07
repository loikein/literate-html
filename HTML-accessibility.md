# Accessibility

<!-- MarkdownTOC -->

- [`lang`](#lang)
- [`alt` & `title` for `img`](#alt--title-for-img)
- [`a`](#a)
    - [`target` vs `rel`](#target-vs-rel)
    - [`title`](#title)
- [`caption` & `scope` for `table`](#caption--scope-for-table)
- [`accesskey`](#accesskey)

<!-- /MarkdownTOC -->

Main refs:

- [Dive Into Accessibility](https://web.archive.org/web/20110927131211/http://diveintoaccessibility.org/) ([中文翻译](http://dia.z6i.org/)), refreshed according to HTML5.
- [HTML: A good basis for accessibility - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)([中文版本](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility/HTML:%E4%B8%BA%E5%8F%AF%E8%AE%BF%E9%97%AE%E6%80%A7%E6%8F%90%E4%BE%9B%E4%B8%80%E4%B8%AA%E8%89%AF%E5%A5%BD%E7%9A%84%E5%9F%BA%E7%A1%80))

## `lang`

You should specify the language of your webpage, as well as every element that is using other languages.

For example:

```html
<html lang="en">
    ...
    <blockquote lang="de">
    ...
    </blockquote>
```

## `alt` & `title` for `img`

Every `<img>` should have `alt`.

```html
<img src="smiley.jpeg" alt="a smiley face">
```

`title` is for extra information, and can be seen when users hover their mouse over the image.

```html
<img src="smiley.jpeg" alt="a smiley face" title="Smiley face of John Smith">
```

## `a`

### `target` vs `rel`

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


## `caption` & `scope` for `table`

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

So you should have at least:

```html
<a href="index.html" 
   accesskey="1">Home</a>
<a href="accessibility_statement.html" 
   accesskey="0">Accessibility Statement</a>

```


