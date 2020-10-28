# Context
- https://reactjs.org/docs/context.html
- Context provides a way to pass data through the component tree without having to pass props down manually at every level
## When to use Context
- Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.
## Before you use Context
- Context is primarily used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult
- If you only want to avoid passing some props through many levels, component composition is often a simpler solution than context
## API
### React.createContext
- Creates a Context object. When React renders a component that subscribes to this Context object it will read the current context value from the closest matching Provider above it in the tree.
- The defaultValue argument is only used when a component does not have a matching Provider above it in the tree. This can be helpful for testing components in isolation without wrapping them. Note: passing undefined as a Provider value does not cause consuming components to use defaultValue.
### Context.provider
- Every Context object comes with a Provider React component that allows consuming components to subscribe to context changes.
- The Provider component accepts a value prop to be passed to consuming components that are descendants of this Provider. One Provider can be connected to many consumers. Providers can be nested to override values deeper within the tree.
- The Provider component accepts a value prop to be passed to consuming components that are descendants of this Provider. One Provider can be connected to many consumers. Providers can be nested to override values deeper within the tree.
- Changes are determined by comparing the new and old values using the same algorithm as Object.is.
### Class.contextType
- The contextType property on a class can be assigned a Context object created by React.createContext(). This lets you consume the nearest current value of that Context type using this.context. You can reference this in any of the lifecycle methods including the render function
### Context.consumer
- A React component that subscribes to context changes. This lets you subscribe to a context within a function component.
- Requires a function as a child. The function receives the current context value and returns a React node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree. If there is no Provider for this context above, the value argument will be equal to the defaultValue that was passed to createContext().
### Context.displayName
- Context object accepts a displayName string property. React DevTools uses this string to determine what to display for the context.
#### examples for reference

