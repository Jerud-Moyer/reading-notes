## Clean Code
### chapter2

- hmm doesn't seem to be there. will check later

## Array Methods
- 1. forEach()
    - This method can help you to loop over array's items.
- 2. includes()
    - This ,method checks if an array includes the item passed in the method.
- 3. filter()
    - This method can create a new array with only elements pass that pass the condition inside the provided function.
- 4. map()
    - This method creates a new array by calling the provided function in every element
- 5. reduce()
    - this method applies a function against an accumulater and each element in the array to reduce it to a single value
- 6. some()
    - this method checks to see if any items in array pass the condition. if even one does, it returns true.
- 7. every()
    - same as sum except all items must passs to return true
- 8. sort()
    - this method is used to arrange array items in ascending or descending order
- 9. Array.from()
    - will turn strings into arrays
- 10. Array.of()
    - will create an array from a series of arguments passed to it

### Array method cheat sheet
- https://jrsinclair.com/javascript-array-methods-cheat-sheet- 
- signed up for my cheet sheet!

### Class syntax
- the 'class' syntax
    - class MyClass {
  // class methods
  constructor() { ... }
  method1() { ... }
  method2() { ... }
  method3() { ... }
  ...
}
- use new MyClass() to create a new object with all the listed methods
    - a new object is created
    - the constructor runs with the given argument and assignd the this.name to it
- what is a class?
    - a class is a special type of function
- Not just syntactic sugar
    - class is labelled by a special internal property
        - [[FunctionKind]]:"classConstructor"
- class expression
- getters and setters
    - Just like literal objects, classes may include getters/setters, computed properties etc.

### Classes
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
- Defining classes
    - Classes are in fact "special functions", and just as you can define function expressions and function declarations, the class syntax has two components: class expressions and class declarations.
- class declarations
    - One way to define a class is using a class declaration. To declare a class, you use the class keyword with the name of the class 
    - hoisting
        - An important difference between function declarations and class declarations is that function declarations are hoisted and class declarations are not. You first need to declare your class and then access it,
- class expressions
    - A class expression is another way to define a class. Class expressions can be named or unnamed. The name given to a named class expression is local to the class's body. (it can be retrieved through the class's (not an instance's) name property, though).
- class body and method definitions
    - The body of a class is the part that is in curly brackets {}. This is where you define class members, such as methods or constructor
    - strict mode
        - The body of a class is executed in strict mode, i.e., code written here is subject to stricter syntax for increased performance, some otherwise silent errors will be thrown, and certain keywords are reserved for future versions of ECMAScript.
    - constructor
        - The constructor method is a special method for creating and initializing an object created with a class. There can only be one special method with the name "constructor" in a class. A SyntaxError will be thrown if the class contains more than one occurrence of a constructor method. A constructor can use the super keyword to call the constructor of the super class.
    - prototype methods
    - static methods
        - The static keyword defines a static method for a class. Static methods are called without instantiating their class and cannot be called through a class instance. Static methods are often used to create utility functions for an application.
    - binding _this_ with proyotype and static methods
        - When a static or prototype method is called without a value for this, such as by assigning a variable to the method and then calling it, the this value will be undefined inside the method. This behavior will be the same even if the "use strict" directive isn't present, because code within the class body's syntactic boundary is always executed in strict mode
    - Sub-classing with _extends_
        - The extends keyword is used in class declarations to create a class as a child of another class
        - If there is a constructor present in the subclass, it needs to first call super() before using "this"
    - species
    - super class calls with _super_
        - The super keyword is used to call corresponding methods of super class.
    - mix-ins
        - Abstract subclasses or mix-ins are templates for classes. An ECMAScript class can only have a single superclass, so multiple inheritance from tooling classes, for example, is not possible. The functionality must be provided by the superclass.
### MVC Arcitecture tutorial
- What is MVC Architechture?
- MVC separates concerns into 3 buckets
    1. Model
        - data
        - often a database
    2. View
        - GUI
        - view of the data, like a chart, diagram, table or form
    3. Controller
        - brains
        - connects the model and view. converts inputs from the view to demands to retrieve/update data in the model
- Benefits of MVC
    - many here, popular in web apps, responsibilities divided between client and server, heklpful for planning etc.
    - separate, loosely coupled concerns allow for separate teams to get the work done

## video
### MVC explained in 4 minutes
- https://www.youtube.com/watch?v=DUg2SWWK18I
- this was a very informative, short video on MVC


