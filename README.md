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

---

* Target attribute that ends with some value
```css
a[href$='.pdf'] {
  background-image: url(`pdficon.gif`);
}
```

For example, you can also indicate on print that there is a PDF behind that text
```css

@media print {
  a[href$='.pdf']:after {
    content: ' (PDF)';
  }
}
```
---

Select any element with an attribute with a substring 'val'*/
```css

a[href*='val']
```
---

* Make attributes case-sensitive / insensitive

default html attributes are case-insensitive
But attributes that were created by you are sensitive
```css
div[id="FOO" i],
/* type is html's own attribute, insensitive, but we forced it to be sensitive*/
input[type="tExT" s] {
  background-color: lightgreen;
}
div[id="FOO" s],
input[type="TEXT" i] {
  background-color: blue;
}
```

## UI Selectors

* :enabled

* :disabled

* :read-only

* :read-write

* :placeholder-shown

* :default

* :checked

* :indeterminate

* :valid

* :invalid

* :in-range

* :out-of-range

* :required

* :optional

* :blank

* :user-invalid
---

## Structural Selectors
They target elements in relation to other elements in the document
* :root

* :empty

* :blank

* :nth-child()

* :nth-last-child()

* :first-child*

* :last-child

* :only-child

* :nth-of-type()

* :nth-last-of-type()

* :first-of-type

* :last-of-type

* :only-of-type