# CSS: `form` & `input`

<!-- MarkdownTOC -->

- [Weird Use Cases of `input`](#weird-use-cases-of-input)
    - [Accessible Pure CSS Accordion Menu](#accessible-pure-css-accordion-menu)

<!-- /MarkdownTOC -->


## Weird Use Cases of `input`

### Accessible Pure CSS Accordion Menu

This is a `checkbox` menu (use tab key to navigate):

<style>
.accordion { padding-left:0 !important; }

.accordion__item { overflow: hidden; }

.accordion__label {
    display: flex;
    justify-content: space-between;
    padding-right: 1em;
    cursor: pointer;
    user-select: none;
    background-color: lightgray;
    border: 1px solid white;
}

.accordion__label::after { content: "\276F"; }
.accordion__input:checked + .accordion__label::after { transform: rotate(90deg); }

.accordion__input:focus { outline: none; }
.accordion__input:focus + .accordion__label {
    outline: 3px solid orange; /* need this even when there is global focus setting*/
    outline-offset: -3px;
}

.accordion__input {
    position: absolute; /* hide behind label */ 
    outline: none;
    width: 1px;
    height: 1px;
    margin-left: 2px;
    margin-top: 2px;
    z-index: -100;
}

.accordion__input + .accordion__label:hover,
.accordion__input:checked + .accordion__label {
    background-color: gray;
    color: white;
}

.accordion__input:checked ~ .accordion__content {
    /* + does not work here for reasons unknown */
    height: auto;
    max-height: 90vh;
}

.accordion__item ul {
    /* normalise */
    list-style-type: disc;
    max-height: 0;
    padding-right: 1em;
}
</style>

<ul class="accordion">
    <li class="accordion__item">
    <input class="accordion__input" id="to-do" type="checkbox" name="to-do-list" />
    <label class="accordion__label" for="to-do">To-do list</label>
    <ul class="accordion__content">
        <li>Going to-do</li>
        <li><strike>Finished to-do</strike></li>
        <li><strike>Finished to-do</strike></li>
    </ul>
    </li>
    <li class="accordion__item">
    <input class="accordion__input" id="to-do-2" type="checkbox" name="to-do-list" />
    <label class="accordion__label" for="to-do-2">To-do list 2</label>
    <ul class="accordion__content">
        <li>Going to-do</li>
        <li>Going to-do</li>
        <li><strike>Finished to-do</strike></li>
    </ul>
    </li>
</ul>

This is a `radio` menu (use arrow keys to navigate):

<ul class="accordion">
    <li class="accordion__item">
    <input class="accordion__input" id="to-do-3" type="radio" name="to-do-3" checked />
    <label class="accordion__label" for="to-do-3">To-do list</label>
    <ul class="accordion__content">
        <li>Going to-do</li>
        <li><strike>Finished to-do</strike></li>
        <li><strike>Finished to-do</strike></li>
    </ul>
    </li>
    <li class="accordion__item">
    <input class="accordion__input" id="to-do-4" type="radio" name="to-do-3" />
    <label class="accordion__label" for="to-do-4">To-do list 2</label>
    <ul class="accordion__content">
        <li>Going to-do</li>
        <li>Going to-do</li>
        <li><strike>Finished to-do</strike></li>
    </ul>
    </li>
</ul>


```html
<ul class="accordion">
    <li class="accordion__item">
    <input class="accordion__input" id="to-do" type="checkbox" name="to-do-list" />
    <label class="accordion__label" for="to-do">To-do list</label>
    <ul class="accordion__content">
        <li>Going to-do</li>
        <li><strike>Finished to-do</strike></li>
        <li><strike>Finished to-do</strike></li>
    </ul>
    </li>
    <li class="accordion__item">
    <input class="accordion__input" id="to-do-2" type="checkbox" name="to-do-list" />
    <label class="accordion__label" for="to-do-2">To-do list 2</label>
    <ul class="accordion__content">
        <li>Going to-do</li>
        <li>Going to-do</li>
        <li><strike>Finished to-do</strike></li>
    </ul>
    </li>
</ul>
```

\-

```css
.accordion { padding-left:0 !important; }

.accordion__item { overflow: hidden; }

.accordion__label {
    display: flex;
    justify-content: space-between;
    padding-right: 1em;
    cursor: pointer;
    user-select: none;
    background-color: lightgray;
    border: 1px solid white;
}

.accordion__label::after { content: "\276F"; }

.accordion__input:focus { outline: none; }
.accordion__input:focus + .accordion__label {
    outline: 3px solid orange;
    outline-offset: -3px;
}

.accordion__input {
    position: absolute; /* hide behind label */ 
    outline: none;
    width: 1px;
    height: 1px;
    margin-left: 2px;
    margin-top: 2px;
    z-index: -100;
}

.accordion__input + .accordion__label:hover,
.accordion__input:checked + .accordion__label {
    background-color: gray;
    color: white;
}

.accordion__input:checked + .accordion__label::after { transform: rotate(90deg); }

.accordion__input:checked ~ .accordion__content {
    /* + does not work here for reasons unknown */
    height: auto;
    max-height: 90vh;
}

.accordion__item ul {
    /* normalise */
    list-style-type: disc;
    max-height: 0;
    padding-right: 1em;
}
```

