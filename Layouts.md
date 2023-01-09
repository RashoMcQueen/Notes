# Floats

```html
element{
  float: ;
}
```

# Flexbox

## Flex Container
- gap
- justify-content
- align-items
- flex-direction
- flex-wrap
- align-content

## Flex Items
- align-self
- flex-grow
- flex-shrink
- flex-basis
- flex 
- order

## Flex Basis
For width

# Grid

## Grid container properties 
- grid-template-rows: <track size>*
- grid-template-columns: <track size>*
- row-gap / column-gap / gap
- justify-content
- align-content

## Grid items
- grid-column / grid-row , to place a grid item into a specific cell, based on line numbers. _span_ key can be used to span an item across more cells.
- justify-self / align-self

## Stuff
fr for flexible width, similar to flex: 1
grid-template-columns: repeat(4, 1fr);

to move grid item to wanted position
```css
.grid-item{
  grid-column: 2/3;
  grid-row: 1/2;
}

/* to expand a item*/
grid-column: 1 / span 3; /* expands three spaces*/
grid-column: 1 / -1; /* expands till the end of the row*/
```

Aligning tracks inside container:
```css
justify-content: center;
align-content: center;
```
Aligning items inside cells
```css
align-items: center;
justify-items: center;
```

## Useful stuff
inline elements don't apply top or bottom properties, to fix display:block
box-sizing: border-box;
