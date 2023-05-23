# Lesson 2: Introduction to CSS

CSS - Cascading Style Sheets
CSS Describes the visual style and presentation of the content written in HTML
CSS consists of lots of properties that are used to format the content; eg properties about the font,text, spacing, layout etc
CSS has a selector, Declaration/Style (Property and value)

## css rule

<img src="../Resources/css_rule.webp" alt="CSS Rule" width="500px" >

## Inline, Internal and External CSS

There are 3 places where we write our css;

-   Inline CSS
-   Internal CSS
-   External CSS

### Inline CSS

This is a way of writing the CSS inside of the elements using the style attribute

-   Inline styles should never be used (No separation of concerns)

### Internal CSS

This is a way of writing the CSS inside the head ealement, using the style element

-   This is incase of alot of CSS code (No separation of CSS code from HTML)

### External CSS

Most preferred

-   You use a separate css file (eg. style.css)
-   We link the css file to html using the _link_ element, in the head element
-   The link tag has the rel, and href properties (attributies)
    -   rel property specifies that it's a stylesheet
    -   href property specifies the path

## Styling text with css (6 Properties)

_font-size_ - specifies the size of the text. By default, font-size is 16px
_font-family_ - specifies different fonts for the text
_text-transfer_ - Turns the text uppercase, or, lowercase or capitalised etc
_font-style_ - turns the text italic etc
_line-height_ - specifies space between lines (no units). By default, line-height is 1
_text-align_ - Aligns the text left, right or center (with reference to the parent element)
_font-weight_ - Makes the text bold

## Combining selectors

Combine selectors with repeated properties and values

### List selector

-   Create a list of selectors and apply the repeated properties
-   We use commas to create a list of selectors e,g h1, h2, h3, h4

### Descendant selector

e.g footer p - selects all the p elements that are inside the footer element

-   To avoid errors (confusion) with other elements, you can make a descendant inside another descendant e. article header p

## Class and ID Selectors

Instead of descendant selectors, its better to give elements names and use their names to select them in css

To select elements;
id - use #
class - use .

-   We are not allowed to repeat id names (We can only use each id name only once)
-   If we need to reuse a name multiple times, then we have to use classes

## Other css styles

_list-style_ - Removes bullets on lists
_text-decoration_ - Removes underline

## Note

In the real world we don't use ids. We only use classes because by using classes we are prepared for the future
Just incase we want to add another related item in the future, we can easily style it with the same css style.
Making the code ready for potential changes

## Working With Colors

**Ways of representing colors**
The RGB Model: Here every color can be represented by a combination of Red, Green and Blue colors.
We give each of the above 3 colors any value between 0 and 255 hence giving a total of 16.8 million colors

Two Ways of representing colors using the RGB Model;

1. RGB/RGBA Notation: e.g rgb(0, 255, 255), rgb(244, 179, 63),rgba(0, 255, 255, 0.3) (RGB with transparency (alpha))
2. HexaDecimal Notation (More used in css): Here we use a scale from 0 to ff. ff is the same as 255 in hexadecimal scale.
   e.g #00ffff. Shorthand is always used when all the colors are identical pairs #0ff

We always use a color picker to generate code.

-   In practice we usually use the hexadecimal notation and when we want transparency, we use the rgba notation

### Shades of Greys

-   These are a special kind of colors.
-   When colors in all the 3 channels are the same, we get the grey color. e.g rgb(0,0,0) or #000, rgb(69, 69, 69) or #444
-   There are 256 grey colors to choose from.

### Color CSS Properties;

_color_: For text
_background-color_: For background
_border_: For borders around an element e.g border: 1px solid #000
border is a special kind of property because we can use one property to define 3 different properties

For colors we can also use the predefined colors names e.g red or blue etc

## Pseudo-classes

A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). For example, the pseudo-class :hover can be used to select a button when a user’s pointer hovers over the button and this selected button can then be styled

-   You use : for a pseudo-class.

other examples of pseudo-classes;

-   _li:first-class_: selects the first element of the list
-   _li:last-child_: last child inside of its parent container
-   _li:nth-child(2, odd, even)_: targets a specific child e.g second

## Styling Hyperlinks

