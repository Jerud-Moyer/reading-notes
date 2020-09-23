## User Modeling
- use separarated model for private encrypted user info.
- user models that have sensitive data should never be sent to client applications
## Cryptography
- The science which studies methiods for encoding messages so they can be read only by a person who knows the secret information required for decoding, called the key.
## Cypher algorithms
- A Cryptographic Cypher Algorithm takes a piece of data and a key and produces encrypted data. Later the encrypted data can be reversed into the original data by decrypting it using the same key.
- User tokens can be created by associated a random unique string (tokenSeed) with a user account and, in turn, encrypting the tokenSeed with a secret key that only the server knows.
## Basic Authorization
- Basic Authorization is a common method used to send a username and password in an HTTP request. The username and password are joined with a ‘:’ then “base64 encoded” and placed after the string ‘Basic ‘. The resulting string is set to the value of an Authorization header.
- Basic Authorization reference
  - https://en.wikipedia.org/wiki/Basic_access_authentication

### Introduction to JSON web tokens
- https://canvas.instructure.com/courses/2231818/discussion_topics/9699687
- JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object

### Authentication Cheetsheet
- https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html

### noide.bcrypt.js
- https://www.npmjs.com/package/bcrypt