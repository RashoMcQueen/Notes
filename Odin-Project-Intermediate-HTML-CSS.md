- [Tables](#tables)
  - [Rem vs Px](#rem-vs-px)
  - [Neutral Font Style](#neutral-font-style)
  - [Useful CSS Properties](#useful-css-properties)
- [Sibling Selectors](#sibling-selectors)
  - [Pseudo Classes](#pseudo-classes)
  - [Pseudo Elements](#pseudo-elements)
  - [Attribute selector](#attribute-selector)
  - [Useful thingys](#useful-thingys)
    - [Negation Pseudo-class](#negation-pseudo-class)
    - [Only of type selector](#only-of-type-selector)
    - [Nth-of-type Selector with Formula](#nth-of-type-selector-with-formula)
  - [Useful links](#useful-links)
- [Forms](#forms)
  - [The inpunt Element](#the-inpunt-element)
  - [Label](#label)
  - [Type Inpunts](#type-inpunts)
    - [Text Area](#text-area)
  - [Selection Elements](#selection-elements)
    - [Select Dropdown](#select-dropdown)
    - [Radio Buttons](#radio-buttons)
    - [Checkboxes](#checkboxes)
  - [Buttons](#buttons)
    - [Submit Buttons](#submit-buttons)
    - [Reset Button](#reset-button)
    - [Generic Button](#generic-button)
  - [Organizing Form Elements](#organizing-form-elements)
    - [Fieldset Element](#fieldset-element)
    - [Legend](#legend)
  - [Styling forms](#styling-forms)
- [Form Example](#form-example)
- [Form Validations](#form-validations)
  - [Required](#required)
  - [Text Length](#text-length)
    - [Minimun length validation](#minimun-length-validation)
    - [Maximum Length](#maximum-length)
  - [Number Range](#number-range)
  - [Pattern Validation](#pattern-validation)
  - [Styling Validations :invalid :valid](#styling-validations-invalid-valid)
  - [Useful links](#useful-links-1)

# Tables

_Colgroup_ for styling all column

```html
<colgroup>
  <col />
  <col style="background-color: yellow" />
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
  
# Sibling Selectors
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

/_ This rule will only select divs with a class of grand-child _/
main > div > div {
}

````
- Selector *~* .- Select every elements that has a sibling
  A ~ B selects all B that follow a A

```css
/* This rule will select all of .group1's siblings - in this case the 2nd and 3rd .child divs */
  .group1 ~ div {
  }
````

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

# Forms

## The inpunt Element

```html
<form action="example.com/path" method="post">
  <label for="first_name">First Name:</label>
  <input type="text" placeholder="Bob..." name="first_name" />
</form>
```

## Label

Labels are clickable too

## Type Inpunts

- Email inputs `html type="email"`
- Password inputs `html type="password"`
- Number inputs `html type="number"`
- Date inputs `html type="date"`

### Text Area

While technically not an input element, the text area element provides an input box that can accept text that spans multiple lines like user comments and reviews. It can also be resized by clicking and dragging the bottom right corner to make it bigger or smaller.

```html
<textarea rows="20" cols="60">Some initial bs</textarea>
```

## Selection Elements

### Select Dropdown

We can set one of the options to be the default selected element by giving one of the options the selected attribute

```html
<select name="Car">
  <option value="mercedes">Mercedes</option>
  <option value="tesla">Tesla</option>
  <option value="volvo" selected>Volvo</option>
  <option value="bmw">BMW</option>
  <option value="mini">Mini</option>
  <option value="ford">Ford</option>
</select>

/* split in groups*/
<select name="fashion">
  <optgroup label="Clothing">
    <option value="t_shirt">T-Shirts</option>
    <option value="sweater">Sweaters</option>
    <option value="coats">Coats</option>
  </optgroup>
  <optgroup label="Foot Wear">
    <option value="sneakers">Sneakers</option>
    <option value="boots">Boots</option>
    <option value="sandals">Sandals</option>
  </optgroup>
</select>
```

### Radio Buttons

When we select one of the radio buttons and then select another, it will deselect the first one. Radio buttons know to do this because they have the same name attribute.
We can set the default selected radio button by adding the checked attribute to it.

**Every radio button group you create should:**

- Be wrapped in a \<fieldset>, which is labeled with a \<legend>.
- Associate a \<label> element with each radio button.
- Use the same name attribute for each radio button in the group.
- Use different value attributes for each radio button.

```html
<h1>Ticket Type</h1>
<div>
  <input type="radio" id="child" name="ticket_type" value="child" />
  <label for="child">Child</label>
</div>

<div>
  <input type="radio" id="adult" name="ticket_type" value="adult" />
  <label for="adult">Adult</label>
</div>

<div>
  <input type="radio" id="senior" name="ticket_type" value="senior" />
  <label for="senior">Senior</label>
</div>
```

### Checkboxes

```html
<h1>Pizza Toppings</h1>

<div>
  <input type="checkbox" id="sausage" name="topping" value="sausage" />
  <label for="sausage">Sausage</label>
</div>

<div>
  <input type="checkbox" id="onions" name="topping" value="onions" />
  <label for="onions">Onions</label>
</div>

<div>
  <input type="checkbox" id="pepperoni" name="topping" value="pepperoni" />
  <label for="pepperoni">Pepperoni</label>
</div>

<div>
  <input type="checkbox" id="mushrooms" name="topping" value="mushrooms" />
  <label for="mushrooms">Mushrooms</label>
</div>
```

## Buttons

### Submit Buttons

```html
<button type="submit">Submit</button>
```

### Reset Button

```html
<button type="reset">Reset</button>
```

### Generic Button

```html
<button type="button">Reset</button>
```

## Organizing Form Elements

### Fieldset Element

```html
<fieldset>
  <label for="first_name">First Name</label>
  <input type="text" id="first_name" name="first_name" />
  <label for="last_name">Last Name</label>
  <input type="text" id="last_name" name="last_name" />
</fieldset>
```

### Legend

The legend element is used to give field sets a heading or caption so the user can see what a grouping of inputs is for.
To create a legend, we use the <legend> element with the text we want to display within its opening and closing tags. A legend should always come right after an opening fieldset tag.

## Styling forms

[Custom checkbox style](https://moderncss.dev/pure-css-custom-checkbox-style/)
[New CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/accent-color)
[Good info about forms](https://www.internetingishard.com/html-and-css/forms/)
[In depth info about forms](https://web.dev/learn/forms/)

# Form Example

```html
<p>This is my page</p>

<form action="">
  <h1>Payment form</h1>
  <p>
    Required fields are followed by
    <strong><span aria-label="required">*</span></strong
    >.
  </p>
  <section>
    <h2>Contact Information</h2>
    <fieldset>
      <legend>Title</legend>
      <ul>
        <li>
          <label for="title_1"
            ><input
              type="radio"
              name="title"
              id="title_1"
              value="K"
            />King</label
          >
        </li>
        <li>
          <label for="title_2"
            ><input
              type="radio"
              name="title"
              id="title_2"
              value="Q"
            />Queen</label
          >
        </li>
        <li>
          <label for="title_3"
            ><input
              type="radio"
              name="title"
              id="title_3"
              value="J"
            />Joker</label
          >
        </li>
      </ul>
    </fieldset>

    <p>
      <label for="name"
        ><span>Name: </span
        ><strong><span aria-label="required">*</span></strong>
      </label>
      <input type="text" name="username" id="name" />
    </p>

    <p>
      <label for="mail">
        <span>Email: </span>
        <strong><span aria-label="required">*</span></strong>
      </label>
      <input type="email" name="usermail" id="mail" />
    </p>

    <p>
      <label for="pwd">
        <span>Password: </span>
        <strong><span aria-label="required">*</span></strong>
      </label>
      <input type="password" name="password" id="pwd" />
    </p>
  </section>

  <section>
    <h2>Payment Information</h2>
    <p>
      <label for="card">
        <span>Card type: </span>
      </label>
      <select name="usercard" id="card">
        <option value="visa">Visa</option>
        <option value="mc">Mastercard</option>
        <option value="amex">American Express</option>
      </select>
    </p>

    <p>
      <label for="number">
        <span>Card number: </span>
        <strong><span aria-label="required">*</span></strong>
      </label>
      <input type="tel" name="cardnumber" id="number" />
    </p>

    <p>
      <label for="expiration">
        <span>Expiration date: </span>
        <strong><span aria-label="required">*</span></strong>
      </label>
      <input
        type="text"
        name=""
        id="expiration"
        required="true"
        placeholder="MM/YY"
        pattern="^(0[1-9]|1[0-2])\/([0-9]{2})$"
      />
    </p>
  </section>

  <section>
    <p>
      <button type="submit">Validate the payment</button>
    </p>
  </section>
</form>
```

# Form Validations

## Required

Add **required** attribute to it

```html
<input type="email" id="user_email" name="user_email" required />
```

## Text Length

### Minimun length validation

```html
<textarea placeholder="What's happening?" minlength="3"></textarea>
```

### Maximum Length

```html
<textarea placeholder="What's happening?" maxlength="20"></textarea>
```

<mark>HTML allows us to apply as many validations as we wish to a form control</mark>

## Number Range

<mark>The min and max attributes only work with number-based form controls such as the number, dates and time inputs.</mark>

```html
<input type="number" id="quantity" name="quantity" min="1" value="0" />
<input type="number" id="passengers" name="passengers" max="5" value="0" />
```

## Pattern Validation

To add a pattern validation, we give the form control a **pattern** attribute with a regular expression as the value.

```html
<input
  type="text"
  id="zip_code"
  name="zip_code"
  pattern="(\d{5}([\-]\d{4})?)"
  title="Please enter a valid zip code, example: 65251"
  required
/>
```

## Styling Validations :invalid :valid

```css
input:invalid {
  border-color: red;
}

input:valid {
  border-color: green;
}
```

## Useful links

- [Forms constraint validation](https://www.sitepoint.com/html-forms-constraint-validation-complete-guide/).
- [Commonly used pattern regular expressions](https://www.html5pattern.com/)
- [How to validate forms](https://twitter.com/vponamariov/status/1400388896136040454)
- [How to Report Errors in Forms](https://www.nngroup.com/articles/errors-forms-design-guidelines/)
