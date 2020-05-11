# CSS: Accessibility

<!-- MarkdownTOC -->

- [`:focus`](#focus)

<!-- /MarkdownTOC -->


Main refs:

- [Dive Into Accessibility](https://web.archive.org/web/20110927131211/http://diveintoaccessibility.org/) ([中文翻译](http://dia.z6i.org/)), refreshed according to CSS3.
- [CSS and JavaScript accessibility best practices - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript) ([中文翻译](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility/CSS%E5%92%8CJavaScript))
- [WebAIM: Accessible CSS](https://webaim.org/techniques/css/)
- [Visual design | Accessibility for Teams](https://accessibility.digital.gov/visual-design/getting-started/)

## `:focus`

Refs: 

- [Styling form controls with CSS, revisited | 456 Berea Street](https://www.456bereastreet.com/archive/200701/styling_form_controls_with_css_revisited/)
- [C15: Using CSS to change the presentation of a user interface component when it receives focus](https://www.w3.org/WAI/WCAG21/Techniques/css/C15)

active & visited?

- When necessary, consider [using JavaScript](https://www.w3.org/WAI/WCAG21/Techniques/client-side-script/SCR31.html).

```css
/* source: https://inclusivedesignprinciples.org */
:focus:not([tabindex="-1"]) {
  outline: 0.125rem solid #fcb316;
  outline-offset: 0.125rem;
  border: 0;
}
```
