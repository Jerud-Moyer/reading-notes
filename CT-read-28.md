## Archetectural Styles and Architectural Patterns
- In software engineering, an Architectural Pattern is a general and reusable solution to an occurring problem in a particular context. It is a recurring solution to a recurring problem.
- The purpose of Architectural Patterns is to understand how the major parts of the system fit together and how messages and data flow through the system.
- We can have multiple patterns in a single system to optimize each section of our code.

### Architectural Patterns vs. Design Patterns
- Architectural Patterns are similar to Design Patterns, but they have a different scope. In a few words, while Design Patterns impact a specific section of the code base, Architectural Patterns are high-level strategies that concern large-scale components, the global properties and mechanisms of a system.

### Styles and Patterns
- Until now, we have talked about Architectural Patterns, but we can also talk about Architectural Styles. The main difference is, an Architectural Pattern, as we said, is a way to solve a recurring architectural problem, while an Architectural Style is a name given to a recurrent Architectural Design. It doesn’t exist to solve a problem.

### Some Major Archetectural Patterns and Archetectual Patterns Styles
#### Layered
- This pattern is used to structure programs that can be decomposed into groups of subtasks. It partitions the concerns of the application into layers.
- Most of the time we have 4 layers
  1. Presentation layer or UI layer
  2. Application layer or Service layer
  3. Business logic layer or Domain layer
  4. Data access layer or Persistence layer
- The popular Model-View-Controller structure (MVC) is a Layered architecture. The Model layer is just above the database and it sometimes contains some business logic. The View is the top layer and corresponds to what the final user sees. The Controller layer is in the middle and it is in charge to send data from the Model to the View and vice versa.

#### Event-driven
- Also called EDA, this pattern organizes a system around the production, detection and consumption of events. Such a system consists of event Emitters and event Consumers. Emitters are decoupled from Consumers, which are also decoupled from each other
- An Emitter is an event source and only knows that the event has occurred. A Consumer needs to know an event has occurred and it has the responsibility of applying a reaction as soon as an event is presented. Sometimes, the reaction is not completely provided by a single Consumer that might forward the event to another component after it has filtered or transformed it.
- Event-driven architecture is easily adaptable to complex environments and can be easily extended when new event types appear. On the other hand, testing can be complex because interactions between modules can only be tested in a fully functioning system

#### Domain Driven design
- This Architectural Style, also known has DDD, is an object-oriented approach. Here, the idea is to design software based on the Business Domain, its elements and behaviors, and the relationships between them.
- The Business Domain is like a sphere of knowledge and activity around which the application logic revolves. It involves rules, processes and existing systems that need to be integrated into our solution. It is a set of classes that represent objects in the Business Model being implemented. The Business Model is the solution to the problem we are trying to solve. To organize and structure the knowledge of our problem, we use a Domain Model that should be accessible and understandable by everyone who is involved with the project. Domain Driven Design is about solving the problems of an organization. The Domain Model is about understanding and interpreting the important aspects of the given problems.
- A language is also structured around the Domain Model and used by all team members to connect all the activities of the team with the software. It is called Ubiquitous Language. We also refer to the Context to define the setting that determines the meaning of a statement
- Domain Driven Design is useful when we build complex software where the need for change is determined. We have to be careful and remember that DDD is not about how to code, but it is a way of looking at things

#### Pipes and filters
- This Architectural Style decomposes a task that performs complex processing into a series of separate elements that can be reused. In other words, it consists of any number of components, called Filters, that transform or filter data, before passing it to other components through connectors called Pipes.
- A Filter transforms the data it receives through Pipes with which it is connected. A Filter can have many input Pipes and many output Pipes.
- There are also two other components, the Pump, which is the data source, and the Sink, which is the final target.
- Pipes and Filters can be applied when the processing of our application can be broken down into a set of independent steps. It can also be useful when flexibility is required or when each step of the processing of the application have different scalability requirements.

#### Micro Services
- The goal of a Microservices architecture is, instead of building one single big monolithic application, to create several tiny programs
- Such an architecture requires every service to be completely independent of the others.

## Container and Presentation Pattern
- The container and presentation pattern splits code into two distinct places:
  1. containers : are stateful components that contain your business login
  2. presentations : are stateless components that present your data
### Containers
- Container components “[a]re concerned with how things work”1. In this role they manage state, fetch data from APIs, setup event handlers, and pass information to other components via props.
### Presentations
- Presentation components “[a]re concerned with how things look”1. In this role they receive props and use those props to render and style DOM.
### Directory Structure
- example here
  - https://alchemycodelab.github.io/fsjs-notes/05_react/patterns/container_presentation/