Here we use Pseudo Classes to help target different states of the links.
_a:link_: Targets the anchor elements with an href attribute
_a:visited_: Targets the anchor elements which are visited before. In practice, always use the same color as the link pc
_a:hover_: targets the hover state of a link
_a:active_: targets the active state of a link

Always defined in the above order

## Using Chrome DevTools

-   Open dev tools
-   Go to elements tab to inspect the different elements
-   Go to style tabs to see the different styles applied to elements
-   You can apply styles from devtools for testing purposes only
-   We can fake that the link is being hovered by clicking on the :hov and checking the :hov checkbox, and active etc

## CSS Theory #1: Conflicts Between Selectors

-   Conflicting when there are multiple selectors selecting the same element e.g by using id, class, element selector e.c
-   Which of the rule applies... all of them apply

### Resolving Conflicting Declarations (Selector specificity)

We have consider according to priority; Hightest to Lowest priority
If there are multiple of the same selector (same hierarchy, same priority), then it is the last that is applied;

-   5. Declarations marked with !important keyword (Highest priority)
-   4. Inline styles (Style attribute in the HTML)
-   3. Id (#) selector
-   2. Class (.) or Pseudo Class (:) selector
-   1. Element selector (p, div, li etc)
-   0. Universal (\*) selector (Lowest priority)

!important keyword should only be used as a last resort

-   Always hover on the selector in the css code to know the specificity
-   Always write your code as simpler as possible

## CSS Theory #2: Inheritance and the Universal Selector

**Inheritance** is a mechanism by which some styles, some properties get their values inherited from parent elements to child elements

-   _body_ element is the parent element of all other elements
-   Only values about text get inherited e.g font-family,font-size, font-weight,font-style,color, line-height, letter-spacing, text-align, text-transform, text-shadow, list-style etc
-   An inherited style is easily overridden by any rule which has a value for that same property.
-   Universal selector (\*) selects all elements

## CSS Theory #3: The CSS Box Model

<img src="../Resources/boxmodel.png" alt="css box model" width="500px">

The Box Model explains how elements are displayed on a web page and how they are sized

-   Each of the content e.g text, image etc can be seen as a rectangular box with a border, space inside and outside
-   Border: A line around the element, still inside of the element.
-   Padding: Invisible space around the content, inside of the element.
-   Margin: Space outside of the element, between elements
-   Content, padding and the border are the visible part of the element
-   All the above are optional
-   Fill area (Content, padding, border): Area that gets filled with background-color or background image

### Element Height and Width Calculation

Final element width = left-border + left-padding + width + right-padding + right-border
Final element height = top-border + top-padding + height + bottom-padding + bottom-border

-   We can specify all the above using css properties

## Using Margins and Paddings

Styles used;

-   padding
-   padding-left
-   padding-right
-   padding-top
-   padding-bottom
-   (Shorthand): padding:top&bottom left&right
-   margin
-   margin-left
-   margin-right
-   margin-top
-   margin-bottom

Global reset: \* { margin: 0; padding: 0;}
Always use either margin bottom or margin top but do not mix. Preferably use margin-bottom

Padding - for elements with background color and borders (side)

### Collapsing Margins

When two margins occupy the same space, they collapse ie the highest margin will take up the space

## Adding Dimensions

use _width_ and _height_
set height or width to _auto_ if the height was specified previously
using percentage(%) is usually of the parent container (changes in responsiveness)

## Centering our Page

Best trick for centering a page.

-   Put all of the content into a container element
-   Give a container certain width
-   Center the container inside of the browser (Add margins to the left and right of the container (auto))

## CSS Theory #4: Types of Boxes

**Block-Level Elements**

-   Some boxes occupy the entire all the space they can horizontally (100% of parent element) and create line breaks after them. They cannot be side by side with one another (eg h1-6, p, body, header, footer, section, nav, aside, div etc) - block level boxes or elements.
-   Box model applies as before
-   With CSS:display: block

**Inline-Level Elements**

-   Some boxes occupy only their space, or width needed for its content (span, strong, em, img, a, button etc) - inline boxes
-   Causes no line breaks after or before the element
-   Box model applies in a different way: heights and width do not apply
-   Paddings and margins are applied only horizontally (left and right)
-   With css: display: inline
