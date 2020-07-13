## HTML
### chapter 3 - lists
- ordered lists
    - ordered lists apear as numbered
    - ol ordered list element tag
    - li list tag for each item
- unordered lists
    - appear as bulleted
    - ul tag
    - li tags
- definition lists
    - a series of terms and their definitions
    - dl tags contain the list items
    - dt contain the term to be defined
    - dd tags contain the definition appear indented
- nested lists
    - you can nest ul tags inside other lists

## CSS
### chapter 13 - boxes
- box dimensions
    - width height
        - pixels offer exact box sizing
        - percentage offers percentage of browser window
        or of parent box
        - ems bases box size on the size of text within
    - min-width min-height or max
        - gives parameters for different size screens
    - overflow
        - hidden hides overflow content
        - scroll makes it scrollable
    - border, margin and padding
    - white spoce and verticle margin
    - border-width
    - border-style
        - solid, dotted, dashed, double, groove, ridge, inset, outset, hidden/none
    - border-color
    - centering content
        - set margins to auto
        - text-align: center;
    - IE6 box model
        - why microsoft?
    - change inline/block display
        - you can change inline to block or visa-versa with the display property
    - hiding boxes
        - visibilty property
    - border images
        - breaks an image into 9 smaller versions for a border (wierd)
    - box shadow (nice)
        - horizontal offset
        - vertical offset
        - blur distance
        - spread of shadow
        - use inset keyword for inner shadow
    - rounded corners
        - border-radius
        - create wacky shapes with different values

## JavaScript
### chapter 4 (continued)
- switch statements
    - starts with a switch value 
    - each case indicates a possible value for this variable and the code should run if the variable matches the value.
- type coercion
    - js can convert some data to complete an operation
    - js is said to use _weak typing_ because the data type for a variable can change
- truthy and falsy values
    - because of type coercion every value in JS can be treated as if it were true or false.
        - falsy values are treated as if they are false
        - truthy values are treated as if they are true
- checking equality and existence
    - use strict operators!
- short cicuit values
    - gonna need some thinking time on this
- loops
    - loops check a condition. if it returns _true_, the code block will run
    - then checked again and again and keep running until _false_
- 3 typrs of loops
    - for
        - to run code a specific number of times
        - the condition is usually a counger
    - while
        - if you dont know how many times it will run
        - condition can be something other than a counter, and the code will loop as long as it returns _true_
    - do while
        - similar to _while_ but will run at least once, even if condition evaluates to _false_
    - loop counters
        - initialization - let i =0;
        - condition - i < 10;
        - update - i++;
    - key loop concepts
        - keywords
            - break this says terminate and move to next block of code
            - continue says stp current iteration and then update and check condition again (if true code runs again)
        - loops and arrays
            - you can use a loop to affect each item in an array
        - performance issues
            - loops can slow the loading of your page
            - infinite loops are bad news
    - using for loops
        

