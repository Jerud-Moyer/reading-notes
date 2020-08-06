## ansycronous javaScript programming and callbacks
- asychronicity in programming languages
    - things can happen independant of main flow
 - js is synchronous by default  
 - callbacks
- alternatives to callbacks
    - Promises
    - Async/Await
### Understanding JS Promises
- how they work
    - when called the caller function for feedback from promise
    - which APIs use promises
        - battery API
        - Fetch API
        - Service Workers
- creating a promise
- consuming a promise
- you can chain promises
- handling errors
- orchestrating promises
### Asynchronous JS
- This is a huge list of guides
    - synchronous JS
    - asynchronous JS
        - used when fetching from APIs etc.
    - Async callbacks
        - functions specified as arguments whe calling a function which will start executing code in the background
### Using promises
- a promise is a returned object
- guarantees
    - cakllbacks will never be called before the completion of the current run
- Chaining
    - execute two or more asynchronous operations back to back where each subsequent operation starts when the previous op succeeds
- error propogation
- promise rejection events
- promise around old callback API
- composition
- timing
- nesting
- common mistakes
### Using Fetch
-  the promise returned from Fetch wont rejec=t on HTTP errors
### fetching 
### link broken

