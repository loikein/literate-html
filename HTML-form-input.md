# HTML: `form` & `input`

<!-- MarkdownTOC -->

- [`input` Tag](#input-tag)
	- [Text](#text)
	- [`button` Tag](#button-tag)
	- [Checkbox](#checkbox)
	- [Radio & `fieldset` \(`id`, `name`, `value` & `label`\)](#radio--fieldset-id-name-value--label)
- [`label`](#label)
	- [Linking `label` & `input`](#linking-label--input)
- [`form` Tag](#form-tag)

<!-- /MarkdownTOC -->

Main refs:

- [Form controls | U.S. Web Design System (USWDS)](https://designsystem.digital.gov/components/form-controls/)

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

## `label`

- When a `<label>` is paird with an `<input>`, clicking the `<label>` also clicks the `<input>`.
	- Use `user-select: none;` to prevent accidental selection.
	- Use `cursor: pointer;` to indicate that the label is clickable.

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


