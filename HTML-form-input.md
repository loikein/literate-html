# HTML: `form` & `input`

<!-- MarkdownTOC -->

- [`input` Tag](#input-tag)
	- [Text](#text)
	- [`button` Tag](#button-tag)
	- [Checkbox](#checkbox)
	- [Radio & `fieldset` \(`id`, `name`, `value` & `label`\)](#radio--fieldset-id-name-value--label)
- [`label` Tag](#label-tag)
	- [Linking `label` & `input`](#linking-label--input)
- [`form` Tag](#form-tag)
- [Weird Usages of `input`](#weird-usages-of-input)
	- [Click to Show Menu](#click-to-show-menu)

<!-- /MarkdownTOC -->

## `input` Tag

Basic attributes:

- `type`
- `name` & `value`
- `form` & `required`
- `autofocus`
- `disabled`

Basic types:

- `text` (default)
- `button` = `<button>`
- `checkbox` & `radio`
- `number` & `tel`
- `date` & `time`
- `email` & `password`
- `color`
- `file`
- `reset`, `submit` & `image`

### Text

This is a `text` that is required (you must fill in), with placeholder:

<label for="name">Input: </label>
<input type="text" id="name" name="name"
	required minlength="4" maxlength="8"
	placeholder="nooo">

```html
<label for="name">Input: </label>
<input type="text" id="name" name="name"
	required minlength="4" maxlength="8"
	placeholder="nooo">
```

### `button` Tag

This is a `<button>`: <button type="button">Click me</button>

<small class="side-note">You do not need to write `type="button"` [unless the button is in a `<form>`](https://stackoverflow.com/questions/41904199/whats-the-point-of-button-type-button).</small>

```html
<button type="button">Click me</button>
```

### Checkbox

This is a `checkbox` with `<label>`: <input type="checkbox" name="check" id="check"><label for="check">Yes or no?</label>

```html
<input type="checkbox" name="check" id="checkbox">
<label for="checkbox">Yes or no?</label>
```

### Radio & `fieldset` (`id`, `name`, `value` & `label`)

This is a `<fieldset>` with `<legend>`: 

<fieldset>
<legend>Which size?</legend>
<input type="radio" id="cup-tall" name="cup" value="tall">
<label for="cup-tall">Tall</label>

<input type="radio" id="cup-grande" name="cup" value="grande" checked>
<label for="cup-grande">Grande</label>

<input type="radio" id="cup-venti" name="cup" value="venti">
<label for="cup-venti">Venti</label>
</fieldset>

\-

```html
<fieldset>
<legend>Which size?</legend>
<input type="radio" id="cup-tall" name="cup" value="tall">
<label for="cup-tall">Tall</label>

<input type="radio" id="cup-grande" name="cup" value="grande" checked>
<label for="cup-grande">Grande</label>

<input type="radio" id="cup-venti" name="cup" value="venti">
<label for="cup-venti">Venti</label>
</fieldset>
```

## `label` Tag

- When a `<label>` is paird with an `<input>`, clicking the `<label>` also clicks the `<input>`.
	- Use `user-select: none;` to prevent accidental selection.

### Linking `label` & `input`

- Use explicit link if you want the `<input>` to appear before the `<label>`.
- These two methods have some additional differences when using the `<input>` for some weird purposes.

Explicit link: <label for="link-l-i">Yes or no?</label><input type="checkbox" name="check" id="link-l-i">

```html
<label for="link-l-i">Yes or no?</label>
<input type="checkbox" name="check" id="link-l-i">
```

Implicit link: <label>Yes or no?<input type="checkbox" name="check"></label>

```html
<label>Yes or no?
	<input type="checkbox" name="check">
</label>
```

## `form` Tag


## Weird Usages of `input`

### Click to Show Menu

This is a `checkbox` menu:

<style>
.accordion-box {
	padding-left:0 !important;
}
.accordion {
	width: 100%;
	overflow: hidden;
	user-select: none;
}
.accordion-label {
	display: flex;
	justify-content: space-between;
	padding-right: 1em;
	cursor: pointer;
}
.accordion-label:hover,
.accordion-label:focus {
	background-color: lightgray;
}
.accordion-label::after {
	content: "\276F";
}
.accordion-content {
	max-height: 0;
	padding-right: 1em;
}
.accordion-box input {
	display: none;
}
.accordion-box input:checked ~ .accordion-label::after {
	-webkit-transform: rotate(90deg);
	transform: rotate(90deg);
}
.accordion-box input:checked ~ .accordion-content {
	max-height: 90vh;
}
</style>

<ul class="accordion-box">
	<li class="accordion">
	<input id="to-do" type="checkbox" name="to-do-list" />
	<label class="accordion-label" for="to-do">To-do list</label>
	<ul class="accordion-content">
		<li>Going to-do</li>
		<li><strike>Finished to-do</strike></li>
		<li><strike>Finished to-do</strike></li>
	</ul>
	</li>
	<li class="accordion">
	<input id="to-do-2" type="checkbox" name="to-do-list" />
	<label class="accordion-label" for="to-do-2">To-do list 2</label>
	<ul class="accordion-content">
		<li>Going to-do</li>
		<li>Going to-do</li>
		<li><strike>Finished to-do</strike></li>
	</ul>
	</li>
</ul>

This is a `radio` menu with same `name`:

<ul class="accordion-box">
	<li class="accordion">
	<input id="to-do-3" type="radio" name="to-do-3" checked />
	<label class="accordion-label" for="to-do-3">To-do list</label>
	<ul class="accordion-content">
		<li>Going to-do</li>
		<li><strike>Finished to-do</strike></li>
		<li><strike>Finished to-do</strike></li>
	</ul>
	</li>
	<li class="accordion">
	<input id="to-do-4" type="radio" name="to-do-3" />
	<label class="accordion-label" for="to-do-4">To-do list 2</label>
	<ul class="accordion-content">
		<li>Going to-do</li>
		<li>Going to-do</li>
		<li><strike>Finished to-do</strike></li>
	</ul>
	</li>
</ul>


```html
<ul class="accordion-box">
	<li class="accordion">
	<input id="to-do" type="checkbox" name="to-do-list" />
	<label class="accordion-label" for="to-do">To-do list</label>
	<ul class="accordion-content">
		<li>Going to-do</li>
		<li><strike>Finished to-do</strike></li>
		<li><strike>Finished to-do</strike></li>
	</ul>
	</li>
	<li class="accordion">
	<input id="to-do-2" type="checkbox" name="to-do-list" />
	<label class="accordion-label" for="to-do-2">To-do list 2</label>
	<ul class="accordion-content">
		<li>Going to-do</li>
		<li>Going to-do</li>
		<li><strike>Finished to-do</strike></li>
	</ul>
	</li>
</ul>
```

\-

```css
/* Accordion styles */
.accordion-box {
	/* ignore the ul style */
	padding-left: 0 !important;
}
.accordion {
	width: 100%;
	overflow: hidden;
	user-select: none;
}
.accordion-label {
	/* right-align the arrow */
	display: flex;
	justify-content: space-between;

	/* add some padding to avoid clip */
	padding-right: 1em;
	cursor: pointer;
}
.accordion-label:hover,
.accordion-label:focus {
	background-color: lightgray;
}
.accordion-label::after {
	/* the arrow */
	content: "\276F";
}
.accordion-content {
	max-height: 0;
	padding-right: 1em;
}
.accordion-box input {
	display: none;
}
.accordion-box input:checked ~ .accordion-label::after {
	-webkit-transform: rotate(90deg);
	transform: rotate(90deg);
}
.accordion-box input:checked ~ .accordion-content {
	/* the menu will not show otherwise */
	max-height: 90vh;
}
```

