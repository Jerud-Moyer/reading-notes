## HTTP
- https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177
- HTTP stands for Hypertext Transfer Protocol. It's a stateless, application-layer protocol for communicating between distributed systems, and is the foundation of the modern web
- HTTP basics
  - HTTP allows for communication between a variety of hosts and clients, and supports a mixture of network configurations.
  - Communication between a host and a client occurs, via a request/response pair. The client initiates an HTTP request message, which is serviced through a HTTP response message in return
- URLS
  - At the heart of web communications is the request message, which are sent via Uniform Resource Locators (URLs).
- VERBS
  - GET: fetch an existing resource. The URL contains all the necessary information the server needs to locate and return the resource.
  - POST: create a new resource. POST requests usually carry a payload that specifies the data for the new resource
  - PUT: update an existing resource. The payload may contain the updated data for the resource.
  - DELETE: delete an existing resource.
  - HEAD: this is similar to GET, but without the message body. It's used to retrieve the server headers for a particular resource, generally to check if the resource has changed, via timestamps.
  - TRACE: used to retrieve the hops that a request takes to round trip from the server. Each intermediate proxy or gateway would inject its IP or DNS name into the Via header field. This can be used for diagnostic purposes.
  - OPTIONS: used to retrieve the server capabilities. On the client-side, it can be used to modify the request based on what the server can support.
- Status codes
  - With URLs and verbs, the client can initiate requests to the server. In return, the server responds with status codes and message payloads. The status code is important and tells the client how to interpret the server response
- request and response message formats
  - reques
    - url + verb
  - response stus code + message
- Using HTTP in webframeworks and libraries
  - ExpressJS
  - Because we are dealing with a server-side framework, there are two primary tasks when dealing with HTTP messages:
    - Read URL fragments and request headers.
    - Write response headers and body

### How DNS works
- https://howdns.works/ep1/
- a funny and informative comic on Domain Name System

### REST API
- https://howdns.works/ep1/
- an excellent video on REST API

### HTTP reference
- https://code-maze.com/the-http-reference/

### REST reference
- https://www.restapitutorial.com/lessons/httpmethods.html