## Container Component Details
- https://alchemycodelab.github.io/fsjs-notes/05_react/patterns/container_presentation/container-details
- Container components are responsible for specifying how a section of our application works. They manage state, fetch data from apis, and setup event handlers.
### Class Containers
- When the Container/Presentation pattern first became popular all containers were class based components. At that time state and lifecycle methods were only available within class components. Since containers are responsible for managing state and fetching data (lifecycle methods) they were exclusively written as class components. This helped highlight the dichotomy between container components (classes) and presentational components (functions).
- Class container components are created by extending the react Component class
#### Initializing State
- Class based container components can initialize state in two ways: 
  1.  class properties; inside a constructor.
    - Using class properties to initialize state is a newer (and maybe cleaner) way to initialize state:
  2. before class properties were proposed (class properties are new to JavaScript) state was initialized in a constructor:
#### Setting State
- To set state inside a class based container component use this.setState.
- Independent state changes (changes that don’t rely on knowing what the current state is) are done by passing an object to this.setState
- this.setState merges your update into the previous state ({ …oldState, …newState }) and initiates a re-render
- Dependent state changes (changes that do rely on knowing what the current state is) are done by passing a function to this.setState. That function receives current state and returns an object for update.
#### Fetching Data
- Class based container components can fetch data inside lifecycle methods (NOTE: you should fetch data with a service function). If your component always needs to fetch some data, you can use componentDidMount to fetch your data right as your component is mounted.
#### Initializing State
- To initialize state use the useState hook. When using useState each piece of state should be a JavaScript primitive (string, number, boolean, null, undefined) or a simple array. You can use multiple useState hooks in a single component.
#### Setting State
- In order to update state we use the second item in the array returned by useState
- State changes that do not rely on the previous state, independent state changes, can be done by passing a new value to setSomeState
- State changes that do rely on the previous state, dependent state changes, can be done by passing a function to setSomeState. The function will receive the current value for someState and will return the new value for someState.
#### Fetching Data
- Fetching data and setting the fetched data in state is considered a side effect. This is because by fetching data we are changing the state of our application.
- In order to handle side effects react provides the useEffect hook. useEffect takes two arguments: 
  1. a function that preforms the side effect; 
  2. an array of values that, when changed, trigger the side effect.
### Containers as Hooks
- Containers can also be written as custom hooks, rather than as components (container hooks vs container components).

## Presentation Component Details
- Presentation components are responsible for specifying how a section of our page looks. They create DOM and styles.
### Creating a Presentational Component
- Presentational components are written as functional components. They return the markup that is going to get rendered to the DOM.
- When we pass props into our component we should use the prop-types package to specify the props our component receives. This gives us convenient warning messages if we forget to pass a prop or pass a prop with the wrong type.
## Functional vs Class Components in React
- https://medium.com/@Zwenza/functional-vs-class-components-in-react-231e3fbd7108
### Differences between functional and claas components
#### Syntax
- The most obvious one difference is the syntax. A functional component is just a plain JavaScript function which accepts props as an argument and returns a React element
- A class component requires you to extend from React.Component and create a render function which returns a React element. This requires more code but will also give you some benefits 
#### State
- Because a functional component is just a plain JavaScript function, you cannot use setState() in your component. That’s the reason why they also get called functional stateless components. So everytime you see a functional component you can be sure that this particular component doesn’t have its own state.
- If you need a state in your component you will either need to create a class component or you lift the state up to the parent component and pass it down the functional component via props.
#### Lifecycle Hooks
- Another feature which you cannot use in functional components are lifecycle hooks. The reason is the same like for state, all lifecycle hooks are coming from the React.Component which you extend from in class components.

#### The above two items have changed withthe react 16.8 hooks update!

## CONDITIONAL RENDERING
- https://reactjs.org/docs/conditional-rendering.html
- in React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application
### Element Variables
- You can use variables to store elements. This can help you conditionally render a part of the component while the rest of the output doesn’t change
### Inline if with logical && operator
- You may embed expressions in JSX by wrapping them in curly braces. This includes the JavaScript logical && operator. It can be handy for conditionally including an element:
- It works because in JavaScript, true && expression always evaluates to expression, and false && expression always evaluates to false.
- Therefore, if the condition is true, the element right after && will appear in the output. If it is false, React will ignore and skip it.
### Inline If-Else with Conditional Operator
- Another method for conditionally rendering elements inline is to use the JavaScript conditional operator condition ? true : false.
### Preventing Component from Rendering
- In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return null instead of its render output.