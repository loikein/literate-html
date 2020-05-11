# HTML: `body` tag

<!-- MarkdownTOC -->

- [`main`](#main)
- [`header` and `footer`](#header-and-footer)
- [Sectioning Elements](#sectioning-elements)
	- [`nav`](#nav)
	- [`article` vs `section` vs `div`](#article-vs-section-vs-div)
	- [`aside`](#aside)
- [Elemental Elements](#elemental-elements)
	- [`em` vs `strong` vs `i`](#em-vs-strong-vs-i)
	- [`s` vs `del`](#s-vs-del)
	- [`small`](#small)
	- [`code` and `pre`](#code-and-pre)
	- [`time`](#time)

<!-- /MarkdownTOC -->

Main refs:

- [4.3 Sections - HTML Standard](https://html.spec.whatwg.org/multipage/sections.html)
- [4.4 Grouping content - HTML Standard](https://html.spec.whatwg.org/multipage/grouping-content.html)
- [4.5 Text-level semantics - HTML Standard](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-small-element)

There can only be 1 `<body>` tag in each document.

## `main`

- A `<main>` tag is a section.
- There can only be 1 *visible* `<main>` tag in each document.

## `header` and `footer`

- A `<header>` or a `<footer>` tag is a group with no specific sementic implementations.
- Each section can contain 1 direct child `<header>` and 1 direct child `<footer>`.
- For accessibility reasons, it is recommended that [each document only contains 1 `<header>` and 1 `<footer>`](https://dequeuniversity.com/rules/axe/3.5/landmark-unique?application=AxeFirefox).

## [Sectioning Elements](https://html.spec.whatwg.org/multipage/dom.html#sectioning-content)

According to [4.3.11 Headings and sections - HTML Standard](https://html.spec.whatwg.org/multipage/sections.html#headings-and-sections),

- Each sectioning element can have their own headings and outlines.
- The first heading in a sectioning element is its heading.
- Implicitly, headings of equal or higher rank start a new section, headings of lower rank start a subsection.
- Explicitly, creating a child section starts a subsection (so you can [use `<h1>` in both the supersection and the subsection](https://html.spec.whatwg.org/multipage/sections.html#the-h1,-h2,-h3,-h4,-h5,-and-h6-elements)).

### `nav`

- A `<nav>` tag contains links to other pages or to parts within the page.
- A `<nav>` tag can be inside or outside a `<header>` tag, but [probably don't put `<header>` tags inside a `<nav>` tag](https://www.sitepoint.com/community/t/h1-inside-nav/35373/6) unless you want to explicitly name the `<nav>`.
- For accessibility reasons, it is recommended that [each document only contains 1 `<nav>`](https://dequeuniversity.com/rules/axe/3.5/landmark-unique?application=AxeFirefox).
- Personally, I like to put the top-level `<nav>` tag inside the top-level `<header>` tag.

```html
<body>
	<header>
		<a href="./home">Logo</a>
		<h1>A good blog</h1>
		<nav><ul>
			<li>Posts</li>
			<li>Archive</li>
			<li>About</li>
		</ul></nav>
	</header>
	<main>…</main>
	<footer>Copyleft 2020</footer>
</body>
```

### `article` vs `section` vs `div`

According to [4.3.3 The section element - HTML Standard](https://html.spec.whatwg.org/multipage/sections.html#the-section-element),

- You should use `<article>` against `<section>` when writing a complete & self-contained part of the document.
- You should use `<div>` against `<section>` when grouping something only for styling purpose.
- Else, you should use `<section>` if you want a group of elements to appear in [page outline](https://html.spec.whatwg.org/multipage/sections.html#outlines) as one (chapter, appendix, etc).

```html
<article>
	<header>
		<hgroup>
			<h1>A good title</h1>
			<h2><time datetime=2020-05-03>2020 May 03</time></h2>
		</hgroup>
		<nav><ul>
			<li>Older post</li>
			<li>Menu</li>
			<li>Newer post</li>
		</ul></nav>
	</header>
	<p>…</p>
	<p>…</p>
	<footer>Tags: atag, anothertag</footer>
</article>

<article>Comments</article>
```

### `aside`

[You should not use](https://html.spec.whatwg.org/multipage/sections.html#the-aside-element) `<aside>` tags to contain sidenotes. They should be essential parts of the document.

## Elemental Elements

Grouping elements + text-level elements

### `em` vs `strong` vs `i`

- `<em>` tags affect the meaning of a sentense by giving emphasis on different words.
- To simply make words stand out (tones, voices, etc), you should use `<i>`.
- To convey importance, you should use `<strong>`.

### `s` vs `del`

- `<s>` represents old contents that are no longer relevant.
- To indicate document edits, you should use `<del>`.

### `small`

[There is no clear standard](https://stackoverflow.com/questions/57272564/what-html-element-for-semantic-sidenotes), but you could [use `<small>` tag to contain sidenotes](https://www.kooslooijesteijn.net/blog/semantic-sidenotes). (I personally prefer sidenote over footnote.)

### `code` and `pre`

Use `<code>` for [inline code](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-code-element), and `<pre><code>` for [code blocks](https://html.spec.whatwg.org/multipage/grouping-content.html#the-pre-element).

### [`time`](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-time-element)


