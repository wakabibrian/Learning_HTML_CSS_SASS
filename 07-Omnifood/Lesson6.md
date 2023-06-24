# Design and Development Process.

# Responsive Web Design

## Max-width

If the container width is larger than the specified max-width, then the width of the element is equal to the specified max-width.
If the container width is smaller than the specified max-width, then the width of the element is equal to 100% of the container element width.

# rem

-   rem - Root element font size
-   Root of the document is the html element (Parent element of all the others)
-   If we dont define the font size on the html element, then 1 rem is equal to the default browser font size (which is always 16px unless the user changes it)
-   When we want to change the font size in media queries we just change the font size of the html.
-   Recommend set the font size to a percentage of the font size of the browser (instead of the fixed) to allow users set their preferred font size
    e.g for 10px, 10px/16px -> 0.625 -> 62.5%
