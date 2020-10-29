# Composition vs Inheritance
- https://reactjs.org/docs/composition-vs-inheritance.html
- React has a powerful composition model, and we recommend using composition instead of inheritance to reuse code between components.
## Containment
- https://reactjs.org/docs/composition-vs-inheritance.html
- We recommend that such components use the special children prop to pass children elements directly into their output:
## Specialization
- Sometimes we think about components as being “special cases” of other components.
- In React, this is also achieved by composition, where a more “specific” component renders a more “generic” one and configures it with props
# So What About Inheritance
- At Facebook, we use React in thousands of components, and we haven’t found any use cases where we would recommend creating component inheritance hierarchies.
- Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Remember that components may accept arbitrary props, including primitive values, React elements, or functions.
- If you want to reuse non-UI functionality between components, we suggest extracting it into a separate JavaScript module. The components may import it and use that function, object, or a class, without extending it.
