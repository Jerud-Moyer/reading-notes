## Scraping
### web scraping with JavaScript
- https://www.scrapingbee.com/blog/web-scraping-javascript/
- Understanding NodeJS
  - A runtime environment for JS
  - makes JS capable of running not only client side but also server side
  - uses event loop to perform multiple tasks
- HTTP clients: querying the web
  - HTTP clients are tools capable of sending a request to a server and then receive a response from it
  - Request
    - Request is one of the most widely used HTTP clients in the Javascript ecosystem, however, though currently, the author of the Request library has officially declared that it is deprecated. This does not mean it is unusable, quite a lot of libraries still use it, and it is every bit worth using. It is fairly simple to make an HTTP request with Request:
  - Axios
    - Axios is a promise-based HTTP client that runs both in the browser and NodeJS. If you use Typescript, then axios has you covered with built-in types. Making an HTTP request with Axios is straight forward, it ships with promise support by default as opposed to utilizing callbacks in Request:
  - Superagent
    - Much like Axios, Superagent is another robust HTTP client that has support for promises and the async/await syntax sugar. It has a fairly straightforward API like Axios, but Superagent has more dependencies and is less popular.
-  Regualr Expressions: The hard way
  - The simplest way to get started with web scraping without any dependencies is to use a bunch of regular expressions on the HTML string that you receive by querying a webpage using an HTTP client, but there is a big tradeoff. Regular Expressions aren't as flexible and quite a lot of people both professionals and amateurs struggle with writing the correct regular expression.
- Cheerio: core JQuery for traversing the DOM
  - Cheerio is an efficient and light library which allows you to use the rich and powerful API of JQuery on the server-side. If you have used JQuery previously then you will feel right at home with Cheerio, it removes all the DOM inconsistencies and browser-related features and exposes an efficient API to parse and manipulate the DOM.
- JSDOM: the DOM for Node
  - JSDOM is a pure Javascript implementation of the Document Object Model to be used in NodeJS, as mentioned previously the DOM is not available to Node, so JSDOM is the closest you can get. It more or less emulates the browser.
- Puppeteer: the headless browser
  - Puppeteer, as the name implies, allows you to manipulate the browser programmatically just like how a puppet would be manipulated by its puppeteer. It achieves this by providing a developer with a high-level API to control a headless version of Chrome by default and can be configured to run non-headless.
  *HOLY CRAP THIS IS AMAZING!*
- Nightmare: an alternative to Puppeteer
  - Nightmare is also a high-level browser automation library like Puppeteer, that uses Electron but is said to be roughly twice as faster as it's predecessor PhantomJS and more modern

  ## Document.quearySelector()
  - https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector
    - The Document method querySelector() returns the first Element within the document that matches the specified selector, or group of selectors. If no matches are found, null is returned.
  - Parameters
    - selectors
      - A DOMString containing one or more selectors to match. This string must be a valid CSS selector string; if it isn't, a SYNTAX_ERR exception is thrown.
  - return value
    - An HTMLElement object representing the first element in the document that matches the specified set of CSS selectors, or null is returned if there are no matches
    - If you need a list of all elements matching the specified selectors, you should use querySelectorAll() instead.
  - exceptions
    - SYNTAX_ERR
    The syntax of the specified selectors is invalid
  - escapimg special characters
    - To match against an ID or selectors that do not follow standard CSS syntax (by using a colon or space inappropriately, for example), you must escape the character with a backslash ("\"). As the backslash is also an escape character in JavaScript, if you are entering a literal string, you must escape it twice (once for the JavaScript string, and another time for querySelector()):

## Document.querySelectorAll()
- https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll
- parameters
  - A DOMString containing one or more selectors to match against. This string must be a valid CSS selector string; if it's not, a SyntaxError exception is thrown. See Locating DOM elements using selectors for more information about using selectors to identify elements. Multiple selectors may be specified by separating them using commas.
- return value
  - A non-live NodeList containing one Element object for each element that matches at least one of the specified selectors or an empty NodeList in case of no matches.
- exceptions
  - The syntax of the specified selectors string is not valid


