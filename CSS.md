# What is CSS?

- Cascading Style Sheets
- Responsible for styling the web
- HTML → structure | CSS → layout/style
- Syntax: selector{property:value;property:value}

```html
<link rel="stylesheet" href="style.css" />
```

- hierarchy of importance: inline styling > internal styling > external styling

  - CSS Rule is made up of selectors, declaration blocks, declaration as property and value

- Specificity explains priority of styling
- element selectors are used to style all elements on the page h1 {....}
- classes can be used to select a specific group of elements .class {...}
- id's can be used to select specific objects (should be unique) #title {....}
- universal Selector * {...} selects all of the elements with the least amount of specificity
- inheritance implies styling added from other elements, even if not specifically dictated to them
  - only same properties will be overwritten
- Last Rule dictates that the last stated property will be the one applied if same property
- Browser Prefixes (-webkit/-moz/etc.) help certain browsers understand latest versions of css
  - [caniuse.com](http://caniuse.com) will tell which versions of webapps support certain syntaxes

# Past the Basics

- Color
  - rgb color selector is scale from 0-255
  - most to least (white 255, 255, 255 and black is 0, 0, 0)
  - rgba affects opacity and transparency (0 is clear/tranparent and gets more opaque as it gets closer to 1.0)
  - hex values #RRGGBB
    - 123456789 A(10) B(11) C(12) D(13) E(14) F(15)
      - 10 11 12 13 14 15
      - #FF000 - RED
      - #00FF00 - GREEN
  - hsl is really deep
  - [coolors.com](http://coolors.com) will give you color palette
- Units and Layout
  - font-size, width, height, pixels
  - pixel size is absolute value
  - percent is relative value
  - em is relative and depends on parent
    - 1em = 16px default browser style
    - 1em = base value
    - rem = RELATIVE depends on root
  - vh/vw - height/width - percent of screen
  - _user agent stylesheet_ is from default browser styles
- Typography

  - font families will try to style as special font, and then next font if browser does not support
  - font-stack generic-family
  - serif, sans-serif, cursive, fantasy, monospace are all generic
  - google fonts is cool
  - font-weight changes boldness
  - line-height and letter-spacing
  - text-transform for uppercase and lowercase
  - text-decoration for formatting (eg. underline, making links look like normal text, etc.)

- CSS Box Model

  - each element is displayed as a box

  ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3c1fd3a3-2285-4495-a176-f92a0602aead/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3c1fd3a3-2285-4495-a176-f92a0602aead/Untitled.png)

  - shortcuts for distances can be written easily
    - padding: 50px; === 50 pixels all around
    - padding: 30px 60px; === 30 pixels top and bottom/60 pixels left and right
    - padding: 20px 40px 60px 10px; === 20 pixels top/40 pixels right/60 pixels bottom/10 pixels left (clockwise from top)
    - padding, margin, border are interchangeable in above example
  - CSS Box Model also has browser defaults
  - border-width/style/color: == can be used to style borders
    - border-radius: == can add curve to border options (percentage)
  - margin can have negative values
  - auto margin can be used to change items based on its contents length

- Display Property
  - Block: always starts a new line and takes full width
  - Inline: Does not start a new line and only takes up as much as content space
  - Horizontal Centering
  - display, opacity, and visibility change how much you can see values on scale from 0 to 1.0
    - display:none means you wont be able to see it at all and others mean it is there but ranges in visibility
- Background Image Properties

  - repeat/norepeat

- Gradient
  - colorzilla
- Media Queries
  - @media screen and (max/min-width: ...px) {...} === will change how the page behaves depending on the size of the browser
  - z-index → z-axis === changes what is on top (only works with position of relative or absolute NOT static)
- Psuedo Elements
  - pseudo elements ::before ::after CONTENT not element
  - content: '' - - - required even if it is not filled
  - img - - - does not work
- Selectors

  - Basic
    - \*all === all elements (least priority)
    - #id === specific id's
    - .class === specific class
    - element === specific elements (p, h1, h2, etc.)
  - Descendant and Child Combinators

    -

    There are four special combinators provided by CSS:

    - General sibling selector (~)
    - Descendant selector (space)
    - Child selector (>)
    - Adjacent sibling selector (+)

    Let us discuss each of them one by one and see how to implement them:

    ## **General Sibling Selector**

    It is implemented for selecting the element which trails the initial or first selector element; as well as shares the same parent as first selector element also. The general sibling selector is implemented explicitly for choosing a group of elements which gets allocated for the same parent element.

    Here is a sample example of how it can be implemented:

    Example:

    ```
    <!DOCTYPE html>
    <html>

    <head>
        <style>
            div ~ p {
                background-color: whitesmoke;
            }
        </style>
    </head>

    <body>

        <p>Some text here.</p>
        <div>
            <p>Some text here.</p>
        </div>
        <p>Some text here.</p>
        <p>Some text here.</p>

    </body>
    </html>
    ```

    ## **Descendant Selector**

    This selector is implemented for selecting every single child elements within the particular tag mentioned in the CSS selector section. The tags may be of the direct child of any specific tag or can be extremely deep within the particular tag. Here is code snippet showing below the how descendant selector adds <p> elements which are within the <div> elements.

    Example:

    ```
    <!DOCTYPE html>
    <html>

    <head>
        <style>
            div p {
                background-color: whitesmoke;
            }
        </style>
    </head>

    <body>

        <div>
            <p>This Paragraph is within div.</p>
            <p>This Paragraph is within div.</p>
            <section>
                <p>This Paragraph is within section and section is within div.</p>
            </section>
        </div>
        <p>This Paragraph is not within div.</p>

    </body>
    </html>
    ```

    ## **Child Selector**

    It is implemented for selecting that particular element which lies within the immediate child of that specific tag. It is more precise or exact than the descendant selector since it chooses only the second selector if it has the first selector element as its parent.

    Example:

    ```
    <!DOCTYPE html>
    <html>

    <head>
        <style>
            div > p {
                background-color: whitesmoke;
            }
        </style>
    </head>

    <body>

        <div>
            <p>This Paragraph is within div.</p>
            <p>This Paragraph is within div.</p>
            <section>
                <p>This Paragraph is within section and section is within div.</p>
            </section>
        </div>
        <p>This Paragraph is not within div.</p>

    </body>
    </html>
    ```

    ## **Adjacent Sibling Selector**

    This selector is implemented for selecting all those elements, which are the contiguous or neighboring siblings of a particular element. Here, the sibling elements ought to have the identical parent element as well as "adjacent," i.e., "immediately following".

    Here is an example of how to implement this adjacent sibling selector:

    Example:

    ```
    <!DOCTYPE html>
    <html>

    <head>
        <style>
            div + p {
                background-color: whitesmoke;
            }
        </style>
    </head>

    <body>

        <p>This Paragraph is not within div.</p>
        <div>
            <p>This Paragraph is within div.</p>
            <p>This Paragraph is within div.</p>
        </div>
        <p>This Paragraph is not within div.</p>

    </body>
    </html>
    ```

  - ::first-line ::first-letter === affects styling
  - :hover === changes style when mouse hovers over element
  - a: —> :link :visitied :hover :active
  - :root === root element of the document

- Transform

  - transform: translate( ), rotate( ), scale( ), skew ( )
  - transition: (change over time)
    - transition-property:
    - transition-duration:
    - transition-delay:
      - can all be written together (transition: all 1s .3s;)
      - transition-timing-function: all 1s .... .3s;
        - ease, linear, ease-in, ease-out, ease-in-out
  - animation: (change over time with points) (transition is from 0-100% and animation can be anything in between)

    - always needs animation-name, animation-duration, and animation-iteration-count
    - @keyframes move {....}

    ```css
    div {
    	width: 200px;
    	height: 100px;
    	margin: 10px;
    	color: beige;
    }
    .animation {
    	background: blue;
    	animation: move 5s 7;
    	animation-fill-mode: forward;
    }
    @keyframes move {
    	0% {
    		opacity: 0;
    	}
    	25% {
    		transform: translateX(200px);
    		opacity: 0.25;
    	}
    	50% {
    		transform: translateX(-100px);
    		opacity: 1;
    	}
    	100% {
    		transform: translateX(0);
    		opacity: 0.5;
    	}
    }
    ```

- CSS Variables
  - —varName:value
  - poperty:var (—varName) (clutch and can be used as variables)
  - :root{ } === global
  - element === local
- Icons

  - Font-Awesome Icons are free, easy, and simple (finesse.cap = 890831)

  ```css
  <link rel="stylesheet" href="/setup.folder/fontawesome-free-5.14.0-web/css/all.css">
  ```

- Text-Shadow/Text-Box
  - x-axis, y-axis, blur, color
  - can also use text shadow generator
- Semantic HTML Tags
  - A semantic element clearly describes its meaning to both the browser and the developer.
    - Examples of **non-semantic** elements: `<div>` and `<span>` - Tells nothing about its content.
    - Examples of **semantic** elements: `<form>`, `<table>`, and `<article>` - Clearly defines its content.
- Emmett
  - element.\_ \_ \_=== creates classes
  - element#\_ \_ \_=== creates id's
  - element>\_ \_ \_=== creates children
  - element\*(#)=== creates multiples of whatever indicated (list items, etc.)
  - element{....}=== creates text
