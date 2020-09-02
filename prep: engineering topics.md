## Quantity trumps Quality
- an interesting take that quantity essentially begets quality. That it's better to be always working on new iterations of something and learn from your mistakes than to labor over one perfect thing.

## Clean Code
- http://ptgmedia.pearsoncmg.com/images/9780132350884/samplepages/9780132350884.pdf

- "Writing clean code is what you must do in order to call yourself a professional.
There is no reasonable excuse for doing anything less than your best."

### foreward
- TPM = Total Productive Maintenance

- 5S philosophy
    - • Seiri, or organization (think “sort” in English). Knowing where things are—using
approaches such as suitable naming—is crucial. You think naming identifiers isn’t
important? Read on in the following chapters.

- • Seiton, or tidiness (think “systematize” in English). There is an old American saying:
A place for everything, and everything in its place. A piece of code should be where
you expect to find it—and, if not, you should re-factor to get it there.

- • Seiso, or cleaning (think “shine” in English): Keep the workplace free of hanging
wires, grease, scraps, and waste. What do the authors here say about littering your
code with comments and commented-out code lines that capture history or wishes for
the future? Get rid of them.

- • Seiketsu, or standardization: The group agrees about how to keep the workplace clean.
Do you think this book says anything about having a consistent coding style and set of
practices within the group? Where do those standards come from? Read on.

- • Shutsuke, or discipline (self-discipline). This means having the discipline to follow the
practices and to frequently reflect on one’s work and be willing to change.

### Chapter 1 Clean Code
 - There will be code
    - some think that code is going tjhe way of the DODO
        - this is nonsense! WE WILL ALWAYS NEED CODE!
- Bad code
    - bad code early on can sink a company
    - weve all made a mess and decided to clean it up 'later'
        - LeBlac's law: later = never
- The total cost of owning a mess
    - problems build as new features are added that conflict with old bad code
    - the problems only compound
- The grand redesign in the sky
    - management relents and agrees to redesign
        - redesign cant be deployed until it can do everything original design did
        - redesign takes so long that by the time it is deployed a new redesign is needed.
- Attitude
    - it os easy to blame managers, marketers, deadlines, etc.
        - the truth is that iot is *our* fault as programmers
        - we tell the magers, who set deadlines, whats up
        - we plan the projects
        - it's unproffessional to bend to the will of managers who don't understand the risks of making a mess
    - The Primal Conundrum
        - The only way to be fast is to take it slow and write clean code.
    - The Art of Clean Code
        - It's no good trying to write clean code if you don't know what it means for code to be clean
        -  being able to recognize clean code
        from dirty code does not mean that we know how to write clean code!
        - writing clean code requires a use of a myriad of little techniques aquired from a sense of 'cleanliness'
        - a programmer needs 'code-sense' to noit just see bad code, but to know hoe to fix it.
    - What is Clean Code?
        - Bjarne Stroustrup, inventor of C++
        and author of The C++ Programming Language
        - elegant
        - efficient
        - Grady Booch, author of Object Oriented Analysis and Design with Applications
            - simple and direct
            - reads like well written prose
            - never obscures the designers intent
        - “Big” Dave Thomas, founder of OTI, godfather of the Eclipse strategy 
            - 'Clean code can be read and enhanced by a developer other than it's original author'
            - it has unit and acceptance tests
            - code should be literate
        - Michael Feathers, author of Working Effectively with Legacy Code
            - 'Clean code always looks like it written by someone who cares'
        - Ron Jeffries, author of Extreme Programming Installed and Extreme Programming Adventures in C#
            - 'In recent years I begin, and nearly end, with Beck’s rules of simple code. In priority order, simple code:
                - Runs all tests;
                - Contains no duplication;
                - Expresses all the design ideas that are in the system;
                - Minimizes the amount of entities such as classes, methods, functions and the like.
        - Ward Cunningham, inventor of Wiki,inventor of Fit, coinventor of eXtreme Programming. Motive force behind Design Patterns. Smalltalk and OO thought leader. The godfather of all those who care about code
            - 'You know you are working on clean code when each routine you read turns out to be pretty much what you expected.'
        - The Boy Scout Rule
            - It's not enough to write the code well, the code has to be kept clean *over time*
            - *leave the campground cleaner than you found it*

## Red, Green, Refactor
- https://www.codecademy.com/articles/tdd-red-green-refactor
- The red, green, refactor approach helps developers compartmentalize their focus into three phases:
    - Red - think about *what* you want to develop
    - Green - think about *how* to make your tests pass
    - Refactor - think about *how* to improve your existing implementation
- RED
    - the starting point
    - the purpose of this phase is to write a test that informs the implementation of the feature
- GREEN
    - the phase where you implement the code to make your test pass
    - the goal is to find a solution, without worrying about the optimizing your implementation.
- REFACTOR
    - think about how to implement your code better or more efficiently
    
## The Cycles of TDD
- **Second by Second** _nano-cycle_; The three laws of TDD
    - You must write a failing test before you write any production code
    - You must not write more of a test than is sufficient to fail, or fail to compile
    - You must not write more production code than is sufficuent to make currently failing test pass
- **Minute by Minute** _micro-cycle_: Red-Green_refactor
    - This cycle is typically executed once for every complete unit test, or once every dozen or so cycles of the three laws. The rules of this cycle are simple.
        - Create a Unit test that fails
        - Write production code that makes that test pass
        - Clean up the mess you just made
- **Decaminute by Decaminute** _milli-cycle_: Specific/Generic
    - as the tests get more specific the code gets more generic
    








