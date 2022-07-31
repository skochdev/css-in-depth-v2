# CSS Attribute selectors

* Select a particular element that has attribute of `lang="en` or `lang=en-...`

```html
<p lang="en">p2</p>
<p lang="en-uk">p3</p>
```
```css
p[lang|='en'] {
  background-color: yellow;
}
```
---

* Target elements whose attribute `href` starts with `mailto`
```css
a[href^='mailto'] {
  background-color: pink;
}

```

* Make links addresses printable

**v1** 

```css
@media print {
    a[href^='mailto']::after {
    content: ' (' attr(href) ')';
    }
}
```
**v2** without media rules works just fine
```css
a[href^='http']:after {
  content: ' (' attr(href) ')';
}
```
