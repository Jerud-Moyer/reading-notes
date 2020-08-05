## Responsive Web Design
- responsive overview
    - responsive vs adaptive vs mobile
        - responsive and adaptive are closely related and often transposedd as one and the same
        - responsive websites continually fluidly chan=ge based on viewport width, 
        - adaptive ones are built to group of preset factors
        - a combo is ideal
        - mobile is to make a seoarate site for mobile users
    - flexible layouts
        - use a flexible grid
        - use relative units of length when sizing boxes
    - media queries
        - provide the abibity to specify different styles for for individual browsers, viewports or device orientation
        - initializing media queries
        - link in html to separate css file
        - in css
            - @media all and (max-width: 1024px) {...}
            - @import url(styles.css) all and (max-width: 1024px) {...}
            - logical operators (and, not and only)
    - media features
        - min-width, max-width
        - orientation media feature
            - determins landscape or portrait
        - aspect ratio
            - pixel ratio
    - mobile first
        - design for mobile and use media queries to add styles for bigger viewports
        - can use "viewport" meta tag
        - viewport scale   
            - minimum-scal
            - maximum-scale
            - initial-scale
            - user-scalable
    - flexible media
        - embedded media
            - absolute position within parent
            - size container with flexible params
### all abot floats
- what is a float?
    - css positioning property
    - allows us to move elements around while parent text wraps around them
    - floated els remain part of the flow of the page
    - four valid values
        - left
        - right
        - none
        - inherit
    - clearing the float
        - Float's sister property is clear
            - both
            - left/right
            - none
            - inherit
    - problems with floats
        - pushdown
            - use overflow: hidden;
        - double-margin bug
            - set display: inline;
        - 3px jog
        - bottom margin bug
### Don't overthink it grids
- most websites now use grids
- box-sizng: border-box;
### css floats explained by riding on an escalator
- respect the pass lane
- floats can introduce up to two new flows of traffic
- 



