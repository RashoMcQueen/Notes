## Pseudo Class

```html
li:first-child{
<!--
  last-child
  nth-child(number, odd/even)
-->
}
```

## Pseudo Elements

```html
li::first-letter{
<!--
element::after: ;
element::before: ;
-->
}
```

## Styling hyperlinks

- a:link {}
- a:visited {}
- a:hover {}
- a:active {}

## Selector Priority

If multiple of any kind applies the last one
1. ID seclector
2. Class or pseudo class
3. Element selector
4. Universal selector

## Box Model

- Border: A line around the element, still inside of the element.
- Padding: Invisible space around the content, inside of the element.
- Margin: Space outside of the element, between elements.

## Absolute positioning

Element will position based on the first parent element  who has the position relative or viewport, if position based on parent, parent need to be position: relative;

## Common practives

- Use only classes
- Use hex and rgb only when needed transparency
