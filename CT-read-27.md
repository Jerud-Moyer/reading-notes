## Understanding React 'setState'
- React components can, and often do, have state
### Workings of 'setSate()'
- setState() is the only legitimate way to update state after the initial state setup
- The reconciliation process is the way React updates the DOM, by making changes to the component based on the change in state
- When the request to setState() is triggered, React creates a new tree containing the reactive elements in the component (along with the updated state).
- This tree is used to figure out how the Search component’s UI should change in response to the state change by comparing it with the elements of the previous tree. React knows which changes to implement and will only update the parts of the DOM where necessary. This is why React is fast.
### Passing a function to 'setState()'
- this is how things are done!
### Access Previous Stae Using Updater
- When building React applications, there are times when you’ll want to calculate state based the component’s previous state. You cannot always trust this.state to hold the correct state immediately after calling setState(), as it is always equal to the state rendered on the screen.
- setState() should be treated asynchronously — in other words, do not always expect that the state has changed after calling setState()

## Lists and Keys
### Rendering multiple components
- You can build collections of elements and include them in JSX using curly braces
- we loop through the numbers array using the JavaScript map() function. We return a <li> element for each item. Finally, we assign the resulting array of elements to listItems
  - const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);

- We include the entire listItems array inside a <ul> element, and render it to the DOM:
- ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);

### Keys
- Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:
- The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:
- When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort:
### Extracting Compnents with keys
- Keys only make sense in the context of the surrounding array
- For example, if you extract a ListItem component, you should keep the key on the <ListItem /> elements in the array rather than on the <li> element in the ListItem itself
### Keys must be unique among siblings
- Keys used within arrays should be unique among their siblings. However they don’t need to be globally unique. We can use the same keys when we produce two different arrays:
### Embedding map() in JSX
- JSX allows embedding any expression in curly braces so we could inline the map() result

## Typechecking With PropTypes
- As your app grows, you can catch a lot of bugs with typechecking. For some applications, you can use JavaScript extensions like Flow or TypeScript to typecheck your whole application. But even if you don’t use those, React has some built-in typechecking abilities. To run typechecking on the props for a component, you can assign the special propTypes property
- PropTypes exports a range of validators that can be used to make sure the data you receive is valid. In this example, we’re using PropTypes.string. When an invalid value is provided for a prop, a warning will be shown in the JavaScript console. For performance reasons, propTypes is only checked in development mode.
### PropTypes
### Requireing Single Child
- With PropTypes.element you can specify that only a single child can be passed to a component as children
### Default Prop Values
- You can define default values for your props by assigning to the special defaultProps property
- if you are using a Babel transform like transform-class-properties , you can also declare defaultProps as static property within a React component class

## Components and Props
- Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.
- Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen
### Function and Class Components
- The simplest way to define a component is to write a JavaScript function:
- function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
- This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.
### Rendering a Component
- Previously, we only encountered React elements that represent DOM tags
- When React sees an element representing a user-defined component, it passes JSX attributes and children to this component as a single object. We call this object “props”.
### Composing Components
- Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail. A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.
### Extracting Componets
- Don’t be afraid to split components into smaller components
- Extracting components might seem like grunt work at first, but having a palette of reusable components pays off in larger apps. A good rule of thumb is that if a part of your UI is used several times (Button, Panel, Avatar), or is complex enough on its own (App, FeedStory, Comment), it is a good candidate to be extracted to a separate component.
### Props are read-only
- Whether you declare a component as a function or a class, it must never modify its own props. 
- All React components must act like pure functions with respect to their props.
### Handling Events
- Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences
  - React events are named using camelCase, rather than lowercase
  - With JSX you pass a function as the event handler, rather than a string.
- Another difference is that you cannot return false to prevent default behavior in React. You must call preventDefault explicitly
- When using React, you generally don’t need to call addEventListener to add listeners to a DOM element after it is created. Instead, just provide a listener when the element is initially rendered

