# Lesson 3: Layouts: Floats, Flexbox and CSS Grid

Layout is the way text, images and other content are placed and arranged on a webpage (instead of having them one after another; normal flow)
Layout gives the page a visual structure and into the structure we place the content

## Types of layouts

-   Page Layout: Laying out elements (big pieces - components) inside of a web page
-   Component Layout: Laying out smaller components inside of the big pieces (components)

## 3 Ways of Building Layouts

1. Float Layouts (old way of building layouts) - using the float css property
2. Flexbox (one of the modern ways of building layouts) - Its perfect for building one dimensional layouts (a layout with just a row) - Perfect for component layouts
3. CSS Grid (one of the modern ways of building layouts) - For laying out elements in 2-dimensional grid. Perfect for page layouts and complex components

## Using Floats

Using css property: float (left, right or none)
The selected element, all other elements float around it

### Normal Flow

-   This is the default positioning of elements on our page
-   We can achieve this value by using css _position: relative_
-   Element is "in flow"
-   Elements are laid out according to their order in the HTML source code

### Absolute Positioning

-   This allows us to absolutely position our elements any where on the page
-   We can achieve this value by using css _position: absolute_
-   Element is removed from the normal flow: "out of flow"
-   No impact on surrounding elements. It might overlap them
-   We use top, bottom, left, right property to offset the element from its relatively positioned container
-   The relative element must be a parent container
-   By default, the relative container is the viewport

### Floats

-   Element is removed from the normal flow: "out of flow"
-   Text and inline elements will wrap around the floated element
-   The container will not adjust its height to the element
-   css property;
    float: left
    float: right

### Clearing Floats

Since the height of the container element of floated item collapses, we need to clear floats
We have to add another element at the container element and clear the floats from there
We use the _clear_ css property (value both for all left and right floats)

To prevent having empty divs; use the clear fix hack
Add a clearfix class on the element with a collapsed height and use pseudo elements clearfix::after then clear: both

### box-sizing: border-box

<img src="../Resources/box-sizing.jpg" alt="box-sizing" width="400px" />

-   border-box changes the default model of box model, the element takes the defined width and height of the element. Instead of adding width or height, and padding
-   The default behavior is content-box
-   Advised to put it on all the elements(\*)

## Flexbox Introduction

Use a css property _display: flex_ on a container with child elements. Makes all elements side by side.
The elements are flex items because they are the child elements of the flex container

### Vertical Alignment

-   Center elements vertically - _align-items: center_
-   Put elements at very start (top) - _align-items: flex-start_
-   Put elements at bottom - _align-items: flex-end_
-   By default - _align-items: stretch_ (all elements stretch as tall as the tallest element)

### Horizontal Alignment

-   Center elements horizontally - _justify-content: center_
-   Distribute space evenly between elements - _justify-content: space-between_

## A Flexbox Overview

What is Flexbox? Flexbox is a set of related CSS Properties for building 1 dimensional layouts
Helpful for aligning items one another inside a container both horizontally and vertically
Flexbox solves common problems such as vertical centering and creating equal height columns
Flexbox is perfect for replacing floats, allowing us to write fewer and cleaner HTML and CSS code

### Flexbox Terminology

<img src="../Resources/css-flex-box.png" alt="CSS Flex Box" width="600px" />

Flex Container: The element on which you want to use flexbox (Set display: flex)
Flex Items: The child elements of the flex container element
Main Axis: The direction on which the flex items are laid out
Cross Axis: The perpendicular axis of the main axis

### All CSS Properties for flex box (Both for flex container and Flex Item)

**Flex Container**

1. gap: 0 - To create space between items, without using margins
2. justify-content: flex-start | flex-end | center | space-between | space-around- To align items along main axis (Horizontally by default)
3. align-items: stretch | flex-start | flex-end | center | baseline - To align items along across axis (vertically by default)
4. flex-direction: row | row-reverse | column | column-reverse - To define which is the main axis
5. flex-wrap: nowrap | wrap | wrap-reverse - To allow items wrap into a new line if they are too large
6. align-content: stretch | flex-start | flex-end | center | space-between | space-around - Only applies when there are multiple lines (flex-wrap: wrap)

**Flex Items**

1. align-self: auto | stretch | flex-start | flex-end | center | baseline - To overwrite align-items for individual flex items
2. flex-grow: 0 - To allow elements to grow (0 means no, 1+ means yes) (1 Allows the elements to grow as they can in the container, they will have the same size)
3. flex-shrink: 1 - To allow elements to shrink (0 means no, 1+ means yes) (1 allows the content fit in the container)
4. flex-basis: auto - To define an item width, instead of width property
5. flex: 0 1 auto - Recommended, shorthand for flex-grow, -shrink, -basis
6. Order: 0 - Controls order of items (-1 makes the item first, 1 makes it last - specify a number greater or less than the other. By default, order is 0 for all elements)

-   The two properties flex-direction and flex-wrap are used so often together that the shorthand property flex-flow was created to combine them. For example, you can use flex-flow: row wrap to set rows and wrap them.
-   flex-grow: 1 on only one element, allows only that one element grow
-   flex-grow: 2 on only one element, doubles the grow in comparison to other elements
-   For flex-shrink, flex-grow and flex-basis, always use the shorthand property
-   for automatic width and spacing; flex: 1

## CSS Grid Introduction

CSS Grid is the most modern way of building layouts & its the most complete one and the easiest

-   In CSS Grid, we have Grid Container and Grid Items; similar logic to flex container and flex items
-   We define our 2-Dimensional layout; columns and rows
-   grid-template-columns - number of columns and size
-   grid-template-rows - number of rows and size
-   column-gap - space between columns
-   row-gap - space between rows

### CSS Grid Overview

-   CSS Grid is a set of CSS properties for building 2 dimensional layouts
-   Divide a container element into rows and columns that can be filled with its child elements
-   CSS Grid allows to write less nested HTML and and easier-to-read CSS
-   CSS Grid is not meant to replace flexbox.Instead they work together perfectly; for 1D layout? use flexbox. For 2D layout, use CSS Grid.

### CSS Grid Terminology

Grid Container: Is where everything happens (display: grid)
Grid Items: These are the child elements of the grid container.
Row Axis and Column Axis (You can not change the direction)

### More CSS Grid Terminology

<img src="../Resources/css-grid.png" alt="CSS Grid" width="600px" />

Grid lines: Lines which divide up the grid and separate the columns and rows. (Grid lines = no. of columns + 1 and no. of rows + 1)
Grid Cells: Might be filled by a grid item of not.
Gutters or Gaps: Space between items.
Grid Track/row/column: In the picture above we have two row tracks amd three column tracks.

### All CSS Properties for CSS Grid (Both for Grid container and Grid Item)

**Grid Container**

1. grid-template-rows: <track size> and grid-template-columns: <track size>; To establish the grid row and column tracks. One length unit for each track. Any unit can be used, new fr fills unused space.
2. row-gap: 0 and column-gap: 0 (gap: 0); To create empty space between tracks.
3. justify-items: stretch | start | center | end and align-items: stretch | start | center | end; To align items inside rows / columns (horizontally / vertically)
4. justify-content: start | start | center | end | ... and align-content: start | start | center | end | ...; To align entire grid inside grid container. Only applies if container is larger than the grid.

**Grid Items**

1. grid-column: <start line> / <end line> | span <number> and grid-row: <start line> / <end line> | span <number>; To place a grid item into a specific cell, based on line numbers. span keyword can be used to span an item across more cells.
2. justify-self: stretch | start | center | end and align-self: stretch | start | center | end; To overwrite justify-items / align-items for single items

### Sizing Grid Columns and Rows

using fr unit instead of px will allow us create flexible columns and flexible rows e.g grid-template-columns: 1fr 1fr 1fr 1fr; will set 4 columns at the same size.

-   With auto it will only take the size necessary to fill its content.
-   Also grid-template-columns: repeat(4, 1fr) will set 4 columns at the same size.
-   grid-template-rows; you have to also define a height.

### Placing and Spanning Grid Items

-   You can turn on and view grid from dev tools.
-   You can use the indicated grid lines to place the grid items anywhere you want.
-   Specify both the grid-column and grid-row, both the start and end e.g grid-column: 2/3; grid-row: 1/2;
-   To span across cells, you can use either grid-column: 2/4; or grid-column: 2 / span 2;
-   To span all the way to the end, you can use grid-column: 1 / -1;

### Aligning Grid Items and Tracks

#### Aligning Tracks inside a container

1. justify-content: start | end | center | space-between | space-around- To align tracks inside the container Horizontally
2. align-content: start | end | center | space-between | space-around - To align tracks inside the container Vertically

#### Aligning items inside cells: Moving items around inside the cells

1. Vertically: align-items: center | start | end; (by default, stretch)
2. Horizontally: justify-items: center | start | end; (by default, stretch)

**For individual items**;
align-self and justify-self

**Note**

-   For small components: Use flex box (one dimensional)
-   For overall page layout: Use CSS Grid (two dimensional)
