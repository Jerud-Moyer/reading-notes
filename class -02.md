## HTML
### chapter 2 - text
- whe creating a web page you add tags (markup)
    - structural markup
    - semantic markup
- headings
    - h1 - h6
- paragraphs
    - p
- bold and italic
    - b
    - i
    - use between p tags to highlight specific passages
- superscript and subscript
    - sup
        - <p>4<sup>th</sup></p>
    - sub
        - <p>co<sub>2</sub></p>
- whitespace
    - whitespace collapsing
- line breaks and horizontal rules
    - br
    - hr adds line
- visual editors
    - visual editor
    - code view
- semantic markup
    - not to affect structure
    - add extra information
        - screen readers
        - search engines
    - examples (of semantic tags)
        - strong
            - content has strong importance
            - needing emphasis
        - em
            - emphasis
            - subtle change
            - default to italic
        - blockquote
            - longer quotes (whole paragraph)
            - browsers will indent whole thing
            - can use p tags within
        - q
            - shorter quote
            - use q withhin p
        - abbr
            - used for abbreviations and acronyms
            - title attribute is used to log full meaning
        - cite 
            - when referencing a source (book,etc.)
            - displays italic
        - dfn
            - used to indicate the defining instance of a new term
        - address
            - used to contain contact details for author of page
        - ins
            - shows content that has been inserted to the document
            - displays underlined
        - del
            - shows content that has been deleted from the document
            - displays struck-through
        - s
            - no longer accurate but should not be deleted (ie price *before* sale)
            - displays struck-through

### chapter 10 - introducing CSS

- understanding CSS: thinking inside the box
    - there is an invisible box around every HTML element
        - block elements
            - look like they start on a new line
            - h1 - h6, p, div
        - inline elements
            - flow within the text and do not start a new line
            - b, i, img, em, span
    - css allows us to create rules that control the way that each individual box (and the contents of that box) is presented
        - boxes
            - width and height
            - borders
            - background colors or images
            - position in browser window
        - text
            - typeface
            - size
            - color
            - italics/ weight / case etc.
        - specifics
            - specific ways to style
                - lists, tables and forms
    - external CSS
        - link element used in HTML file to to tell browser where to find CSS
            - href specifies path
            - type specifies the type of document being linked to value should be text/css
            - rel specifies relationship between the HTML page and the file it is linked to. The value should be stylesheet when linking to a css file.
        - multiple css files may be linked. separated for fonts and colors for one and layout control for the other, for example.
    - internal css
        - you can include css rules directly in HTML file using style tag
        - this would go in the HEAD element type='text/css'
    - CSS selectors
        - universal selector * {} targets all elements on page
        - type selector h1.h2,h3 {} targets those elements
        - class selector .class {} targets named class
        - id selector #id {}
        - child selector li>a {} targets any a elements that are children of an li element (but not other a elements on the page.)
        - descendant selector p a {} targets any a elements that sit inside a p element even if there are other elements nested between them
        - adjacent sibling selector h1+p {} targets targets the first p element after any h1 element but not the other p elements
        - general sibling selector h1~p {} if you had 2 p elements that are siblings of  an h1 element this rule would apply to both.
    - how css rules cascade
        - last rule, if 2 selectors are identicle the latter of the 2 will take precedence.
        - specificity, if one selector is more soecific than the others, the more specific rule will take precedence.
        - important, you can add !important after any property value to indicate that should be more so than other rules hat apply to the same element
    - inheritance

    ## Javacript
    ### chapter - basic javascript instructions

    - a script is a series of instructions the computer follows one by one
    - each individual instruction is called a statement
    - js is case sensitive
    - each statement should start on a new line and end in a semicolon
    - statements can be organized into code blocks
    - code blocks are situated between curly braces
    - no semicolon after closing curly brace
    - you can write comment to explain what your code does
        - comments are not read by computer
        - multi line comments /* */
        - single line comments //
    - a script stores data in VARIABLES
    - declare variables with key words
        - const
        - let
    - assign them a value with the = assignment operator
    - data types
        - numeric
        - string
        - boolean
    - rules for naming variables
        - must begin with a letter, $, or _
            - never a number
        - name can contain letters, numbers, $, or _
            - not - or .
        - no keywords or reserved words
        - all variables are case sensitive
        - use a name that describes the kind of info the variable stores
        - use camelCase
    - arrays
        -  a variable with a list of values
        - [] with commas
        - numbering on arrays begins in 0
        use index numbers to acces items in array
    - expressions
        - 1 - expressions that just assign a value to a variable.
        const dumb = 'taking notes';
        - 2 - expressins that use 2 or more values to return a single value.
        const area = 6 * 9;
    - operators
        - assigment operators - =
        - arithmetic operators - + - * / % ++ --
        - string operators - +
        - comparison operators < > ==
        - logical operators - && === 

### chapter 4 - decisions and loops

- evaluating conditional statements
    - if (this happens) {
        do this;
    } else {
        do this;
    }
- more comaparison operators
    - == is equal to
    - != is not equal to
    - === strict equal to (data type and value)
    - !== strict not equal to
- a typical expression here would have 2 operands and one operator (jerud >= thor)
- or the operands could each be an expression ((sunshine + beach) > (poop + pee))
- or logical operators can be used here
    - && logical and
    - || logical or
    - ! logical not


