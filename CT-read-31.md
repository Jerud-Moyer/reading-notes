# Building Your Own Hooks
- https://reactjs.org/docs/hooks-custom.html
- Building your own Hooks lets you extract component logic into reusable functions.
## Extracting a custom hook
- When we want to share logic between two JavaScript functions, we extract it to a third function. Both components and Hooks are functions, so this works for them too!
- Unlike a React component, a custom Hook doesn’t need to have a specific signature. We can decide what it takes as arguments, and what, if anything, it should return. In other words, it’s just like a normal function. Its name should always start with use so that you can tell at a glance that the rules of Hooks apply to it.
## using a custom hook
- Custom Hooks are a convention that naturally follows from the design of Hooks, rather than a React feature
- Do I have to name my custom Hooks starting with “use”? Please do. This convention is very important. Without it, we wouldn’t be able to automatically check for violations of rules of Hooks because we couldn’t tell if a certain function contains calls to Hooks inside of it
- Do two components using the same Hook share state? No. Custom Hooks are a mechanism to reuse stateful logic (such as setting up a subscription and remembering the current value), but every time you use a custom Hook, all state and effects inside of it are fully isolated
- How does a custom Hook get isolated state? Each call to a Hook gets isolated state.

### Tip: Pass Information Between Hooks
- Since Hooks are functions, we can pass information between them.

# Rules of Hooks
-  https://reactjs.org/docs/hooks-rules.html
### Only call hooks at the top level
- Don’t call Hooks inside loops, conditions, or nested functions.
### Only Call Hooks from React Functions
- Don’t call Hooks from regular JavaScript functions.
### ESLint Plugin
- We released an ESLint plugin called eslint-plugin-react-hooks that enforces these two rules. 
### Explanation
- we can use multiple State or Effect Hooks in a single component
-  React relies on the order in which Hooks are called.

# The Guide to Learning React Hooks
- https://www.telerik.com/kendo-react-ui/react-hooks-guide/#toc-custom-react-hooks
## What You Should Knpw About React Hooks
- First released in October of 2018, the React hook APIs provide an alternative to writing class-based components, and offer an alternative approach to state management and lifecycle methods. Hooks bring to functional components the things we once were only able to do with classes, like being able to work with React local state, effects and context through useState, useEffect and useContext.
### So how do we use hooks?
### The Benefits of using hooks
- Hooks do trim the fat. It cuts down and makes our code more readable, concise and clear.
### Five Important Rules for Hooks
  1. Never call Hooks from inside a loop, condition or nested function
  2. Hooks should sit at the top-level of your component
  3. Only call Hooks from React functional components
  4. Never call a Hook from a regular function
  5. Hooks can call other Hooks
### Class vs Functional Counter Component Example with useState
- Call useState and useEffect as Much as You Want
### Hooks for Context
- useContext
- we can pass the data needed (as an object) into a <provider> component through its value attribute. By doing this, we allow any component and its child components to share this data.
### Updating state with a provider
### Hooks for Reducers
- React Hooks educer is similar to JS array prototype reducer
- our reducer receives a state and action as arguments, the state gets reduced (accumulated) based on the action.type, and we return our new state after running the instructions that match the case for that specific action.type.
### Custom React Hooks
- Hooks are just functions! Anything that is a function can become a Hook. I feel that the documentation on the ReactJS docs site is not simple enough. 
### revisiting the Hook effect
- Hooks, and specifically useEffect, now allow you to split up code based on what it's doing rather than what lifecycle method it's in. When we only had classes and lifecycle methods, we would sometimes have to mix concerns. Now, using multiple useEffect methods, React can apply each effect in the order they are specified. This is a huge benefit for organizing code in your application.
### Creating a custom Hook


# 10 React Hooks you should have in your toolbox
- https://blog.bitsrc.io/10-react-custom-hooks-you-should-have-in-your-toolbox-aa27d3f5564d
1. useArray hook
- installation
  - yarn add react-hanger
- import
  - import { useArray } from 'react-hanger'
2. react-use-form-state-hook
- installation
  - npm i react-use-form-state
3. rect-fetch-hook
- installation
  - npm i react-fetch-hook
4. useMedia Hook
5. react-usePortal Hook
- installation
  - yarn add react-useportal
6. react-firebase-hooks
- installation
  - npm i react-firebase-hooks
7. use-onClickOutside hook
8. useIntersectionObserver Hook
- installation
  - npm i react-use-intersection-observer
9. use-location hook
10. use-redux hook
- installation
  - yarn add use-redux
