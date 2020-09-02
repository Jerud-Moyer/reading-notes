## Promise
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
- The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value
### Description
- A Promise is a proxy for a value not necessarily known when the promise is created
- A promise is in one of these states
    - pending: Initial state, neither fulfilled nor rejected.
    - fulfilled: meaning that the operation completed succesfully
    - rejected: meaning that the operation failed
- A pending promise can either be fulfilled with a value, or rejected with a reason (error). When either of these options happens, the associated handlers queued up by a promise's then method are called. If the promise has already been fulfilled or rejected when a corresponding handler is attached, the handler will be called, so there is no race condition between an asynchronous operation completing and its handlers being attached.
- Chained promises
    - The methods promise.then(), promise.catch(), and promise.finally() are used to associate further action with a promise that becomes settled. These methods also return a newly generated promise object
    - the promises of a chain are nested
- Constructor
    - Promise()
    - creates a new Promise object
- static methods
    - Promise.all(iterable)
    - Promise.allSettled(iterable)
    - Promise.any(iterable)
    - Promise.race(iterable)
    - Promise.reject(reason)
    - Promise.resolve(value)
- instance methods
    - Promise.prototype.catch()
    - Promise.prototype.then()
    - Promise.prototype.finally()
## Destructuring assignment
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
- this is a JS expression that allows us to unpack values from arrays or properties from objects into distinc variables
- Description
    - the object and array literals expressions provide an easy way to create packages of data
    - The destructuring assignment uses similar syntax, but on the left-hand side of the assignment to define what values to unpack from the sourced variable
## Spread Syntax
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax
- Spread syntax (...) allows an iterable such as an array expression to be expanded in places where zero or more arguments (or function calls) or elements (for array literals) are expected. or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.
- Rest syntax (parameters)
    - Rest syntax looks exactly like spread syntax. In a way, rest syntax is the opposite of spread syntax. Spread syntax "expands" an array into its elements, while rest syntax collects multiple elements and "condenses" them into a single element
- spread in array literals
    - a more powerful array literal
        - can be used to esily insert on array into another
    - copy an array
        - works similar to arr.slice()
    - a better way to concatenate arrays
- spread in object literals
    - The Rest/Spread Properties for ECMAScript proposal (ES2018) added spread properties to object literals. It copies own enumerable properties from a provided object onto a new object.
- only for iterables
    - Objects themselves are not iterable, but they become iterable when used in an Array, or with iterating functions such as map(), reduce(), and assign(). When merging 2 objects together with the spread operator, it is assumed another iterating function is used when the merging occurs.
## REST
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters
- The rest parameter syntax allows us to represent an indefinite number of arguments as an array
- Syntax
    - function f(a, b, ...theeArgs)
- Description
    - A function's last parameter can be prefixed with ... which will cause all remaining (user supplied) arguments to be placed within a "standard" JavaScript array.
    - difference between rest parameters and the arguments object
        - rest parameters are only the ones that haven't been given a separate name (i.e. formally defined in function expression), while the arguments object contains all arguments passed to the function
        - the arguments object is not a real array, while rest parameters are Array instances, meaning methods like sort, map, forEach or pop can be applied on it directly
        - the arguments object has additional functionality specific to itself (like the callee property)
    - from arguments to an array
        - Rest parameters have been introduced to reduce the boilerplate code that was induced by the arguments
    # video
    ## TDD where did it all go wrong?
    - growing resistence to TDD
    - the problem
        - if you stick artound somewhere long enough you get to see your mistakes
        - some early developers resisted it
            - some thought maybe just for juniors
        - we often write more test code than implementation code
            - it slows us down
            - refactoring leading to breaking tests
        - some aproaches like "programmer anarchy', 'spike and stabilize', and 'lean software development' want to drop TDD 
        - why is the 'duct-tape programmer' winning?
        - when we return to our tests- because they are broken we dont remember their intent
    - TDD is dead, long live testing 
        - where did it all go wrong?
        - TDD rebooted
            - read 'Test-Driven Development' by Kent Black
            - Avoid testing implementation details, test behaviors
                - many practice TDD by using 'adding a new method to a class' as the trigger to write a test
                    - this fails to capture the ethos of TDD
                    - adding a new class is not the trigger for writing tests
                    - the trigger is implementing a requirement
            - test the public API
                - what is the contract with the user?
                - what does the software offer?
                    - that is what you test
            - The SUT is not a class (system under test)
                - th SUT is the 'exports' from the module - it's facade
                - unit here means a module
            - do not write tests for implementation details - these change!
                - write them only against the stable contract of the API
                - the key is the refactoring step
            - The object of TDD is to test the behavior within the system
        - focusing on methods creates tests that are hard to maintain
            - we dont capture the behavior we wnt to preserve
            - we cant refactor easily because implementation details are exposed to tests
- Red-Green-Refactor
    - RED
        - write a little test that doesnt work
        and perhaps doesnt even compile at first
    - GREEN
        - make the test work quickly, committing whatever sins necessary in the process
    - REFACTOR
        - make it good code
    - make it run. Get to green as fast as possible
        - not just accepting sin
            - embrace it
    - the refactoring step is when we produce clean code
        - do not write new tests in this phase
    
    ## What the heck is an event loop anyway?
    - https://www.youtube.com/watch?v=8aGhZQkoFbQ
    - What is JavaScript?
        - Heap, stack, web APIs
        - single threaded call stack
            - one piece of code at a time
    - blocking
        - what happens when things are slow
    - concurrency and the event loop
        - one thing at a time, except, not really
    - event loop looks at stack and task queue
    - callbacks can be functions called by other functions or fucntions called asychronously
    - this video was helpful in understanding some of the more esoteric aspects of JS







                









