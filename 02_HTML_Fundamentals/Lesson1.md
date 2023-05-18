# Lesson 1: Introduction to HTML

-   HTML - HyperText Markup Language
-   HTML is a markup language that web developers use to structure and
    describe the content of a webpage (not a programming language)
-   HTML consists of elements that describe different types of content:
    paragraphs, links, headings, images, video, etc.
-   It consists of opnening and closing tags
-   some elements without content like img have no closing tags
-   Web browsers understand HTML and render HTML code as websites

## Basic HTML Document Structure

-   Each html document has the following structure:

1. Doctype - html: Tells the browser that the document is html - uses html 5 specification to render the page (No closing tag)
2. html element: Each html page must start with html element (Which is the parent element of the head and body elements) (has closing tag)
3. head element: This is for elements that are not visible/not rendered in the browswer window.
   Examples of head elements:
    - title: title of the web page (has closing tag)
    - meta: meta data (data about the data) (no closing tag): has attributes like charset - UTF-8 (simple characters used in the English language)
4. body element: This contains all the elements that are visible on the web page.
   Examples of body elements:
    - headings
    - Other Text Elements

## Text Elements

1. headings: Used to breakdown big blocks of code into more logical sections and add a title to each of the sections.
   There are 6 headings (according to hierrachy): h1 - h6 (Have both opening and closing tags)
   h1 - Primary heading
   h2 - secondary heading
   h3 - h6 - Tertiary headings
   NOTE: Each page should have only 1 h1 heading (1 primary heading); it's of good practice
2. Paragraph: p element; used to mockup bigger blocks of text (has closing tag)

##### Adding Comments

A comment is a way of writing code that will not be visible in the browser.
Helps in writing comments about our code

3. bold and italic text:
   For bold: b - bold (Use of b is not a good practice - older html element)
   From html 5 we use strong element instead of b

    - b doesnt have semantic meaning (Without a specific meaning)
    - Strong means that it is an important text
      For italic: i - italic (Use of i is not a good practice - older html element)
      From html 5 we use em element instead of i
        - em - emphasize

4. Lists with bullet points and numbers
   ol element - ordered lists creating numbered lists
   ul element - unordered lists creating bullet points lists
   li element - li - list item; creates a list inside ol or ul

NOTE: Elements inside the parent elements are the child elements

## Images and Attributes

img element: For adding images (No closing tag)
We use attributes
Attributes are pieces of data which we can use to describe elements
e.g for images

-   src attribute: Describing the source from which the browser should read
-   alt attribute: Alternative text; text that should describe what the image is about
    alt helps search engines to know what is in the image
    alt helps blind people to use our website (Screen reader reads the alternative text)
    alt also displays the text incase the image is not found
-   width attribute: specifies the width
-   height attribute: specifies the height

Attributes for html element: lang; specifies the language of the document e.g en
for English, de for Germany

## Hyperlinks

Links (link between pages): Enables the internet to be a world wide web
Links can be in two categories

1. Link to other pages within our website (e.g home to blog page)
2. Link to outside of our website (e.g my page to udemy.com)
   To create a link we use a element (anchor) (Has closing tag)
    - we use the href attribute to provide the link we are pointing to
    - target attribute: specifies whether we want to open the page in a new tab (value: \_blank). By default the target attribute has value: \_self (opens from the same page)
    - To create a link which doesnt go anywhere, you use the # value for the href attribute

## Structuring our Page

Structuring the page (html 5 elements) help in grouping the html code in a logical way:
Elements used in structuring the page:

1. nav element: Page navigation; contains the navigation elements (groups the elements together)
2. header element: groups the heading and navigation of the page: Top part of a web document
3. article element: Body of the blog post
    - Inside the article we can also group the top part as heading
4. footer element: Specifies the footer (at the end of the page)
5. aside element: Secondary information that usually complements the information in the main page

-   Structuring (grouping) the page helps in styling using css and Semantic HTML

## Semantic HTML

Semantic means that some elements have a meaning or a purpose attached to them.
Always think about what the element does and means not only what it looks like.
Not all elements are semantic e.g b and i (use strong or em with meaning)
div element also has no meaning (like nav)
Why give our html meaning?

-   Search engine optimization
-   Important for accessibility (people who rely on screen readers)
