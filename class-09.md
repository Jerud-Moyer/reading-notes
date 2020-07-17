## HTML
### chapter 7 forms
- form controls
    - adding text
        - input, passwords, etc.
    - making choices
        - radio buttons, checkboxes, drop down boxes
    - submitting
        - buttons
    - file uploads
- how forms work
    - user fills in form uses button to submit
- form structure
    - form controls inside form el
    - each el needs an action attribute
    - forms can be sent using one of two methods
        - get
            - short forms, search boxes etc.
        - post
            - longer, has uploads, etc.
    - text input
        - input el
            - type='text'
            - type='password'
    - text area
        - textarea el
        - multi line text input
    - radio button
        - input el
        - type='radio'
    - check box
        - input el
        - type="checkbox"
    - drop down list box
        - select el
        - option el
    - file input box
        - input el
            - type="file"
    - submit button
        - input el
        - type='submit'
    - image button
        - input el
        - type='image'
    - grouping form els
        - fieldset el
        - legend el
    - input 'types'
        - date
        - email
        - url
        - search
        
## CSS
### chapter 14 - lists, tables and forms

- bullet point styles (uls)
- disk
    - circle
        - square
- ols
    - decimal
    - decimal-leading-zero
    - lower-alpha
    - upper-alpha
    - lower-roman
    - upper-roman
- list-style-image
    - use image for bullets
    - list-style-position
        - bullet inside text box
        - bullet outside tb
- table properties
    - same as for all else
    - empty-cells
    - border-spacing
    - border-collapse
- use your css to make forms more readable!

## JavaScript
### chapter 6 - events
- UI events
    - load
    - unload
    - error
    - resize
    - scroll
- Keyboard events
    - keydown
    - keyup
    - keypress
- mouse events
    - click
    - dblclick
    - mousedown
    - mouseup
    - mousemove
    - mouseover
    - mouseout
- focus events
    - focus/focusin
    - blur/focusout
- form events
    - input
    - change
    - submit
    - reset
    - cut
    - copy
    - paste
    - select
- mutation events
    - DOMSubtreemodified
    - DOMNodeinserted
    - DOMNoderemoved
    - DOMNodeinsertedIntoDocument
    - DOMNodeRemovedFRomDocument
- ways to bind an event to an el
    - HTML eveny handlers
        - do not use
    - treaditional DOM event handlers
        - element.onevent = functioname
    - DOM level 2 handlers
- event listeners
    - newer way to handle events
    - they can deal with more than one
- using parameters with ehandlers and listeners
- event flow
    - event bubbling
        - js can make it co events also trigger parent els
        - events starts at most specific node, then travels outward
    - event catpturing
        - event starts at least specific node and travels inward
    - why flow matters
        - flow only really matters when we have event handlers in our code on an element *and* one of it's ancester elements.
        - default is bubbling
        - final parameter in addEventListener
        is boolean. true = capoturing and false = bubbling
- the event object
    - when even=t occurs the object tells you info about the event and the el it happened on.
    - using e listeners with the event object
- event delegation
    - e listeners for many els can slow down a page, flow allows you to listen for event on parent el
    - works with new els
    - solves limitations with *this* keyword
    - simplifies your code
- changing defaiult behavior
    - event object has methods to change default behavior of an el and its ancestors
        - preventDefault()
        - stopPropagation()
        - using both methods
            - return false
- different types pof events
    - w3c DOM events
    - HTML5 events
    - BOM events
- ui events
    - load / unload
    - error
    - resize
    - scroll
- focus and blur events
- mouse events
- click
- event object tells you where the cursor was when event was triggered
- keyboard events
- form events
- mutation events
- HTML 5 events









