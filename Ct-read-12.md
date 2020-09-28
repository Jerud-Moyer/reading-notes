## Why you should use BCrypt to hash passwords
### Hashed password solutions fall short
- Many password solutions simply are not good enough and put your data and resources at risk
- plain text passwords
  - a plain text password makes use of only letters. Should a hacker gain access to passwords such as these, they can easily pose as a user on your system
- One way hash
  - With a one-way hash password, a server does not store plain text passwords to authenticate a user. Here, a password has a hashing algorithm applied to it to make it more secure
  - While in theory, this is a far better password solution, hackers have found ways around this system as the algorithm used is not exactly a one-way option at all. In fact, hackers can just continue to guess passwords until they gain access to your resources
- Salting the password
  - ‘salt’ adds a very long string of bytes to the password
  - but if a hacker has access to your source code, they will easily be able to find the ‘salt’ string for passwords
- Random 'salt' for each user
  - This will increase encryption significantly as hackers will have to try to find a password for a single user at a time. Again, even though it means they will have to spend more time cracking the passwords for multiple users, they will still be able to gain access to your resources. It just takes longer
### The BCrypt solution
-  With Key Factor changes, the hash output can be influenced. In this way, BCrypt remains extremely resistant to hacks, especially a type of password cracking called rainbow table
- This Key Factor will continue to be a key feature as computers become more powerful in the future. Why? Well, because it compensates for these powerful computers and slows down hashing speed significantly. Ultimately slowing down the cracking process until it’s no longer a viable strategy

## Hashing in Action: Understanding BCrypt
- adding 'salt' to hashing makes a double whammy of security excellence
- There are plenty of cryptographic functions to choose from such as the SHA2 family and the SHA-3 family. However, one design problem with the SHA families is that they were designed to be computationally fast. How fast a cryptographic function can calculate a hash has an immediate and significant bearing on how safe the password is.
### Motivation behind bcryp
- Technology changes fast. Increasing the speed and power of computers can benefit both the engineers trying to build software systems and the attackers trying to exploit them. Some cryptographic software is not designed to scale with computing power.

### What it bcrypt?
- bcrypt was designed by Niels Provos and David Mazières based on the Blowfish cipher: b for Blowfish and crypt for the name of the hashing function used by the UNIX password system
### how does bcrypt work
- it runs in 2 phases
  - phase 1 - A function called EksBlowfishSetup is setup using the desired cost, the salt, and the password to initialize the state of eksblowfish. Then, bcrypt spends a lot of time running an expensive key schedule which consists of performing a key derivation where we derive a set of subkeys from a primary key. Here, the password is used as the primary key. In case that the user selected a bad or short password, we stretch that password/key into a longer password/key
- phase 2 - The magic value is the 192-bit value OrpheanBeholderScryDoubt. This value is encrypted 64 times using eksblowfish in ECB mode with the state from the previous phase. The output of this phase is the cost and the 128-bit salt value concatenated with the result of the encryption loop
- The result of bcrypt achieves the three core properties of a secure password function as defined by its designers
  - It's preimage resistant
  - The salt space is large enough to mitigate precomputation attacks, such as rainbow tables.
  - It has an adaptable cost
  ### best practices
  - The challenge of security engineers is to decide what cost to set for the function. This cost is also known as the work factor. OWASP recommends as a common rule of thumb for work factor setting to tune the cost so that the function runs as slow as possible without affecting the users' experience and without increasing the need to use additional hardware that may be over budget.
  - two-factor authentication
  ### implementing
  - Technique 1
    - gnerate a salt and hash on separate function calls
  - Technique 2
    - Auto generate a salt and a hash
  ### validating a password with hash

  ## Token Storage
  ### Next.js static site scenarios
  1. When accessing a page
  2. When accessing an API route
  3. When your application calls an API hosted outside of your Next.js application on behalf of the user

  ### Where a server is available, your app can handle the interaction with Auth0 and create a session, but in this model, we don't have a backend. All of the work happens on the frontend:
  1. The user is redirected to Auth0
  2. When the user is successfully signed in, they will be redirected back to the application
  3. The client-side will complete the code exchange with Auth0 and retrieve the user's id_token and access_token which will be stored in memory.

  ### Traditional web app scenarios
  - If your app is using a sign in scenario that doesn't require API calls, only an ID token is required. There is no need to store it. You can validate it and get the data from it that you required
  - If your app needs to call APIs on behalf of the user, access tokens and (optionally) refresh tokens are needed. These can be stored server-side or in a session cookie. The cookie needs to be encrypted and have a maximum size of 4 KB. If the data to be stored is large, storing tokens in the session cookie is not a viable option
  ### Native/mobile app scenarios
  - Store tokens in a secure storage that the OS offers and limit access to that storage. For example, leverage KeyStore for Android and KeyChain for iOS
  ### Single page app scenarios
  - We recommend using the Auth0 SPA SDK to handle token storage, session management, and other details for you
  - When the SPA calls only an API that is served from a domain that can share cookies with the domain of the SPA, no tokens are needed. OAuth adds additional attack vectors without providing any additional value and should be avoided in favor of a traditional cookie-based approach
  - When the SPA calls multiple APIs that reside in a different domain, access, and optionally, refresh tokens are needed.
  ### Browser in-memory scenarios
  - Auth0 recommends storing tokens in browser memory as the most secure option. Using Web Workers to handle the transmission and storage of tokens is the best way to protect the tokens, as Web Workers run in a separate global scope than the rest of the application. Use Auth0 SPA SDK whose default storage option is in-memory storage leveraging Web Workers.
  - If you cannot use Web Workers, Auth0 recommends as an alternative that you use JavaScript closures to emulate private methods
  ### Browser local storage scenarios
  - Using browser local storage can be a viable alternative to mechanisms that require retrieving the access token from an iframe and to cookie-based authentication across domains when these are not possible due to browser restrictions


