# CSS: `form` & `input`

<!-- MarkdownTOC -->

- [Weird Use Cases of `input`](#weird-use-cases-of-input)
    - [Accessible Accordion Menu](#accessible-accordion-menu)

<!-- /MarkdownTOC -->


## Weird Use Cases of `input`

### Accessible Accordion Menu

This is a `checkbox` menu (use tab key to navigate):

<style>
.accordion-box { padding-left:0 !important; }

.accordion {
    width: 100%;
    overflow: hidden;
}
.accordion-label {
    display: flex;
    justify-content: space-between;
    padding-right: 1em;
    cursor: pointer;
    user-select: none;
    background-color: lightgray;
    border: 1px solid white;
}

.accordion-box input:focus + .accordion-label {
    outline: 3px solid orange;
    outline-offset: -3px;
}

.accordion-label::after { content: "\276F"; }

.accordion-content {
    max-height: 0;
    padding-right: 1em;
}
.accordion input {
    position: absolute; /* hide behind label */ 
    outline: none;
    width: 1px;
    height: 1px;
    margin-left: 2px;
    margin-top: 2px;
    z-index: -100;
}

.accordion input + .accordion-label:hover,
.accordion input:checked + .accordion-label {
    background-color: gray;
    color: white;
}

.accordion input:checked + .accordion-label::after { transform: rotate(90deg); }

.accordion-box input:checked ~ .accordion-content {
    /* + does not work here for reasons unknown */
    height: auto;
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

This is a `radio` menu (use arrow keys to navigate):

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
.accordion-box { padding-left:0 !important; }

.accordion {
    width: 100%;
    overflow: hidden;
}
.accordion-label {
    display: flex;
    justify-content: space-between;
    padding-right: 1em;
    cursor: pointer;
    user-select: none;
    background-color: lightgray;
    border: 1px solid white;
}

.accordion-box input:focus + .accordion-label {
    outline: 3px solid orange;
    outline-offset: -3px;
}

.accordion-label::after { content: "\276F"; }

.accordion-content {
    max-height: 0;
    padding-right: 1em;
}
.accordion input {
    position: absolute; /* hide behind label */ 
    outline: none;
    width: 1px;
    height: 1px;
    margin-left: 2px;
    margin-top: 2px;
    z-index: -100;
}

.accordion input + .accordion-label:hover,
.accordion input:checked + .accordion-label {
    background-color: gray;
    color: white;
}

.accordion input:checked + .accordion-label::after { transform: rotate(90deg); }

.accordion-box input:checked ~ .accordion-content {
    /* + does not work here for reasons unknown */
    height: auto;
    max-height: 90vh;
}
```

