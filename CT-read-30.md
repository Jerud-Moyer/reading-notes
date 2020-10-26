## Hooks at a Glance
- https://reactjs.org/docs/hooks-overview.html
- Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class
### state hook
- useStae is a hook that you can call inside a function component to preserve the state between rerenders.
- useState returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler or somewhere else
- The only argument to useState is the initial state.
#### Dexclaring multiple stste values
- You can use the State Hook more than once in a single component:
- The array destructuring syntax lets us give different names to the state variables we declared by calling useState. These names aren’t a part of the useState API. Instead, React assumes that if you call useState many times, you do it in the same order during every render.
#### Bit what is a hook?
- Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes. 
- React provides a few built-in Hooks like useState. You can also create your own Hooks to reuse stateful behavior between different components.
### Effect hook
- The Effect Hook, useEffect, adds the ability to perform side effects from a function component. It serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes,
- When you call useEffect, you’re telling React to run your “effect” function after flushing changes to the DOM.
- Effects are declared inside the component so they have access to its props and state. By default, React runs the effects after every render — including the first render. 
- Hooks let you organize side effects in a component by what pieces are related 
### Rules of hooks
- Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.
- Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions. 
### Building your own hooks
- Sometimes, we want to reuse some stateful logic between components. Traditionally, there were two popular solutions to this problem: higher-order components and render props.
- The state of each component is completely independent. Hooks are a way to reuse stateful logic, not state itself. 
### Other hooks
- useContext lets you subscribe to React context without introducing nesting:
- useReducer lets you manage local state of complex components with a reducer

## Using the State Hook
- https://reactjs.org/docs/hooks-state.html
- Hooks don’t work inside classes. But you can use them instead of writing classes.
### What is a hook?
- A Hook is a special function that lets you “hook into” React features. For example, useState is a Hook that lets you add React state to function components.
### When would I use a hook?
- If you write a function component and realize you need to add some state to it, previously you had to convert it to a class. Now you can use a Hook inside the existing function component. 
### Declarting a state variable
- In a function component, we have no this, so we can’t assign or read this.state. Instead, we call the useState Hook directly inside our component:
#### What does calling useState do?
- The only argument to the useState() Hook is the initial state. Unlike with classes, the state doesn’t have to be an object.
#### what does useState return?
- It returns a pair of values: the current state and a function that updates it.

## Using the Effect Hook
- https://reactjs.org/docs/hooks-effect.html
- The Effect Hook lets you perform side effects in function components:
- Data fetching, setting up a subscription, and manually changing the DOM in React components are all examples of side effects
### Effects without cleanup
- Sometimes, we want to run some additional code after React has updated the DOM. Network requests, manual DOM mutations, and logging are common examples of effects that don’t require a cleanup. We say that because we can run them and immediately forget about them. Let’s compare how classes and Hooks let us express such side effects.
#### what does useEffect do?
-  By using this Hook, you tell React that your component needs to do something after render. React will remember the function you passed (we’ll refer to it as our “effect”), and call it later after performing the DOM updates. In this effect, we set the document title, but we could also perform data fetching or call some other imperative API.
#### Why is useEffect called inside a component?
- Placing useEffect inside the component lets us access the count state variable (or any props) right from the effect. We don’t need a special API to read it — it’s already in the function scope. Hooks embrace JavaScript closures and avoid introducing React-specific APIs where JavaScript already provides a solution.
#### Does useEffect run after every render?
- Yes! By default, it runs both after the first render and after every update.
- Instead of thinking in terms of “mounting” and “updating”, you might find it easier to think that effects happen “after render”. React guarantees the DOM has been updated by the time it runs the effects.

### Effects with cleanup
- Earlier, we looked at how to express side effects that don’t require any cleanup. However, some effects do. For example, we might want to set up a subscription to some external data source. In that case, it is important to clean up so that we don’t introduce a memory leak! Let’s compare how we can do it with classes and with Hooks.

## Hooks API Reference
- https://reactjs.org/docs/hooks-reference.html
