## Tables
*Colgroup* for styling all column
```html
  <colgroup>
    <col>
    <col style="background-color: yellow">
  </colgroup>
```
<thead> <tbody> <tfoot>
  
## Rem vs Px
Use rem for fontsize px for everything else
  
## Neutral Font Style
```css
  font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
```
## Useful CSS Properties
- Overflow.
- Opacity (zero for transparent).
  
## Sibling Selectors
- Selector *+* .- immediately follows a specific tag 
  p + .intro selects every element with class="intro" that directly follows a p
  div + a selects every a element that directly follows a div
  
```html
<main>
  <h1>Hello</h1>
  <h1>Wolrd</h1> /*Only this would be affected*/
</main>	
```
```css
h1 + h2 {
  color: orange;
}
```
- Selector *>* .- select child elements
```html
 <main class="parent">
  <div class="child group1">
    <div class="grand-child group1"></div>
  </div>
  <div class="child group2">
    <div class="grand-child group2"></div>
  </div>
  <div class="child group3">
    <div class="grand-child group3"></div>
  </div>
</main> 
```
```css
  /* This rule will only select divs with a class of child */
main > div {
}

/* This rule will only select divs with a class of grand-child */
main > div > div {
}
```
- Selector *~* .- Select every elements that has a sibling
  A ~ B selects all B that follow a A
  
```css
/* This rule will select all of .group1's siblings - in this case the 2nd and 3rd .child divs */
  .group1 ~ div {
  }
}```  
  
## Pseudo Classes

specificity (0, 0, 1, 0)

- **:focus**
- **:hover**
- **:active**
- **:visited**
- **:first-child and last-child**
- **:empty elements that have no children at all**
- **:only-child elements with no sibling**
- **:nth-child**

```css
.myList:nth-child(5) {
  /* Selects the 5th element with class myList */
}
.myList:nth-child(3n) {
  /* Selects every 3rd element with class myList */
}
.myList:nth-child(3n + 3) {
  /* Selects every 3rd element with class myList, beginning with the 3rd */
}
.myList:nth-child(even) {
  /* Selects every even element with class myList */
}
```

## Pseudo Elements

specificity (0, 0, 0, 1)

- **marker** allows you to customize the styling of your <li> elements’ bullets or numbers.
- **::first-letter** and **::first-line**
- **before** and **after**

## Attribute selector

- [attribute]
- selector[attribute]
- [attribute="value"]

```css
  [src] {
    /* This will target any element that has a src attribute. */
  }

  img[src] {
    /* This will only target img elements that have a src attribute. */
  }

  img[src="puppy.jpg"] {
    /* This will target img elements with a src attribute that is exactly "puppy.jpg" */
  }

[class^='aus'] {
  /* Classes are attributes too!
    This will target any class that begins with 'aus':
    class='austria'
    class='australia'
  */
}

[src$='.jpg'] {
  /* This will target any src attribute that ends in '.jpg':
  src='puppy.jpg'
  src='kitten.jpg'
  */
}

[for*='ill'] {
  /* This will target any for attribute that has 'ill' anywhere inside it:
  for="bill"
  for="jill"
  for="silly"
  for="ill"
  */
}

orange.small
```

## Useful thingys

### Negation Pseudo-class

**not(X)** .- You can use this to select all elements that do not match selector "X".

E.g. :not(#fancy) selects all elements that do not have id="fancy".

### Only of type selector

**:only-of-type** .- Selects the only element of its type within another element.

### Nth-of-type Selector with Formula

**:nth-of-type(An+B)** .- The nth-of-type formula selects every nth element, starting the count at a specific instance of that element.

E.g. `css span:nth-of-type(6n+2)` selects every 6th instance of a span, starting from (and including) the second instance.

[Useful info](https://flukeout.github.io/)  
            
## Useful links
[CSS Cheat Sheet](https://websitesetup.org/wp-content/uploads/2019/11/wsu-css-cheat-sheet-gdocs.pdf)
[Emmet Cheat Sheet](https://docs.emmet.io/cheat-sheet/)
