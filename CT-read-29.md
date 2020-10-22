## Model-View-Controller
- https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model–view–controller (usually known as MVC) is a software design pattern[1] commonly used for developing user interfaces that divides the related program logic into three interconnected elements. This is done to separate internal representations of information from the ways information is presented to and accepted from the user.
- Traditionally used for desktop graphical user interfaces (GUIs), this pattern has become popular for designing web applications.[4] Popular programming languages like JavaScript, Python, Ruby, PHP, Java, C#, and Swift have MVC frameworks that are used for web or mobile application development straight out of the box
### Compnents
#### Model
- The central component of the pattern. It is the application's dynamic data structure, independent of the user interface.[5] It directly manages the data, logic and rules of the application.
#### View
- Any representation of information such as a chart, diagram or table. Multiple views of the same information are possible, such as a bar chart for management and a tabular view for accountants
#### Controller
- Accepts input and converts it to commands for the model or view
##### In addition to dividing the application into these components, the model–view–controller design defines the interactions between them
- The model is responsible for managing the data of the application. It receives user input from the controller.
- The view means presentation of the model in a particular format.
- The controller responds to the user input and performs interactions on the data model objects. The controller receives the input, optionally validates it and then passes the input to the model.

## The 4 layers of single page apps you need to know
- https://hackernoon.com/architecting-single-page-applications-b842ea633c2e
### View
### Application Services
### Domain
### Store
 
## Model View Controller Pattern for React
- https://blog.testdouble.com/posts/2019-11-04-react-mvc/
- Probably the widest quoted pattern in UI development is Model View Controller (MVC)—it’s also the most misquoted.
  — Martin Fowler
- The guiding light of Model View Controller (MVC) is separating presentation from domain. Why is that important to do? Our application’s “domain” is where we model our perception of the problem and its solution. By making this code separate—without reference to any UI—it could be modeled more correctly, tested more deeply, and presented more numerously.
- The most important part of MVC is the model. In truth, you aren’t doing MVC until you have a model
### Implementing MVC patterns in React
1. A Presentation Layer of Controller and View React Components
2. A UI-Agnostic Data Model
#### Pillar 1: Presentation layer of controller and view React components
- This pillar is about separating components by their role regarding access/knowledge of domain objects and logic.

## Reconciliation
### Motivation
- When you use React, at a single point in time you can think of the render() function as creating a tree of React elements. On the next state or props update, that render() function will return a different tree of React elements. React then needs to figure out how to efficiently update the UI to match the most recent tree
### The Diffing Algoirithm
- When diffing two trees, React first compares the two root elements. The behavior is different depending on the types of the root elements.
#### Elements of a different type
- Whenever the root elements have different types, React will tear down the old tree and build the new tree from scratch.
-  When tearing down a tree, old DOM nodes are destroyed. Component instances receive componentWillUnmount(). When building up a new tree, new DOM nodes are inserted into the DOM. Component instances receive componentWillMount() and then componentDidMount(). Any state associated with the old tree is lost.
#### Dom elements of the same type
- When comparing two React DOM elements of the same type, React looks at the attributes of both, keeps the same underlying DOM node, and only updates the changed attributes. For example:
#### Component elements of the same type
- When a component updates, the instance stays the same, so that state is maintained across renders. React updates the props of the underlying component instance to match the new element, and calls componentWillReceiveProps() and componentWillUpdate() on the underlying instance.
#### Recursing on childern
- By default, when recursing on the children of a DOM node, React just iterates over both lists of children at the same time and generates a mutation whenever there’s a difference.
#### Keys
- In order to solve this issue, React supports a key attribute. When children have keys, React uses the key to match children in the original tree with children in the subsequent tree. For example, adding a key to our inefficient example above can make the tree conversion efficient:




