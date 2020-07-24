## JavaScript
### chapter 10 - error handling & debugging

- order of execution
    - functions do their job before that info being stored in a variable
- execution contexts
    - global context
    - function context
    - eval context
- variable scope
    - global scope
    - function level scope
- The stack
    - the js interpreter reads one line at a time
    - whena statement needs data from another function it stacks the new function on top of the current task
- execution context and hoisting
    - two phases of activity
        - prepare
        - execute
- understanding scope
    - each execution contextbhas its own variables object
- understanding errors
- error objects
    - can help you fine your mistakes
    - 7 types
        - Error
            - the basic error
        - SyntaxError
            - syntax is not correct
        - ReferenceError
            - variable does not exist
        - TypeError
            - value is unexpected data type
        - RangeError
            - number outside of range
        - URIError
            - incorrect use of URI functions
        - EvalError
            - incorrect use of eval() function
- how to deal with errors
    - debug the script to fix errors
    - handle errors gracefully
- a debugging workflow
    - debugging is about deduction
        - where is the problem?
            - dev tools helpful here
        - what exactly is the problem?
            - breakpoints will help
    - keep notes
- browser dev toools and JS console
    - these can tell ya where a problem is and what it might be
- you can type code in the console!
- write from the script
- logging data  to the console
    - console.log()
    - console.info()
    - console.warn()
    - console.error()
    - console.group()
    - console.table()
    - console.assert()
- breakpoints
    - useful for stopping code at aparticular point
    - with multiple points you can 'step through' code
    - conditional breakpoints
        - indicate a breakpoint should be triggered only if specific conditions are met
    - debugger keyword
        - works like breakpoints
    - handling exceptions
        - try
            - first try this code
        - catch
            - if try fails, catch steps in with an alternative
        - finally
            - finally will run either way if try works or fails
- throwing errors
    - if you know something might cause a problem for your script you can gennerate your own errors before the interpreter creates them
- debugging tips
    - another browser
    - add numbers
        - log num,bers to console so you can see how far code runs before breaking
    - strip it back
        - remove parts of code to a bare minimum you need
    - explaining the code
        - rubberducking
    - search
        - stack overflow etc.
    - code playgrounds
        - JSBIN.com etc
    - validation tools
        - linters and such