## Snapshot Testing
- Snapshot tests are a very useful tool whenever you want to make sure your UI does not change unexpectedly
- A typical snapshot test case renders a UI component, takes a snapshot, then compares it to a reference snapshot file stored alongside the test. The test will fail if the two snapshots do not match: either the change is unexpected, or the reference snapshot needs to be updated to the new version of the UI component.
### Snapshot testing with Jest
- A similar approach can be taken when it comes to testing your React components. Instead of rendering the graphical UI, which would require building the entire app, you can use a test renderer to quickly generate a serializable value for your React tree.
### Updating Snapshots
- jest --updateSnapshot
### Interactive Snapshot Mode
- Failed snapshots can also be updated interactively in watch mode
- Once you enter Interactive Snapshot Mode, Jest will step you through the failed snapshots one test at a time and give you the opportunity to review the failed output.
### Inline Snapshots
- inline snapshots behave identically to external snapshots (.snap files), except the snapshot values are written automatically back into the source code. This means you can get the benefits of automatically generated snapshots without having to switch to an external file to make sure the correct value was written.
- Inline snapshots are powered by Prettier. To use inline snapshots you must have prettier installed in your project. Your Prettier configuration will be respected when writing to test files
- If you have prettier installed in a location where Jest can't find it, you can tell Jest how to find it using the "prettierPath" configuration property.
### Property Matchers
- Often there are fields in the object you want to snapshot which are generated (like IDs and Dates). If you try to snapshot these objects, they will force the snapshot to fail on every run:
- For these cases, Jest allows providing an asymmetric matcher for any property. These matchers are checked before the snapshot is written or tested, and then saved to the snapshot file instead of the received value:
### Best Practices
- Snapshots are a fantastic tool for identifying unexpected interface changes within your application – whether that interface is an API response, UI, logs, or error messages. As with any testing strategy, there are some best-practices you should be aware of, and guidelines you should follow, in order to use them effectively.
1. Treat Snapshots as code
  - Commit snapshots and review them as part of your regular code review process. This means treating snapshots as you would any other type of test or code in your project
  - Ensure that your snapshots are readable by keeping them focused, short, and by using tools that enforce these stylistic conventions
  - The goal is to make it easy to review snapshots in pull requests, and fight against the habit of regenerating snapshots when test suites fail instead of examining the root causes of their failure
2. Tests should be deterministic
  - Your tests should be deterministic. Running the same tests multiple times on a component that has not changed should produce the same results every time. You're responsible for making sure your generated snapshots do not include platform specific or other non-deterministic data.
3. Use descriptive snapshot names
  - Always strive to use descriptive test and/or snapshot names for snapshots. The best names describe the expected snapshot content. This makes it easier for reviewers to verify the snapshots during review, and for anyone to know whether or not an outdated snapshot is the correct behavior before updating.

## Introducing the React Testing Library
### The Problem
- You want to write maintainable tests for your React components. As a part of this goal, you want your tests to avoid including implementation details of your components and rather focus on making your tests give you the confidence for which they are intended. As part of this, you want your testbase to be maintainable in the long run so refactors of your components (changes to implementation but not functionality) don't break your tests and slow you and your team down
### The Solution
- The react-testing-library is a very light-weight solution for testing React components. It provides light utility functions on top of react-dom and react-dom/test-utils, in a way that encourages better testing practices.
- The utilities this library provides facilitate querying the DOM in the same way the user would. Finding form elements by their label text (just like a user would), finding links and buttons by their text (like a user would). It also exposes a recommended way to find elements by a data-testid as an "escape hatch" for elements where the text content and label do not make sense or is not practical.
### What the Library is Not
  1. A test runner or framework
  2. Specific to a testing framework (though we recommend Jest as our preference, the library works with any framework, and even in codesandbox!)
### High Level Overview API
- Simulate: a re-export from the Simulate utility from thereact-dom/test-utilsSimulateobject.
- wait: allows you to wait for a non-deterministic period of time in your tests. Normally you should mock out API requests or animations, but even if you're dealing with immediately resolved promises, you'll need your tests to wait for the next tick of the event loop and wait is really good for that. (Big shout out to Łukasz Gozda Gandecki who introduced this as a replacement for the (now deprecated)flushPromises API)
- render: This is the meat of the library. It's fairly simple. It creates a divwith document.createElement, then uses ReactDOM.render to render to that div.
- The render function returns the following objects and utilities:
  - container: The div your component was rendered to
  - unmount: A simple wrapper over ReactDOM.unmountComponentAtNodeto unmount your component (to facilitate easier testing of componentWillUnmount for example).
  - getByLabelText: Get a form control associated to a label
  - getByPlaceholderText: Placeholders aren't proper alternatives to labels, but if this makes more sense for your use case it's available.
  - getByText: Get any element by its text content.
  - getByAltText: Get an element (like an <img>) by it's alt attribute value.
  - getByTestId: Get an element by its data-testid attribute.







