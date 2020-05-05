# `form` & `input`

<!-- MarkdownTOC -->

- [`label` Tag](#label-tag)
    - [Linking `` & ``](#linking--)
- [`input` Tag](#input-tag)
    - [Text](#text)
    - [Button](#button)
    - [Checkbox](#checkbox)
    - [Radio](#radio)
- [`label` Tag](#label-tag-1)
- [`form` Tag](#form-tag)

<!-- /MarkdownTOC -->

## `label` Tag

- When a `<label>` is paird with an `<input>`, clicking the `<label>` also clicks the `<input>`.
    - Use `user-select: none;` to prevent accidental selection.

### Linking `<label>` & `<input>`

When using the `<input>` for some weird purposes, these two methods have some differences, but for now they are the same.

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


## `input` Tag

Basic attributes:

- `type`
- `name` & `value`
- `form` & `required`
- `autofocus`
- `disabled`

Basic types:

- `text` (default)
- `button`
- `checkbox` & `radio`
- `number` & `tel`
- `date` & `time`
- `email` & `password`
- `color`
- `file`
- `reset`, `submit` & `image`

### Text

This is a text `input` tag:

<label for="name">Input: </label>
<input type="text" id="name" name="name" minlength="4" maxlength="8">

```html
<label for="name">Input: </label>
<input type="text" id="name" name="name" required minlength="4" maxlength="8">
```

### Button


### Checkbox


### Radio


## `label` Tag

## `form` Tag
