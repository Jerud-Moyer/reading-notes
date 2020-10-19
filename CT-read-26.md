## An intro I to Webpack: what it is and hoe to use it is
### the problem
- more modern websites began to have many, many for files than the sites of old
- there alsio began to be a gap between the code developers wre writing and that which browsers could interpret
- the so lution: Webpack, a static module bundler.

### how was Webpack the answer?
-  Webpack goes through your package and creates what it calls a dependency graph which consists of various modules which your webapp would require to function as expected. Then, depending on this graph, it creates a new package which consists of the very bare minimum number of files required, often just a single bundle.js file which can be plugged in to the html file easily and used for the application.

### tutorial walk-through

## Webpack Concepts
- At its core, webpack is a static module bundler for modern JavaScript applications. When webpack processes your application, it internally builds a dependency graph which maps every module your project needs and generates one or more bundles.
### entry
- An entry point indicates which module webpack should use to begin building out its internal dependency graph. webpack will figure out which other modules and libraries that entry point depends on (directly and indirectly)
- By default its value is ./src/index.js, but you can specify a different (or multiple entry points) by setting an entry property in the webpack configuration
### output
- The output property tells webpack where to emit the bundles it creates and how to name these files. It defaults to ./dist/main.js for the main output file and to the ./dist folder for any other generated file.
- You can configure this part of the process by specifying an output field in your configuration:
webpack.config.js
### Loaders
- Out of the box, webpack only understands JavaScript and JSON files. Loaders allow webpack to process other types of files and convert them into valid modules that can be consumed by your application and added to the dependency graph.
- loaders have two properties in your webpack configuration:
  1. The test property identifies which file or files should be transformed.
  2. The use property indicates which loader should be used to do the transforming.
### Plugins
- While loaders are used to transform certain types of modules, plugins can be leveraged to perform a wider range of tasks like bundle optimization, asset management and injection of environment variables.
- In order to use a plugin, you need to require() it and add it to the plugins array. Most plugins are customizable through options. Since you can use a plugin multiple times in a configuration for different purposes, you need to create an instance of it by calling it with the new operator.
### mode
- By setting the mode parameter to either development, production or none, you can enable webpack's built-in optimizations that correspond to each environment. The default value is production.
### Browser Compatability
- webpack supports all browsers that are ES5-compliant (IE8 and below are not supported). webpack needs Promise for import() and require.ensure(). If you want to support older browsers, you will need to load a polyfill before using these expressions.

## Rendering Elements
### Rendering an Element into the DOM
- code example
  - const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
### Updating the Rendered Element
- React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time
### React Only Updates What's Necessary
- React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.

## Hello World
- react docs
  - https://reactjs.org/docs/hello-world.html

## Introducing JSX
- JSX is a syntax extension to JavaScript
### Why JSX
- React doesn’t require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages






  
