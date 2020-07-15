## HTML
### chapter 4 - links
- links are a defining feature of the web
    - allow easy movement between pages
- writing links
    - links created using __a__ element
        - specify destination with href attribute
        - users click on text between *a* tags
        - absolute urls link to other pages on web
        - relative urls link to pages within the same site
            - no need to specify domain name
- directory structure
    - you can place the pages for weach different section of the site in their own folders
    - top directory is the root
        - children
            - grand children
    - home page of a site written in HTML is called *index.html*
- relative urls
    - provide a shoethand for the browser to find your files 
    - relative link type
        - same folder
            - in the same folder, just use file name
        - child folder
            - childfolder/file
        - grandchild folder
            - child/grandchild/file
        - parent folder
            - ../file
        - grandparent folder
            - ../../file
- mailto
    - create a link that starts the users email program and begins an email with destination address
    - use *a* element
    - href begins with mailto: attribute
- links that open in new window
    - use *target* attribute
- link to specific part of same page
    - link to *id* attributes
    - value of href starts with *#value*
- link to specific part on other page
    - add *#value* (of id) to end of href link

## CSS
### chapter 15 - layout

- controlling position of elements
- creating site layouts
- designing for different sized screens

- key cocepts in positioning elements
    - building blocks
        - block level elements
            - start on a new line
        - inline elements
            - flow in between surounding text
    - containing elements
        - a block e,ement that contains other block elements is called a *parent element*
- controlling the position of elements
    - positioning schemes
        - normal flow
            - each block element appears below the last. regardless of width.
        - relative positioning
            - moves an element but not the others
        - absolute positioning
            - positions the element relative to its parent. out of normal flow, does nor=t affect position of others. move as users scroll
        - fixed positioning
            - a form of absolute that positions element in relation to browser window as apposed to parent element. do not affect others, do not move on scroll
        - floating elements
            - allows you to take out of normal flow and position to far right or far left of containing box. becomes block element around which others can flow.
        - when you move any element from normal flow, it can overlap. z-index property allows you to decide which will be on top.

## JavaScript
### chapter 3 (first part) functions, methods and arrays

- What is a function
    - function name(parameter, parameter, etc) {
        instructions; return value;
    }
    - declaring a function
        - give it a name, write the statements between curly braces
    - calling a function
        - calling the function function(); will execute the code in the curly braces
    - declaring functions that need info
        - if the function needs more info it will need to be passed parameters (in parentheses)
        - these will need to ba established in declaration and will act like variables within the function
    - calling functions that need parameters
        - when you call a function that has parameters, you specify the value of those parameters
    - getting a single value from out of a function
        - some fuctions return info to the code that called them.
    - getting multiple values out of a function
        - functions can return more than one value using an array
    - anonymous functions and function expressions
        - function declaration
            - the kinds of functions we have seen. declare them and call them any time.
        - function expression
            - a function where one might expect an expression
            - name usually omitted
            - not processed until interpreter gets to that statement
        - immediately invoked function expressions
            - or *iffy* not given a name, instead invoked as the interpreter comes upon them
                - const area = (function() { const width = 3; const height =2; return width * height; )()})
            - when to use anonymous functions and *iffys*
                - when code only needs to be run once within a task rather than repeatedly being called by other parts of the script
                    - as an argument to a function
                    - to assign value to a property of an object
                    - in event handlers and listeners
                    - to prevent conflicts between two scripts that might use the same variable names
    - variable scope
        - local variables
            - whena variable is created inside a function
                - when function is run twice, variables can have different values
                - different functions can use variables with the same names
            - global variables
                - created outside of functions and can be called anywhere in the script
        - how variables and memory work
            - global variable use memory for the duration that the page is in use
            - local variables are forgotten once that part of the script is run
            - the more variables you have, the more memory your script takes to run
            - naming collisions
                - be careful when naming global variables
                






        
