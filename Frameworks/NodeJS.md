# Node.js Interview Questions and Answers

Node.js is one of the most popular JavaScript runtime environments, widely used for building fast, scalable, and real-time applications.  
In technical interviews, candidates are often asked Node.js questions ranging from basic concepts to advanced scenarios, depending on their experience level.

This document contains a collection of **Node.js interview questions and answers for all levels**:

- **Beginner:** Covers basic concepts, environment setup, and core features.
- **Intermediate:** Focuses on practical applications, modules, middleware, and performance optimization.
- **Senior/Advanced:** Includes architecture decisions, scaling, security, design patterns, and best practices.

By going through these questions, you can **revise key concepts**, **prepare for interviews at different levels**, and **strengthen your Node.js knowledge**.

---

This section provides the **basic Node.js interview questions** which will primarily help freshers.

---

---

## Table of Contents

1. [What is Node.js and Where can you use it?](#1-what-is-nodejs-and-where-can-you-use-it)
2. [Why use Node.js?](#2-why-use-nodejs)
3. [How does Node.js work?](#3-how-does-nodejs-work)
4. [Why is Node.js Single-threaded?](#4-why-is-nodejs-single-threaded)
5. [If Node.js is single-threaded, how does it handle concurrency?](#5-if-nodejs-is-single-threaded-then-how-does-it-handle-concurrency)
6. [Explain callback in Node.js](#6-explain-callback-in-nodejs)
7. [Advantages of using promises instead of callbacks](#7-what-are-the-advantages-of-using-promises-instead-of-callbacks)
8. [Define the term I/O](#8-how-would-you-define-the-term-io)
9. [How is Node.js most frequently used?](#9-how-is-nodejs-most-frequently-used)
10. [Difference between frontend and backend development](#10-explain-the-difference-between-frontend-and-backend-development)
11. [What is NPM?](#11-what-is-npm)
12. [What are the modules in Node.js?](#12-what-are-the-modules-in-nodejs)
13. [What is the purpose of the module .Exports?](#13-what-is-the-purpose-of-the-module-exports)
14. [Why is Node.js preferred over other backend technologies like Java and PHP?](#14-why-is-nodejs-preferred-over-other-backend-technologies-like-java-and-php)
15. [What is the difference between Angular and Node.js?](#15-what-is-the-difference-between-angular-and-nodejs)
16. [Which database is more popularly used with Node.js?](#16-which-database-is-more-popularly-used-with-nodejs)
17. [What are some of the most commonly used libraries in Node.js?](#17-what-are-some-of-the-most-commonly-used-libraries-in-nodejs)
18. [What are the pros and cons of Node.js?](#18-what-are-the-pros-and-cons-of-nodejs)
19. [What is the command used to import external libraries?](#19-what-is-the-command-used-to-import-external-libraries)
20. [What does event-driven programming mean?](#20-what-does-event-driven-programming-mean)
21. [What is an Event Loop in Node.js?](#21-what-is-an-event-loop-in-nodejs)
22. [Differentiate between process.nextTick() and setImmediate()?](#22-differentiate-between-process-nexttick-and-setimmediate)
23. [What is an EventEmitter in Node.js?](#23-what-is-an-eventemitter-in-nodejs)
24. [What are the two types of API functions in Node.js?](#24-what-are-the-two-types-of-api-functions-in-nodejs)
25. [What is the package.json file?](#25-what-is-the-packagejson-file)
26. [How would you use a URL module in Node.js?](#26-how-would-you-use-a-url-module-in-nodejs)
27. [What is the Express.js package?](#27-what-is-the-expressjs-package)
28. [How do you create a simple Express.js application?](#28-how-do-you-create-a-simple-expressjs-application)
29. [What are streams in Node.js?](#29-what-are-streams-in-nodejs)
30. [How do you install, update, and delete a dependency?](#30-how-do-you-install-update-and-delete-a-dependency)
31. [How do you create a simple server in Node.js that returns Hello World?](#31-how-do-you-create-a-simple-server-in-nodejs-that-returns-hello-world)
32. [Explain asynchronous and non-blocking APIs in Node.js](#32-explain-asynchronous-and-non-blocking-apis-in-nodejs)
33. [How do we implement async in Node.js?](#33-how-do-we-implement-async-in-nodejs)
34. [What is a callback function in Node.js?](#34-what-is-a-callback-function-in-nodejs)
35. [What is REPL in Node.js?](#35-what-is-repl-in-nodejs)
36. [What is the control flow function?](#36-what-is-the-control-flow-function)
37. [How does control flow manage the function calls?](#37-how-does-control-flow-manage-the-function-calls)
38. [What is the difference between fork() and spawn() methods in Node.js?](#38-what-is-the-difference-between-fork-and-spawn-methods-in-nodejs)
39. [What is the buffer class in Node.js?](#39-what-is-the-buffer-class-in-nodejs)
40. [What is piping in Node.js?](#40-what-is-piping-in-nodejs)
41. [What are some of the flags used in the read/write operations in files?](#41-what-are-some-of-the-flags-used-in-the-readwrite-operations-in-files)
42. [How do you open a file in Node.js?](#42-how-do-you-open-a-file-in-nodejs)
43. [What is callback hell?](#43-what-is-callback-hell)
44. [What is a reactor pattern in Node.js?](#44-what-is-a-reactor-pattern-in-nodejs)
45. [What is a test pyramid in Node.js?](#45-what-is-a-test-pyramid-in-nodejs)
46. [For Node.js, why does Google use the V8 engine?](#46-for-nodejs-why-does-google-use-the-v8-engine)
47. [Describe Node.js exit codes.](#47-describe-nodejs-exit-codes)
48. [Explain the concept of middleware in Node.js](#48-explain-the-concept-of-middleware-in-nodejs)
49. [What are the different types of HTTP requests?](#49-what-are-the-different-types-of-http-requests)
50. [How would you connect a MongoDB database to Node.js?](#50-how-would-you-connect-a-mongodb-database-to-nodejs)
51. [What is the purpose of NODE_ENV?](#51-what-is-the-purpose-of-node_env)
52. [List the various Node.js timing features](#52-list-the-various-nodejs-timing-features)
53. [What is WASI, and why is it being introduced?](#53-what-is-wasi-and-why-is-it-being-introduced)
54. [What is a first-class function in JavaScript?](#54-what-is-a-first-class-function-in-javascript)
55. [How do you manage packages in your Node.js project?](#55-how-do-you-manage-packages-in-your-nodejs-project)
56. [How is Node.js better than other frameworks?](#56-how-is-nodejs-better-than-other-frameworks)
57. [What is a fork in Node.js?](#57-what-is-a-fork-in-node-js)
58. [List down the two arguments that async.queue takes as input?](#58-list-down-the-two-arguments-that-async-queue-takes-as-input)
59. [What is the purpose of module.exports?](#59-what-is-the-purpose-of-module-exports)
60. [What tools can be used to assure consistent code style?](#60-what-tools-can-be-used-to-assure-consistent-code-style)
61. [What is the difference between JavaScript and Node.js?](#61-what-is-the-difference-between-javascript-and-nodejs)
62. [What is the difference between asynchronous and synchronous functions?](#62-what-is-the-difference-between-asynchronous-and-synchronous-functions)
63. [What are the asynchronous tasks that should occur in an event loop?](#63-what-are-the-asynchronous-tasks-that-should-occur-in-an-event-loop)
64. [What is the order of execution in control flow statements?](#64-what-is-the-order-of-execution-in-control-flow-statements)
65. [Are there any disadvantages to using Node.js?](#66-are-there-any-disadvantages-to-using-nodejs)
66. [What is the primary reason for using the event-based model in Node.js?](#67-what-is-the-primary-reason-for-using-the-event-based-model-in-nodejs)
67. [What is the difference between Node.js and Ajax?](#68-what-is-the-difference-between-nodejs-and-ajax)
68. [What is the advantage of using Node.js?](#69-what-is-the-advantage-of-using-nodejs)
69. [Does Node run on Windows?](#70-does-node-run-on-windows)
70. [Can you access DOM in Node?](#71-can-you-access-dom-in-node)
71. [Why is Node.js quickly gaining attention from Java programmers?](#72-why-is-nodejs-quickly-gaining-attention-from-java-programmers)
72. [What are the challenges with Node.js?](#73-what-are-the-challenges-with-nodejs)
73. [What is "non-blocking" in Node.js?](#74-what-is-non-blocking-in-nodejs)
74. [How does Node.js overcome the problem of blocking I/O operations?](#75-how-does-nodejs-overcome-the-problem-of-blocking-io-operations)
75. [How can we use async/await in Node.js?](#76-how-can-we-use-asyncawait-in-nodejs)
76. [How can we use async/await in Node.js?](#76-how-can-we-use-asyncawait-in-nodejs)
77. [Why should you separate the Express app and server?](#77-why-should-you-separate-the-express-app-and-server)
78. [Explain the concept of stub in Node.js](#78-explain-the-concept-of-stub-in-nodejs)
79. [What is the framework that is used majorly in Node.js today?](#79-what-is-the-framework-that-is-used-majorly-in-nodejs-today)
80. [What are the security implementations that are present in Node.js?](#80-what-are-the-security-implementations-that-are-present-in-nodejs)
81. [What is Libuv?](#81-what-is-libuv)
82. [What are global objects in Node.js?](#82-what-are-global-objects-in-nodejs)
83. [Why is assert used in Node.js?](#83-why-is-assert-used-in-nodejs)
84. [Why is ExpressJS used?](#84-why-is-expressjs-used)
85. [What is the use of the connect module in Node.js?](#85-what-is-the-use-of-the-connect-module-in-nodejs)
86. [What's the difference between 'front-end' and 'back-end' development?](#86-whats-the-difference-between-front-end-and-back-end-development)
87. [What are LTS releases of Node.js?](#87-what-are-lts-releases-of-nodejs)
88. [What do you understand about ESLint?](#88-what-do-you-understand-about-eslint)
89. [Define the concept of the test pyramid. Please explain the process of implementing them in terms of HTTP APIs.](#89-define-the-concept-of-the-test-pyramid-please-explain-the-process-of-implementing-them-in-terms-of-http-apis)
90. [How does Node.js handle the child threads?](#90-how-does-nodejs-handle-the-child-threads)

---

## 1. What is Node.js and Where can you use it?

**Answer:**  
Node.js is an open-source, cross-platform JavaScript runtime environment and library to run web applications outside the client’s browser. It is mainly used to create server-side web applications.

Node.js is perfect for **data-intensive applications** as it uses an **asynchronous, event-driven model**.

You can use Node.js in:

- I/O intensive web applications like video streaming sites
- Real-time web applications
- Network applications
- General-purpose applications
- Distributed systems

---

## 2. Why use Node.js?

**Answer:**  
Node.js makes building scalable network programs easy. Some of its advantages include:

- It is generally fast
- It rarely blocks
- It offers a unified programming language and data type
- Everything is asynchronous
- It yields great concurrency

---

## 3. How does Node.js work?

**Answer:**  
A web server using Node.js typically follows an **asynchronous, event-driven architecture**. The workflow can be described as follows:

![Node.js Architecture Workflow](/images/nodejs/Node.js_Architecture_Workflow.avif)

1. **Client Requests:**  
   Clients send requests to the web server to interact with the web application. These requests can be either **non-blocking** or **blocking**, such as:

   - Querying for data
   - Deleting data
   - Updating data

2. **Event Queue:**  
   Node.js retrieves the incoming requests and adds them to the **Event Queue**.

3. **Event Loop:**  
   The requests are processed one-by-one through the **Event Loop**:

   - It checks if a request is simple enough not to require any external resources.
   - Simple (non-blocking) requests, such as I/O polling, are processed directly and responses are sent back to the clients.

4. **Thread Pool:**
   - Complex (blocking) requests, like database queries, computations, or file system access, are assigned to a **single thread from the Thread Pool**.
   - The thread completes the task and sends the response back to the Event Loop, which then returns it to the client.

**Key Point:** Node.js uses a **single-threaded event loop** for non-blocking operations and a **thread pool** for heavy, blocking tasks, enabling high concurrency and scalability.

## 4. Why is Node.js Single-threaded?

**Answer:**  
Node.js is **single-threaded** to efficiently handle **asynchronous processing**.

By performing async operations on a single thread under typical web loads, Node.js can achieve:

- **Higher performance** – because threads are not blocked waiting for I/O operations.
- **Better scalability** – as a single thread can handle thousands of concurrent connections efficiently.

This design contrasts with traditional thread-based implementations, where each request often requires a separate thread, which can consume more memory and reduce scalability.

## 5. If Node.js is single-threaded, then how does it handle concurrency?

**Answer:**  
Even though Node.js is **single-threaded**, it can handle **concurrent client requests** efficiently using the **Event Loop**.

Key points:

- Node.js does **not** follow the traditional multi-threaded request/response model.
- It follows a **single-threaded, event-driven model**, heavily influenced by JavaScript’s **event-based architecture** and **callback system**.
- The **Event Loop** is at the core of Node.js processing. It continuously monitors the **Event Queue** and handles incoming requests asynchronously.
- Simple, non-blocking tasks are processed immediately, while heavy, blocking tasks are delegated to the **thread pool**.

This architecture allows Node.js to **manage thousands of concurrent connections** without creating a new thread for each request, making it lightweight and highly scalable.

## 6. Explain callback in Node.js

**Answer:**  
A **callback function** is a function that is passed as an argument to another function and is executed **after a given task is completed**.

Key points about callbacks in Node.js:

- They allow other code to run **in the meantime**, preventing blocking of the execution thread.
- Node.js is an **asynchronous platform**, so it heavily relies on callbacks.
- **All Node.js APIs** are designed to support callbacks for handling asynchronous operations like I/O, networking, or file system access.

**Example:**

```javascript
const fs = require("fs");

fs.readFile("example.txt", "utf8", (err, data) => {
  if (err) {
    console.error("Error reading file:", err);
    return;
  }
  console.log("File contents:", data);
});
```

## 7. What are the advantages of using promises instead of callbacks?

**Answer:**  
Using **Promises** in Node.js offers several advantages over traditional callbacks:

1. **Structured Control Flow:**  
   Promises make the flow of asynchronous logic more **specified and structured**, reducing the complexity of nested callbacks (callback hell).

2. **Low Coupling:**  
   Promises promote **looser coupling** between different parts of the code, making it easier to maintain and reuse.

3. **Built-in Error Handling:**  
   Promises provide **.catch()** methods to handle errors in a centralized way, avoiding scattered error handling in multiple callbacks.

4. **Improved Readability:**  
   Promises improve the **readability** of asynchronous code, making it look more linear and easier to understand.

**Example:**

```javascript
const fs = require("fs").promises;

fs.readFile("example.txt", "utf8")
  .then((data) => {
    console.log("File contents:", data);
  })
  .catch((err) => {
    console.error("Error reading file:", err);
  });
```

## 8. How would you define the term I/O?

**Answer:**  
The term **I/O (Input/Output)** refers to any program, operation, or device that **transfers data** between a medium and another medium.

Key points:

- Every transfer is an **output** from one medium and an **input** into another.
- The medium can be:

  - A **physical device** (e.g., keyboard, hard drive)
  - A **network** (e.g., API requests, sockets)
  - **Files within a system**

  ![How would you define the term I/O](/images/nodejs/io.jpeg)

In Node.js, **I/O operations** (like reading/writing files, network requests, database queries) are typically **asynchronous**, which allows the single-threaded event loop to handle multiple operations concurrently without blocking.

## 9. How is Node.js most frequently used?

**Answer:**  
Node.js is widely used for building **high-performance, scalable applications**, especially those requiring real-time data and asynchronous processing. Common use cases include:

- **Real-time chats** – e.g., chat applications with instant messaging
- **Internet of Things (IoT)** – handling large numbers of device connections
- **Complex Single-Page Applications (SPAs)** – dynamic front-end applications
- **Real-time collaboration tools** – e.g., collaborative editors or whiteboards
- **Streaming applications** – e.g., video and audio streaming platforms
- **Microservices architecture** – creating lightweight, decoupled services that communicate efficiently

Node.js’s **event-driven, non-blocking I/O model** makes it particularly suitable for these use cases.

## 10. Explain the difference between frontend and backend development

**Answer:**

| Frontend                                                                      | Backend                                                                                     |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Refers to the **client-side** of an application                               | Refers to the **server-side** of an application                                             |
| Part of the web application that users can **see and interact with**          | Constitutes everything that happens **behind the scenes**                                   |
| Includes everything that contributes to the **visual aspects** of the web app | Generally includes a **web server** that communicates with a **database** to serve requests |
| Technologies include **HTML, CSS, JavaScript, AngularJS, ReactJS**            | Technologies include **Java, PHP, Python, Node.js**                                         |

**Summary:**

- Frontend focuses on **user interface and experience**.
- Backend focuses on **data processing, storage, and server logic**.

## 11. What is NPM?

**Answer:**  
**NPM** stands for **Node Package Manager**, which is responsible for managing all the packages and modules for Node.js.

**Main functionalities of NPM:**

| Functionality        | Description                                                                                                             |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Online repositories  | Provides online repositories for Node.js packages/modules, searchable at [search.nodejs.org](https://search.nodejs.org) |
| Command-line utility | Installs Node.js packages, manages Node.js versions, and handles dependencies                                           |

NPM makes it easy to **share, install, and manage Node.js packages**, making Node.js development more efficient.

## 12. What are the modules in Node.js?

Modules in Node.js are like **JavaScript libraries** that can be used in a Node.js application to include a set of functions.

To include a module in a Node.js application, use the `require()` function with the module name inside parentheses:

```javascript
const http = require("http"); // Example of including the HTTP module
```

Node.js has many modules to provide the basic functionality needed for a web application. Some of them include:

| Module          | Description                                                            |
| --------------- | ---------------------------------------------------------------------- |
| **HTTP**        | Includes classes, methods, and events to create a Node.js HTTP server  |
| **util**        | Includes utility functions useful for developers                       |
| **fs**          | Includes events, classes, and methods to deal with file I/O operations |
| **url**         | Includes methods for URL parsing                                       |
| **querystring** | Includes methods to work with query strings                            |
| **stream**      | Includes methods to handle streaming data                              |
| **zlib**        | Includes methods to compress or decompress files                       |

## 13. What is the purpose of the module .Exports?

In **Node.js**, a module encapsulates all related code into a single unit of code by moving all relevant functions into a single file.  
You can **export a module** using `module.exports`, which allows the functions, objects, or variables inside a file to be imported and used in another file.

#### Example:

```js
// math.js
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

// Export functions
module.exports = { add, subtract };
```

## 14. Why is Node.js preferred over other backend technologies like Java and PHP?

Some of the reasons why Node.js is preferred include:

- Node.js is very fast
- Node Package Manager has over 50,000 bundles available at the developer’s disposal
- Perfect for data-intensive, real-time web applications, as Node.js never waits for an API to return data
- Better synchronization of code between server and client due to same code base
- Easy for web developers to start using Node.js in their projects as it is a JavaScript library

---

## 15. What is the difference between Angular and Node.js?

| Angular                                                     | Node.js                                                                 |
| ----------------------------------------------------------- | ----------------------------------------------------------------------- |
| Frontend development framework                              | Server-side environment                                                 |
| Written in TypeScript                                       | Written in C, C++ languages                                             |
| Used for building single-page, client-side web applications | Used for building fast and scalable server-side networking applications |
| Splits a web application into MVC components                | Generates database queries                                              |

---

## 16. Which database is more popularly used with Node.js?

**Answer:**  
MongoDB is the most common database used with Node.js. It is a **NoSQL, cross-platform, document-oriented database** that provides:

- High performance
- High availability
- Easy scalability

---

## 17. What are some of the most commonly used libraries in Node.js?

**Answer:**  
Some of the most commonly used libraries in Node.js include:

- **ExpressJS** – A flexible Node.js web application framework that provides a wide set of features to develop web and mobile applications.
- **Mongoose** – A Node.js library that simplifies connecting an application to a MongoDB database and managing data schemas.

---

## 18. What are the pros and cons of Node.js?

| Node.js Pros                                                                    | Node.js Cons                                                                  |
| ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Fast processing and an event-based model                                        | Not suitable for heavy computational tasks                                    |
| Uses JavaScript, which is well-known amongst developers                         | Using callbacks can be complex, leading to nested callbacks                   |
| Node Package Manager has over 50,000 packages providing various functionalities | Dealing with relational databases is not ideal                                |
| Best suited for streaming large amounts of data and I/O-intensive operations    | Since Node.js is single-threaded, CPU-intensive tasks are not its strong suit |

---

## 19. What is the command used to import external libraries?

**Answer:**  
The `require` command is used for importing external libraries in Node.js.

**Example:**

```javascript
var http = require("http"); // This loads the HTTP library into the variable 'http'
```

## 20. What does event-driven programming mean?

**Answer:**  
Event-driven programming is a programming paradigm that **uses events to trigger various functions**.

- An **event** can be anything, such as typing a key, clicking a mouse button, or receiving data.
- A **callback function** is registered with an element and executes whenever the event is triggered.

**Example:**

```javascript
const button = document.getElementById("myButton");

button.addEventListener("click", () => {
  console.log("Button was clicked!");
});
```

## 21. What is an Event Loop in Node.js?

**Answer:**  
The **Event Loop** in Node.js handles asynchronous callbacks and is the foundation of Node.js's **non-blocking I/O** model.  
It allows Node.js to perform **non-blocking operations** despite being single-threaded, making it one of the most important features of the Node.js environment.

---

## 22. Differentiate between process.nextTick() and setImmediate()

**Answer:**  
The distinction between `process.nextTick()` and `setImmediate()` in Node.js is:

- **process.nextTick()**: Postpones the execution of a callback **until the current operation completes** and the event loop is at its **next phase**. It runs **before any I/O events** in the next loop cycle.
- **setImmediate()**: Executes a callback **on the next cycle of the event loop**, allowing the event loop to handle any pending I/O operations before running the callback.

**Key Point:**  
`nextTick()` is executed **before** the event loop continues, while `setImmediate()` executes **after I/O events** in the next loop iteration.

---

## 23. What is an EventEmitter in Node.js?

**Answer:**  
The **EventEmitter** is a class in Node.js that allows objects to **emit events** and register **listeners** (callback functions) for those events.

- Whenever an object from the EventEmitter class **emits an event**, all attached functions (listeners) are called **synchronously**.

**Example:**

```javascript
const EventEmitter = require("events");
const myEmitter = new EventEmitter();

myEmitter.on("event", () => {
  console.log("An event occurred!");
});

myEmitter.emit("event"); // Output: An event occurred!
```

## 24. What are the two types of API functions in Node.js?

**Answer:**  
The two types of API functions in Node.js are:

- **Asynchronous, non-blocking functions** – These functions allow other operations to run while waiting for completion.
- **Synchronous, blocking functions** – These functions block the execution of code until the operation completes.

---

## 25. What is the package.json file?

**Answer:**  
The **package.json** file is the heart of a Node.js project. It contains **metadata** about the project and is located in the root directory of any Node application or module.

- It is automatically created when you run the command: `npm init`
- You can edit parameters like `name`, `version`, `description`, `main`, `scripts`, and `dependencies` when creating a Node.js project

**Example:**

```json
{
  "name": "my-node-app",
  "version": "1.0.0",
  "description": "A simple Node.js project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  },
  "dependencies": {}
}
```

## 26. How would you use a URL module in Node.js?

**Answer:**  
The **URL module** in Node.js is a built-in module that provides utilities for **URL resolution and parsing**.  
It helps to split a web address into a readable format and access its components such as protocol, hostname, pathname, query, and hash.

**Example:**

```javascript
const url = require("url");

const myURL = new URL("https://example.com/path?name=NodeJS#section1");

console.log(myURL.hostname); // Output: example.com
console.log(myURL.pathname); // Output: /path
console.log(myURL.search); // Output: ?name=NodeJS
console.log(myURL.hash); // Output: #section1
```

## 27. What is the Express.js package?

**Answer:**  
**Express.js** is a flexible Node.js **web application framework** that provides a wide set of features to develop both **web and mobile applications**.  
It simplifies routing, middleware management, and handling HTTP requests and responses.

**Example:**

```javascript
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Hello World!");
});

app.listen(3000, () => {
  console.log("Server is running on port 3000");
});
```

## 28. How do you create a simple Express.js application?

**Answer:**  
In Express.js, a simple application uses the **request** and **response** objects:

- **Request (`req`)**: Represents the HTTP request and contains properties like query string, parameters, body, and HTTP headers.
- **Response (`res`)**: Represents the HTTP response that the Express app sends when it receives a request.

**Example:**

```javascript
var express = require("express");
var app = express();

app.get("/", function (req, res) {
  res.send("Hello World");
});

var server = app.listen(8081, function () {
  var host = server.address().address;
  var port = server.address().port;

  console.log("Example app listening at http://%s:%s", host, port);
});
```

## 29. What are streams in Node.js?

Streams are objects that enable you to read data or write data continuously.

There are four types of streams:

- **Readable** – Used for reading operations
- **Writable** − Used for write operations
- **Duplex** − Can be used for both read and write operations
- **Transform** − A type of duplex stream where the output is computed based on the input

## 30. How do you install, update, and delete a dependency?

In Node.js, dependencies are managed using **npm** (Node Package Manager) or **yarn**.

- **Install a dependency**:

```bash
npm install <package-name>
# or with yarn
yarn add <package-name>

# Update a dependency:
npm update <package-name>
# or with yarn
yarn upgrade <package-name>

#Delete a dependency:
npm uninstall <package-name>
# or with yarn
yarn remove <package-name>
```

## 31. How do you create a simple server in Node.js that returns Hello World?

To create a simple server that returns "Hello World":

```javascript
// Import the HTTP module
const http = require("http");

// Create the server
const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "text/plain" });
  res.end("Hello World\n");
});

// Server listens on port 8080 and IP address 127.0.0.1
server.listen(8080, "127.0.0.1", () => {
  console.log("Server running at http://127.0.0.1:8080/");
});
```

**Steps explained:**

1. Import the built-in `http` module.
2. Use `createServer()` with a callback that takes `request` and `response`.
3. Write "Hello World" as the response.
4. Listen on port `8080` and IP `127.0.0.1`.

## 32. Explain asynchronous and non-blocking APIs in Node.js

- All Node.js library APIs are **asynchronous**, which means they are also **non-blocking**.

- A Node.js-based server **never waits** for an API to return data. Instead, it moves to the next API after calling it, and a **notification mechanism** from the Node.js **event loop** responds to the server when the previous API call is complete.

## 33. How do we implement async in Node.js?

In Node.js, **async** allows the JavaScript engine to wait for a function to complete before moving to the next line of code.

For example, when using an asynchronous operation like `request.get()`, the engine pauses at that point until the request completes, ensuring that subsequent lines execute only after the awaited operation finishes.

```javascript
import fetch from "node-fetch"; // Only needed if using node-fetch in older Node.js

async function func1() {
  try {
    const response = await fetch("http://localhost:3000");
    const data = await response.text(); // or .json() if the response is JSON
    console.log("Fetched response:", data);
  } catch (err) {
    console.log("Error:", err);
  }
}

func1();
```

## 34. What is a callback function in Node.js?

A **callback** is a function that is passed as an argument to another function and is **executed after a given task is completed**.

Callbacks prevent blocking and allow other code to run in the meantime, making Node.js **asynchronous** and **non-blocking**.

## 35. What is REPL in Node.js?

**REPL** stands for **Read-Eval-Print Loop**. It represents an interactive computer environment similar to a **Windows console** or **Unix/Linux shell**, where:

REPL performs the following desired tasks:

- **Read** - Reads users input, parses the input into JavaScript data-structure and stores in memory
- **Eval** - Takes and evaluates the data structure
- **Print** - Prints the result
- **Loop** - Loops the above command until user presses ctrl-c twice

## 36. What is the control flow function?

A **control flow function** is code that helps **manage the execution order** between several asynchronous function calls.

Since Node.js executes operations asynchronously, control flow functions ensure that tasks are executed in the correct sequence, handle dependencies between operations, and manage what happens when an operation finishes or fails.

## 37. How does control flow manage the function calls?

The **control flow** in Node.js manages asynchronous function calls by ensuring proper coordination between tasks. It performs the following jobs:

1. **Control the order of execution** – Ensures functions run in the correct sequence.
2. **Collect data** – Gathers results from different asynchronous operations.
3. **Limit concurrency** – Restricts how many functions run at the same time.
4. **Call the next step in a program** – Proceeds to the next task once the current one finishes.

## 38. What is the difference between fork() and spawn() methods in Node.js?

In Node.js, both `fork()` and `spawn()` are used to create child processes, but they differ in behavior:

- **fork()**

  - A special case of `spawn()`.
  - Creates a **new instance of the V8 engine**.
  - Used specifically to spawn new Node.js processes.
  - Useful for running multiple workers on the same Node.js code base.

- **spawn()**
  - Launches a **new process** with a given command.
  - Does **not** generate a new V8 instance.
  - Only a single copy of the Node.js module runs on the processor.
  - Typically used for executing system commands or external processes.

## 39. What is the buffer class in Node.js?

The **Buffer class** in Node.js is used to handle **binary data** directly.

- Buffers work like an array of integers but correspond to raw memory allocations **outside the V8 heap**.
- They are essential because **pure JavaScript cannot efficiently handle binary data**.
- Commonly used when dealing with:
  - File I/O
  - TCP streams
  - Image/video data
  - Binary protocols

### Example:

```javascript
// Create a buffer from a string
const buf = Buffer.from("Hello World", "utf-8");

console.log(buf); // <Buffer 48 65 6c 6c 6f 20 57 6f 72 6c 64>
console.log(buf.toString()); // Hello World
console.log(buf.length); // 11
```

## 40. What is piping in Node.js?

**Piping** is a mechanism in Node.js that allows you to **connect the output of one stream directly to another stream**.

- It is mainly used to **transfer data between streams** without manually handling the data events.
- Example: Reading from a file (input stream) and writing it to another file (output stream).

### Example: File Copy using Pipe

```javascript
const fs = require("fs");

// Create a readable stream (input.txt)
const reader = fs.createReadStream("input.txt");

// Create a writable stream (output.txt)
const writer = fs.createWriteStream("output.txt");

// Pipe data from reader to writer
reader.pipe(writer);

console.log("Data piped successfully!");
```

### Key Notes:

- `pipe()` can be **chained** to connect multiple streams.
- Commonly used in:
  - **File handling**
  - **Network streams**
  - **Compressing/Decompressing files**

```javascript
const fs = require("fs");
const zlib = require("zlib");

// Compress input.txt to input.txt.gz
fs.createReadStream("input.txt")
  .pipe(zlib.createGzip())
  .pipe(fs.createWriteStream("input.txt.gz"));

console.log("File compressed successfully!");
```

## 41. What are some of the flags used in the read/write operations in files?

### File System Flags in Node.js

| Flag | Mode          | Description                                                                          |
| ---- | ------------- | ------------------------------------------------------------------------------------ |
| `r`  | Read          | Opens file for reading. Throws error if file does not exist.                         |
| `r+` | Read & Write  | Opens file for reading and writing. Throws error if file does not exist.             |
| `w`  | Write         | Opens file for writing. Creates new file if not exists, truncates if exists.         |
| `w+` | Read & Write  | Opens file for reading and writing. Creates file if not exists, truncates if exists. |
| `a`  | Append        | Opens file for appending. Creates file if not exists.                                |
| `a+` | Read & Append | Opens file for reading and appending. Creates file if not exists.                    |

**Key Notes:**

- `r` and `r+` → Require file to exist.
- `w`, `w+` → Create file if missing, truncate if exists.
- `a`, `a+` → Create file if missing, append instead of truncating.

## 42. How do you open a file in Node.js?

This is the syntax for opening a file in Node.js:

```javascript
fs.open(path, flags[, mode], callback)
```

## 43. What is callback hell?

Callback hell, also known as the **pyramid of doom**, occurs when callbacks are nested deeply and become **unreadable and unmanageable**. This makes the code harder to read, debug, and maintain.

It usually happens due to **improper implementation of asynchronous logic** in JavaScript.

**Example of callback hell:**

```javascript
doSomething(function (result) {
  doSomethingElse(result, function (newResult) {
    doAnotherThing(newResult, function (finalResult) {
      console.log(finalResult);
    });
  });
});
```

## 44. What is a reactor pattern in Node.js?

The **Reactor Pattern** is a design pattern used for **non-blocking I/O operations** in Node.js.

**How it works:**

- A **handler** is associated with each I/O operation.
- When an I/O request is generated, it is submitted to a **demultiplexer**.
- The demultiplexer monitors multiple I/O events and dispatches them to their respective handlers when they are ready.

**Key Points:**

- Enables **asynchronous, non-blocking behavior**.
- Helps Node.js handle thousands of concurrent connections efficiently.
- Forms the foundation of Node.js’s **event-driven architecture**.

## 45. What is a test pyramid in Node.js?

The **Test Pyramid** is a concept in software testing that describes the **distribution of different types of tests** to achieve efficient and maintainable testing.

![What is a test pyramid in Node.js?](/images/nodejs/test-pyramid.jpeg)

**Structure of the Test Pyramid:**

1. **Unit Tests (Base of the Pyramid)**

   - Test individual functions or modules in isolation.
   - Fast to execute and easy to maintain.

2. **Integration Tests (Middle Layer)**

   - Test the interaction between multiple modules or components.
   - Ensure that different parts of the system work together correctly.

3. **End-to-End (E2E) Tests (Top Layer)**
   - Test the entire application flow from start to finish.
   - Slower to run and harder to maintain, but ensure the system works as expected from the user’s perspective.

**Key Points:**

- More **unit tests** than integration or E2E tests.
- Helps balance **test coverage, speed, and maintainability**.
- Guides developers to write **efficient automated tests** for Node.js applications.

## 46. For Node.js, why does Google use the V8 engine?

The **V8 engine**, developed by Google, is an **open-source JavaScript engine written in C++**. It is used in **Google Chrome** and also powers **Node.js**.

**Why V8 is used:**

- Designed to **improve the speed of JavaScript execution**.
- Converts JavaScript code into **efficient machine code** rather than interpreting it line by line.
- Uses a **Just-In-Time (JIT) compiler** to optimize performance during execution.
- Provides **high performance and efficiency**, making it ideal for server-side applications in Node.js.

**Key Points:**

- Enables **fast JavaScript execution** both in browsers and Node.js.
- Forms the foundation for Node.js’s **event-driven, non-blocking architecture**.
- Competes with other engines like **SpiderMonkey** (Mozilla) and **Rhino** (Java-based).

## 47. Describe Node.js exit codes

Node.js **exit codes** are numeric codes returned by a process when it **terminates**. These codes indicate whether the process ended successfully or if an error occurred.

![Node.js exit codes](/images/nodejs/exit-codes.jpeg)

**Common Exit Codes:**

| Exit Code | Meaning                                     |
| --------- | ------------------------------------------- |
| `0`       | Success — process completed without errors. |
| `1`       | Uncaught Fatal Exception / Generic Error.   |
| `7`       | Command line usage error.                   |
| `9`       | Fatal error (abort).                        |
| `13`      | Permission denied.                          |
| `14`      | Internal JavaScript evaluation failure.     |
| `15`      | Termination (SIGTERM signal).               |

**Key Points:**

- `process.exit(code)` can be used to **manually terminate** a Node.js process.
- Exit codes are helpful for **automation scripts**, **CI/CD pipelines**, and **error handling**.
- Non-zero codes indicate **errors or abnormal termination**.

## 48. Explain the concept of middleware in Node.js

**Middleware** is a function in Node.js that has access to the **request (`req`)** and **response (`res`)** objects, as well as the **next** function in the request-response cycle.

**Main tasks performed by middleware:**

- Execute any code.
- Update or modify the request and response objects.
- Finish the request-response cycle (e.g., send a response).
- Invoke the **next middleware** in the stack using `next()`.

**Example:**

```javascript
function logger(req, res, next) {
  console.log(`${req.method} ${req.url}`);
  next(); // Pass control to the next middleware
}

app.use(logger);
```

## 49. What are the different types of HTTP requests?

HTTP defines a set of **request methods** used to perform actions on a server. The most common HTTP request types are:

| Method    | Description                                                                             |
| --------- | --------------------------------------------------------------------------------------- |
| `GET`     | Retrieve data from the server.                                                          |
| `POST`    | Submit data to the server, usually causing a change in state or side effects.           |
| `HEAD`    | Similar to `GET`, but requests **only the headers** without the response body.          |
| `DELETE`  | Delete the specified resource on the server.                                            |
| `PUT`     | Update a resource completely or create it if it does not exist.                         |
| `PATCH`   | Partially update a resource.                                                            |
| `OPTIONS` | Describe the communication options for the target resource.                             |
| `CONNECT` | Establish a tunnel to the server identified by the target resource (used with proxies). |

**Key Points:**

- `GET` and `HEAD` are **safe and idempotent**.
- `POST` is generally used for **creating resources or triggering actions**.
- `PUT` is **idempotent**; calling it multiple times has the same effect as once.
- `PATCH` is used for **partial updates**.
- `DELETE` removes resources and is usually **idempotent**.
- `OPTIONS` is useful for **CORS preflight requests** and discovering allowed methods.
- `CONNECT` is mostly used for **tunneling through proxies** (e.g., HTTPS).

## 50. How would you connect a MongoDB database to Node.js?

To connect a **MongoDB database** to Node.js, you typically use the official **MongoDB Node.js driver** or an ORM like **Mongoose**.

**Steps using the MongoDB driver:**

1. **Install the driver**:

```bash
npm install mongodb
```

2. **Create a MongoClient object**:

```javascript
const { MongoClient } = require("mongodb");
const url = "mongodb://localhost:27017";
const dbName = "myDatabase";

const client = new MongoClient(url);
```

3. **Connect to the database**:

```javascript
async function main() {
  try {
    await client.connect();
    console.log("Connected successfully to MongoDB");

    const db = client.db(dbName);
    // You can now perform CRUD operations on `db`
  } catch (err) {
    console.error(err);
  } finally {
    await client.close();
  }
}

main();
```

**Key Points:**

- Specify the correct connection URL (IP/hostname, port, and database name).
- Always handle errors during connection.
- Use client.close() to properly close the connection.
- For production, consider connection pooling for better performance.

**Optional: Using Mongoose:**

```bash
npm install mongoose
```

```javascript
const mongoose = require("mongoose");

mongoose
  .connect("mongodb://localhost:27017/myDatabase", {
    useNewUrlParser: true,
    useUnifiedTopology: true,
  })
  .then(() => console.log("MongoDB connected"))
  .catch((err) => console.error(err));
```

## 51. What is the purpose of NODE_ENV?

`NODE_ENV` is an **environment variable** in Node.js that specifies the **execution environment** of an application. It helps developers configure the app differently for **development, testing, and production** environments.

**Common values:**

| Value         | Purpose                                                                                       |
| ------------- | --------------------------------------------------------------------------------------------- |
| `development` | Used while developing the application; often enables detailed logging and debugging features. |
| `production`  | Used in production; disables debugging and enables performance optimizations.                 |
| `test`        | Used during testing; may enable mock data, test databases, or special logging.                |

**Key Points:**

- Allows **conditional code execution** depending on the environment.
- Improves **performance and security** in production by disabling verbose logging.
- Can be accessed in Node.js using `process.env.NODE_ENV`.

**Example:**

```javascript
if (process.env.NODE_ENV === "development") {
  console.log("Running in development mode");
} else if (process.env.NODE_ENV === "production") {
  console.log("Running in production mode");
}
```

## 52. List the various Node.js timing features

Node.js provides several **timing-related functions** to schedule code execution and control delays. These features are part of the **Timers module**.

**Common Node.js timing features:**

| Feature              | Description                                                                                           |
| -------------------- | ----------------------------------------------------------------------------------------------------- |
| `setTimeout()`       | Executes a function **once after a specified delay** (in milliseconds).                               |
| `clearTimeout()`     | Cancels a timeout previously established by `setTimeout()`.                                           |
| `setInterval()`      | Repeatedly executes a function at **specified intervals** (in milliseconds).                          |
| `clearInterval()`    | Cancels an interval previously established by `setInterval()`.                                        |
| `setImmediate()`     | Executes a function **immediately after the current event loop cycle**.                               |
| `clearImmediate()`   | Cancels an immediate execution previously scheduled by `setImmediate()`.                              |
| `process.nextTick()` | Schedules a callback to **run at the end of the current operation**, before the event loop continues. |

**Key Points:**

- Timing functions are essential for **asynchronous programming** in Node.js.
- `setTimeout()` and `setInterval()` are **global functions**, no need to require any module.
- `setImmediate()` and `process.nextTick()` help **control the order of asynchronous callbacks** in the event loop.

**Example:**

```javascript
setTimeout(() => console.log("Executed after 2 seconds"), 2000);
setImmediate(() => console.log("Executed immediately after I/O events"));
process.nextTick(() => console.log("Executed at the end of current operation"));
```

## 53. What is WASI, and why is it being introduced?

**WASI** (WebAssembly System Interface) is a **system interface for WebAssembly** that allows running WebAssembly applications outside the browser in a **secure and sandboxed environment**.

**Key Concepts:**

- Each WASI instance represents a **unique sandbox environment**.
- A WASI instance must specify:
  - **Command-line parameters**
  - **Environment variables**
  - **Sandbox directory structure** for security.
- Provides **API and helper methods** for interacting with WASI-based applications.

**Why WASI is being introduced:**

- To allow WebAssembly applications to **run safely on servers, desktops, or embedded devices**.
- Provides **standardized system calls** for file I/O, clocks, and other OS-level interactions.
- Enhances **portability, security, and modularity** of WebAssembly programs.

**Example Use Case:**

```javascript
const { WASI } = require("wasi");
const wasi = new WASI({
  args: process.argv,
  env: process.env,
  preopens: { "/sandbox": "./sandbox" },
});
```

**Key Points:**

- WASI enables running WebAssembly modules outside browsers.
- Ensures isolation and security for system-level interactions.
- Useful for server-side, CLI, or embedded WebAssembly applications.

## 54. What is a first-class function in JavaScript?

A **first-class function** is a function that is treated as a **first-class citizen** in JavaScript. This means it can be:

- **Assigned to variables**
- **Passed as arguments** to other functions
- **Returned from other functions**
- **Stored in data structures** like arrays or objects

**In Node.js:**

- First-class functions are heavily used in **asynchronous programming**.
- They enable **callbacks, promises, and higher-order functions**, allowing non-blocking and flexible code.

**Example:**

```javascript
// Assigning function to a variable
const greet = function (name) {
  console.log(`Hello, ${name}`);
};

// Passing function as an argument
function processUserInput(callback) {
  const name = "Alice";
  callback(name);
}

processUserInput(greet);

// Returning a function from another function
function multiplier(factor) {
  return function (x) {
    return x * factor;
  };
}

const double = multiplier(2);
console.log(double(5)); // Output: 10
```

**Key Points:**

- First-class functions allow modular, reusable, and composable code.
- Essential for event-driven and asynchronous programming in Node.js.

## 55. How do you manage packages in your Node.js project?

In Node.js, **packages** are managed using the **Node Package Manager (NPM)** or alternatives like **Yarn**. This allows you to **install, update, and manage dependencies** for your project.

**Managing packages with NPM:**

1. **Initialize a project**:

```bash
npm init
# or npm init -y (to accept defaults)
```

2. **Install packages**:

```bash
npm install <package-name >      # Install locally and add to dependencies
npm install -g <package-name >   # Install globally
npm install <package-name > --save-dev  # Install as development dependency
```

3. **Uninstall packages**:

```bash
npm uninstall <package-name >
```

4. **Update packages**:

```bash
npm update <package-name >
```

5. **Check outdated packages**:

```bash
npm update <package-name >
```

6. **Package.json file**:

- Lists all project dependencies and versions.
- Allows reproducible builds across environments.

**Key Points**:

- NPM helps manage third-party libraries efficiently.
- Provides a registry for publishing your own packages.
- Essential for project modularity and dependency management in Node.js.

## 56. How is Node.js better than other frameworks?

**Node.js** is a **server-side JavaScript runtime** built on the **V8 engine** (used by Google Chrome). It offers several advantages over other frameworks:

**Key Advantages:**

1. **High Performance**

   - V8 engine compiles JavaScript to machine code, making Node.js **very fast**.
   - Handles **concurrent requests efficiently** using the **event-driven, non-blocking I/O model**.

2. **Scalability**

   - Built for **real-time, high-traffic applications**.
   - Supports **horizontal scaling** across multiple servers.

3. **Full-Stack JavaScript**

   - Developers can use **JavaScript for both frontend and backend**, simplifying the development process.

4. **Large Ecosystem**

   - Access to **NPM registry** with thousands of open-source packages and libraries.

5. **Community Support**

   - Strong **community and corporate backing** for updates, tools, and best practices.

6. **Asynchronous & Non-Blocking**
   - Ideal for **I/O-heavy applications**, like chat apps, APIs, and streaming services.

**Summary:**  
Node.js provides **speed, scalability, and efficiency** while allowing developers to **use JavaScript across the entire stack**, which many traditional frameworks do not support.

## 57. What is a fork in Node.js?

In Node.js, **`fork()`** is a method used to create a **new child process** that runs a **separate Node.js instance**.

**Key Points:**

- Allows running **CPU-intensive tasks** without blocking the main event loop.
- Useful for **creating clusters** of Node.js servers to improve performance.
- The parent and child processes can communicate via **inter-process messaging** using `send()` and `on('message')`.

**Example:**

```javascript
const { fork } = require("child_process");

const child = fork("child.js");

child.on("message", (msg) => {
  console.log("Message from child:", msg);
});

child.send({ hello: "world" });
```

## 58. List down the two arguments that async.queue takes as input

The `async.queue` function in Node.js is used to **create a task queue** that executes tasks in parallel with controlled concurrency.

**Arguments:**

1. **Worker function**

   - A function that processes each task in the queue.
   - Receives the task data and a callback to signal completion.

2. **Concurrency limit (optional)**
   - Specifies the **maximum number of tasks** to process in parallel.
   - Defaults to `1` if not provided.

**Example:**

```javascript
const async = require("async");

const queue = async.queue(function (task, callback) {
  console.log("Processing task:", task.name);
  callback();
}, 2); // concurrency = 2

queue.push({ name: "Task 1" });
queue.push({ name: "Task 2" });
queue.push({ name: "Task 3" });
```

**Key Points:**

- Controls parallel execution of asynchronous tasks.
- Ensures efficient resource usage without overwhelming the system.
- Useful for I/O-heavy or CPU-bound tasks in Node.js applications.

## 59. What is the purpose of module.exports?

In Node.js, **`module.exports`** is an object used to **export functions, objects, or values** from a module so that they can be accessed in other modules using `require()`.

**Key Points:**

- Determines what a module **exposes to other modules**.
- By default, a module returns **an empty object** if nothing is exported.
- Can export **single values, multiple functions, objects, or classes**.

**Example 1: Exporting a function**

```javascript
// math.js
function add(a, b) {
  return a + b;
}
module.exports = add;

// app.js
const add = require("./math");
console.log(add(2, 3)); // Output: 5
```

**Example 2: Exporting multiple values**

```javascript
// utils.js
module.exports = {
  greet: function (name) {
    console.log(`Hello, ${name}`);
  },
  farewell: function (name) {
    console.log(`Goodbye, ${name}`);
  },
};

// app.js
const utils = require("./utils");
utils.greet("Alice"); // Output: Hello, Alice
utils.farewell("Bob"); // Output: Goodbye, Bob
```

**Summary:**
`module.exports` allows you to organize code into reusable modules and share functionality across your Node.js project.

## 60. What tools can be used to assure consistent code style?

Several tools can be used in Node.js to **ensure consistent code style and improve code quality**:

| Tool         | Purpose                                                                                                            |
| ------------ | ------------------------------------------------------------------------------------------------------------------ |
| **ESLint**   | Linting tool that detects **syntax errors, code smells, and potential bugs**.                                      |
| **Prettier** | Code formatter that enforces **consistent code formatting** across the project.                                    |
| **Jest**     | Testing framework that ensures **code correctness** and helps maintain quality through unit and integration tests. |

**Key Points:**

- Using these tools together helps **maintain readability, consistency, and reliability**.
- ESLint can be configured with **rules and plugins** specific to your project.
- Prettier can automatically format code on **save or commit**.
- Jest ensures that **changes do not break existing functionality**.

## 61. What is the difference between JavaScript and Node.js?

| Feature       | JavaScript                       | Node.js                                                  |
| ------------- | -------------------------------- | -------------------------------------------------------- |
| Type          | Programming language             | Runtime environment for executing JS outside the browser |
| Execution     | Runs in web browsers             | Runs on server or local machine using V8 engine          |
| Usage         | Frontend web development         | Backend/server-side development                          |
| Built-in APIs | Browser-specific APIs (DOM, BOM) | Node.js-specific APIs (file system, network, etc.)       |
| Compilation   | Interpreted by browser engines   | Compiled and executed by V8 engine                       |
| Environment   | Browser environment              | Server-side environment                                  |

**Summary:**

- **JavaScript** is the language.
- **Node.js** is a runtime that allows you to run JavaScript **outside the browser**, making server-side programming possible.

## 62. What is the difference between asynchronous and synchronous functions?

| Feature     | Synchronous Functions                    | Asynchronous Functions                         |
| ----------- | ---------------------------------------- | ---------------------------------------------- |
| Execution   | Blocks other code until completion       | Allows other code to run while waiting         |
| Flow        | Executed **step by step**                | Executed **in parallel or deferred**           |
| Use Case    | Simple, sequential tasks                 | I/O operations, API calls, database queries    |
| Scalability | Can slow down applications               | Enables scalable and non-blocking applications |
| Example     | Reading a file using `fs.readFileSync()` | Reading a file using `fs.readFile()`           |

**Key Points:**

- **Synchronous functions** block the main thread, making them unsuitable for high-concurrency tasks.
- **Asynchronous functions** use callbacks, promises, or `async/await` to handle tasks without blocking.
- Asynchronous behavior is **essential for scalable Node.js applications**, especially for I/O-heavy workloads.

## 63. What are the asynchronous tasks that should occur in an event loop?

In Node.js, the **event loop** handles asynchronous tasks to ensure **non-blocking execution**. Common asynchronous tasks include:

| Task Type                  | Description                                                                |
| -------------------------- | -------------------------------------------------------------------------- |
| **I/O Operations**         | File system operations, network requests, database queries, etc.           |
| **Timers**                 | Functions scheduled with `setTimeout()` or `setInterval()`.                |
| **Callback Functions**     | Functions passed as callbacks to handle asynchronous events or operations. |
| **Promises / Async-Await** | Tasks scheduled using promises that resolve asynchronously.                |

**Key Points:**

- Performing these tasks asynchronously allows Node.js to **handle many concurrent requests efficiently**.
- The **event loop** ensures that the main thread is **never blocked**, even when executing I/O or timers.
- Helps maintain **high performance and scalability** in server-side applications.

## 64. What is the order of execution in control flow statements?

In Node.js, the **order of execution** is determined by the **event loop** and the type of control flow statements used.

**Execution Flow:**

1. **Synchronous code** executes **first**, line by line.
2. **Asynchronous callbacks** (from I/O, timers, promises) are placed in **queues** and executed later by the event loop.
3. **Timers** (`setTimeout`, `setInterval`) are executed after the specified delay, in the **timers phase** of the event loop.
4. **I/O callbacks** are executed in the **poll phase**.
5. **`process.nextTick()` callbacks** are executed **before the next event loop tick**, giving them higher priority.
6. **Promise callbacks** (microtasks) are executed **after the current operation but before I/O events**.

**Summary Example:**

```javascript
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);
Promise.resolve().then(() => console.log("Promise"));
process.nextTick(() => console.log("Next Tick"));

console.log("End");
```

**Output:**

```javascript
Start
End
Next Tick
Promise
Timeout
```

**Key Points:**

- Node.js first executes synchronous code, then microtasks (nextTick, promises), followed by timers and I/O callbacks.
- Understanding this order is crucial for writing predictable asynchronous code.

## 66. Are there any disadvantages to using Node.js?

While Node.js offers many benefits, it also has some **disadvantages**:

| Disadvantage                                            | Explanation                                                                                                             |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Not suitable for CPU-intensive tasks**                | Node.js is single-threaded, so heavy computation can **block the event loop**, slowing down the application.            |
| **High memory usage per connection**                    | Each connection consumes memory, and applications with **many simultaneous connections** can quickly exhaust resources. |
| **Callback-heavy code** (without proper async handling) | Can lead to **callback hell**, making code harder to read and maintain.                                                 |
| **Immature ecosystem for certain use cases**            | Some libraries may not be as stable or mature as those in other environments.                                           |

**Key Points:**

- Ideal for **I/O-heavy, real-time applications** rather than CPU-bound tasks.
- Requires careful **memory and concurrency management** for high-load systems.
- Proper use of **worker threads or child processes** can mitigate some CPU-bound limitations.

## 67. What is the primary reason for using the event-based model in Node.js?

The **primary reason** for using an **event-based model** in Node.js is **performance and scalability**.

**Key Points:**

- Node.js uses **non-blocking I/O operations**, allowing the server to handle **many connections concurrently**.
- The **event loop** ensures that operations like network requests, file reads, and database queries **do not block the main thread**.
- Enables **efficient resource usage**, making Node.js ideal for **real-time and high-concurrency applications**.

**Example:**

```javascript
const http = require("http");

const server = http.createServer((req, res) => {
  res.end("Hello World");
});

server.listen(3000, () => {
  console.log("Server listening on port 3000");
});
```

- The server can handle multiple requests simultaneously without blocking, thanks to the event-driven architecture.

## 68. What is the difference between Node.js and Ajax?

| Feature           | Ajax                                                                                      | Node.js                                                                      |
| ----------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Type              | Client-side technology                                                                    | Server-side runtime environment                                              |
| Purpose           | Enables **asynchronous communication** between client and server without full page reload | Used for **building fast, scalable, and efficient server-side applications** |
| Use Case          | Updating parts of a webpage dynamically                                                   | Real-time applications like chat, online games, streaming                    |
| Execution         | Runs in the browser                                                                       | Runs on the server using the V8 JavaScript engine                            |
| Programming Model | Works via **XMLHttpRequest or Fetch API**                                                 | Uses **event-driven, non-blocking I/O** model                                |

**Summary:**

- **Ajax** is mainly for **client-side async interactions**.
- **Node.js** is for **server-side development**, handling requests and serving data efficiently.
- They often work together: Node.js serves the backend, while Ajax requests data asynchronously from the frontend.

## 69. What is the advantage of using Node.js?

Node.js offers several **advantages** that make it popular for modern web development:

| Advantage                  | Explanation                                                                                                                |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **High Performance**       | Built on the **V8 engine**, Node.js executes JavaScript very quickly.                                                      |
| **Scalability**            | Uses **event-driven, non-blocking I/O**, allowing it to handle a **large number of simultaneous connections** efficiently. |
| **Real-time Applications** | Ideal for **chat apps, online games, and streaming services** due to non-blocking architecture.                            |
| **Easy to Learn & Use**    | JavaScript is already widely known, making it easier for developers to adopt Node.js.                                      |
| **Full-Stack JavaScript**  | Developers can use **JavaScript on both frontend and backend**, simplifying development.                                   |
| **Large Ecosystem**        | Access to **NPM packages** for almost any functionality.                                                                   |

**Summary:**  
Node.js is **fast, scalable, and well-suited for real-time, high-concurrency applications**, making it a top choice for modern backend development.

## 70. Does Node run on Windows?

**Yes**, Node.js runs on Windows as well as other major operating systems.

**Key Points:**

- Node.js is a **cross-platform runtime environment**.
- Supported OS: **Windows, macOS, Linux**.
- Installation on Windows can be done via the **official Node.js installer** from [nodejs.org](https://nodejs.org).
- Once installed, Node.js can be used in **Command Prompt, PowerShell, or Windows Terminal**.

**Example: Verify Node.js installation on Windows**

```bash
node -v
npm -v
```

- These commands display the installed versions of Node.js and NPM.

## 71. Can you access DOM in Node?

**No**, you cannot access the DOM in Node.js.

**Key Points:**

- The **DOM (Document Object Model)** is a browser-specific API used to **manipulate HTML and XML documents**.
- Node.js is a **server-side runtime**, so it **does not run in a browser**.
- For DOM-like manipulation in Node.js, you can use **libraries such as `jsdom` or `cheerio`**, which simulate the DOM in a server environment.

**Example using `jsdom`:**

```javascript
const { JSDOM } = require("jsdom");

const dom = new JSDOM(`<body><p>Hello World</p></body>`);
console.log(dom.window.document.querySelector("p").textContent); // Output: Hello World
```

- This allows DOM-like operations in Node.js without an actual browser.

## 72. Why is Node.js quickly gaining attention from Java programmers?

**Node.js** is attracting Java programmers for several reasons:

**Key Points:**

- **High Performance:** Built on the **V8 engine**, Node.js executes JavaScript very quickly compared to traditional Java-based servers.
- **Scalability:** Its **event-driven, non-blocking I/O model** allows handling a large number of simultaneous connections efficiently.
- **Resource Efficiency:** Node.js consumes fewer resources for I/O-heavy tasks compared to Java, which can be **memory and CPU intensive**.
- **Real-time Applications:** Ideal for **chat apps, streaming, and online games** where low latency is critical.
- **Unified Language:** Developers can use **JavaScript for both frontend and backend**, simplifying development.

**Summary:**  
Java programmers see Node.js as a **faster, lightweight alternative** for building scalable, real-time, and high-performance server-side applications.

## 73. What are the challenges with Node.js?

While Node.js is powerful, it has some **challenges**:

| Challenge               | Explanation                                                                                                                                 |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Single-threaded**     | Node.js executes one task at a time, so **CPU-intensive tasks** can block the event loop and slow down the application.                     |
| **Relative newness**    | Node.js is newer than technologies like Java or PHP, so **less mature ecosystem** and **fewer resources** are available for some use cases. |
| **Memory limitations**  | Node.js is better suited for **lightweight, I/O-heavy applications**, and may not be ideal for **memory-intensive applications**.           |
| **Callback-heavy code** | Improper handling of asynchronous code can lead to **callback hell**, making maintenance harder.                                            |
| **Error handling**      | Asynchronous errors need careful management; unhandled errors can crash the application.                                                    |

**Summary:**  
Node.js is excellent for **I/O-heavy and real-time applications**, but requires careful **resource management** and proper **architecture** for CPU-bound or memory-heavy tasks.

## 74. What is "non-blocking" in Node.js?

In Node.js, **non-blocking** refers to the ability to **execute multiple tasks concurrently** without waiting for one task to finish before starting the next.

**Key Points:**

- Achieved through **asynchronous I/O operations**.
- Allows Node.js to **handle multiple requests simultaneously**.
- Prevents the **event loop from being blocked**, ensuring **high performance and scalability**.

**Example:**

```javascript
const fs = require("fs");

// Non-blocking read
fs.readFile("file.txt", "utf8", (err, data) => {
  if (err) throw err;
  console.log(data);
});

console.log("This runs before the file is read");
```

**Output:**

```javascript
This runs before the file is read
[Contents of file.txt]
```

- The log shows that Node.js does not wait for the file read to complete before moving on.

## 75. How does Node.js overcome the problem of blocking I/O operations?

Node.js addresses blocking I/O using an **event-driven, non-blocking I/O model**.

**Key Points:**

- **Asynchronous Callbacks:**

  - I/O operations are performed **asynchronously** using callbacks, allowing the main thread to continue processing other tasks while waiting for I/O to complete.

- **Single-threaded Event Loop:**

  - Node.js uses a **single-threaded event loop** to manage all asynchronous operations efficiently.
  - The event loop ensures that **multiple requests can be handled concurrently** without blocking the server.

- **High Scalability:**
  - Non-blocking I/O allows Node.js to handle **high volumes of simultaneous connections** efficiently.

**Example:**

```javascript
const fs = require("fs");

fs.readFile("file.txt", "utf8", (err, data) => {
  if (err) throw err;
  console.log("File content:", data);
});

console.log("Server continues processing other tasks...");
```

**Output:**

```javascript
Server continues processing other tasks...
File content: [Contents of file.txt]
```

- Node.js continues executing other code while waiting for the file read operation, demonstrating non-blocking behavior.

## 76. How can we use async/await in Node.js?

**`async/await`** is a modern syntax in Node.js to handle asynchronous operations more **readably** than using callbacks or promises alone.

**Key Points:**

- **`async` keyword:** Marks a function as asynchronous and ensures it **returns a promise**.
- **`await` keyword:** Pauses the execution of the function until the promise **resolves or rejects**.
- Requires functions that **return promises**.

**Example:**

```javascript
const fs = require("fs").promises;

async function readFileAsync() {
  try {
    const data = await fs.readFile("file.txt", "utf8");
    console.log("File content:", data);
  } catch (err) {
    console.error("Error reading file:", err);
  }
}

readFileAsync();
console.log("This runs before the file is read");
```

**Explanation:**

- `readFileAsync()` is marked as async, allowing use of await.
- `await fs.readFile()` pauses execution until the file is read.
  -Meanwhile, the rest of the code (like the last console.log) continues executing, demonstrating non-blocking behavior.

**Benefits:**

- Cleaner and more readable code compared to nested callbacks.
- Easier error handling using try/catch.

## 77. Why should you separate the Express app and server?

Separating the **Express application** and the **server** provides several benefits, including **testing, scalability, and flexibility**.

**Key Points:**

1. **Easier Testing**

   - By separating the app from the server, you can **test app logic independently**.
   - Makes it easier to **identify and fix bugs** without running the full server.
   - Compatible with tools like **Supertest** for route testing.

2. **Improved Scalability**

   - Allows you to **run multiple instances** of the app on different servers.
   - Helps **distribute load** and improves overall performance.

3. **Flexibility to Change Server**
   - Keeping app logic separate from server logic makes it easier to **switch to a different server** if necessary.
   - Avoids major code changes while changing the server environment.

**Example Structure:**

```javascript
// app.js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
    res.send('Hello World');
});

module.exports = app;

// server.js
const app = require('./app');
const PORT = 3000;

app.listen(PORT, () => {
    console.log(`Server running on port ${PORT}`);
});

**Explanation:**

- `app.js` contains all routes and middleware.
- `server.js` handles listening on a port, separating environment concerns from app logic.
```

## 78. Explain the concept of stub in Node.js

In Node.js, a **stub** is a function used as a **placeholder for a more complex function**, commonly in **unit testing**.

**Key Points:**

- Stubs **replace real functions** with simplified versions.
- They **return predetermined values** to make tests **predictable and consistent**.
- Useful for **isolating code** under test without relying on external dependencies (like databases or APIs).
- Often used with testing frameworks like **Sinon.js**.

**Example Using Sinon.js:**

```javascript
const sinon = require("sinon");

// Original function
function getUser(id) {
  // Imagine this calls a database
  return { id, name: "Alice" };
}

// Stub the function
const stub = sinon.stub().returns({ id: 1, name: "Stub User" });

console.log(stub()); // Output: { id: 1, name: 'Stub User' }
```

**Summary:**

- Stubs help create controlled testing environments.
- They allow testing specific parts of your code without invoking the real implementations.

## 79. What is the framework that is used majorly in Node.js today?

While several frameworks exist for Node.js, the **most popular frameworks today** are:

| Framework      | Description                                                                                                                                   |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Express.js** | Minimalist, fast, and widely used framework for building **web applications and APIs**. Highly flexible with a large ecosystem of middleware. |
| **Koa.js**     | Lightweight and modern framework developed by the Express team. Uses **async/await** by default for **cleaner asynchronous code**.            |

**Key Points:**

- **Express** is the most widely adopted due to **simplicity, middleware support, and community resources**.
- **Koa** is preferred for projects needing **modern async handling and modular architecture**.
- Other frameworks exist (Hapi, NestJS, Fastify), but **Express dominates most Node.js projects**.

## 80. What are the security implementations that are present in Node.js?

Node.js provides several **security mechanisms** to protect applications and data:

| Security Feature              | Description                                                                                                                |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Sandboxed Environment**     | Node.js can run code in a **restricted environment**, preventing malicious code from accessing sensitive system resources. |
| **TLS/SSL Encryption**        | Supports **TLS/SSL** for encrypting data in transit, ensuring secure communication and preventing eavesdropping.           |
| **Secure Package Management** | Using **npm audit** and vetted packages to avoid vulnerabilities from third-party modules.                                 |
| **Environment Variables**     | Sensitive data like API keys and passwords can be stored in **environment variables** rather than hardcoded.               |
| **Helmet and Middleware**     | Security middleware like **Helmet** can be used in Express apps to **set HTTP headers securely**.                          |

**Summary:**

- Node.js provides **runtime-level security** and **library-based measures** to help developers secure applications.
- Proper implementation of these features is crucial for **preventing attacks and protecting data**.

## 81. What is Libuv?

**Libuv** is a core library used by Node.js to handle **asynchronous I/O operations efficiently**.

**Key Points:**

- Provides **cross-platform support** for asynchronous operations like **file system access, networking, and timers**.
- Implements the **event loop** in Node.js, enabling **non-blocking I/O**.
- Abstracts low-level OS operations, making Node.js **consistent across different operating systems**.
- Written in **C** and used under the hood by Node.js to manage **concurrent operations** without blocking the main thread.

**Summary:**  
Libuv is essential for Node.js to provide **high-performance, event-driven, and non-blocking I/O capabilities**.

## 82. What are global objects in Node.js?

**Global objects** in Node.js are **available in all modules** without needing to explicitly import or require them.

**Key Points:**

- Accessible anywhere in your Node.js application.
- Commonly used global objects include:

| Object           | Description                                                                                                           |
| ---------------- | --------------------------------------------------------------------------------------------------------------------- |
| **`process`**    | Provides information and control over the current Node.js process (e.g., environment variables, exiting the process). |
| **`console`**    | Used for logging and debugging (e.g., `console.log()`, `console.error()`).                                            |
| **`Buffer`**     | Handles binary data in Node.js (e.g., reading files, network streams).                                                |
| **`__dirname`**  | Represents the directory name of the current module.                                                                  |
| **`__filename`** | Represents the full file path of the current module.                                                                  |

**Summary:**  
Global objects simplify Node.js development by providing **built-in tools and access** without the need to import modules.

## 83. Why is assert used in Node.js?

The **`assert`** module in Node.js is primarily used for **writing tests** and verifying that code behaves as expected.

**Key Points:**

- Provides **assertion methods** to test **conditions and values**.
- Throws an **error** if the assertion fails, helping identify bugs early.
- Useful in **unit tests** and **simple verification** during development.

**Example:**

```javascript
const assert = require('assert');

const sum = (a, b) => a + b;

assert.strictEqual(sum(2, 3), 5); // Passes
assert.strictEqual(sum(2, 2), 5); // Throws AssertionError

**Summary:**

- assert is a `built-in Node.js module` for `verifying assumptions` in code.
- Helps developers `catch errors early` and write `reliable tests`.
```

## 84. Why is ExpressJS used?

**ExpressJS** is a popular framework for Node.js, widely used for building **web applications and APIs**.

**Key Points:**

- **Minimal and Flexible:** Provides a **lightweight framework** while allowing developers to structure applications as needed.
- **Routing and Middleware:** Simplifies handling **HTTP requests, routes, and middleware**.
- **Active Community:** Large ecosystem of **plugins, tutorials, and support**, making development easier.
- **Performance:** Fast and efficient due to **Node.js non-blocking architecture**.
- **Scalable:** Can be used for **small projects and enterprise-level applications**.

**Summary:**  
ExpressJS is chosen for **its simplicity, flexibility, and robust community support**, making it ideal for developing **web applications, REST APIs, and server-side applications** in Node.js.

## 85. What is the use of the connect module in Node.js?

The **Connect module** in Node.js is a **middleware framework** that provides a foundation for building web applications and APIs. It is lightweight and extensible, and many frameworks (including **ExpressJS**) are built on top of Connect.

### Key Uses:

- **Middleware Handling:** Provides a way to manage and execute multiple middleware functions in the request/response cycle.
- **Error Handling:** Allows adding custom or prebuilt **error-handling middleware** to catch and process errors.
- **Cookie Parsing:** Supports middleware for **parsing cookies** from request headers.
- **Session Management:** Enables **session middleware** for handling user sessions.
- **Reusability:** Middleware functions are modular, reusable, and can be composed for different applications.

### Example:

```js
const connect = require("connect");
const app = connect();

// Example middleware
app.use((req, res, next) => {
  console.log("Request received: " + req.url);
  next();
});

app.use((req, res) => {
  res.end("Hello from Connect!");
});

app.listen(3000);
```

### **Summary:**

The Connect module is used to manage middleware efficiently in Node.js applications, providing a foundation for features like routing, session handling, cookies, and error management.

## 86. What's the difference between 'front-end' and 'back-end' development?

### **Front-End Development (Client-Side):**

- Focuses on the **visual and interactive part** of a web application that users directly interact with.
- Involves designing and building the **UI/UX**.
- Technologies used:
  - **HTML, CSS, JavaScript**
  - Frameworks/Libraries: **React, Angular, Vue.js**
- Responsibilities:
  - Creating responsive layouts.
  - Managing user interactions.
  - Ensuring good performance across devices and browsers.

### **Back-End Development (Server-Side):**

- Focuses on the **logic, database, and server-side operations** of an application.
- Handles data storage, security, and application performance.
- Technologies used:
  - Languages: **Node.js, PHP, Python, Java, Ruby**
  - Databases: **MySQL, PostgreSQL, MongoDB**
  - Frameworks: **Express.js, Django, Spring Boot, Laravel**
- Responsibilities:
  - Implementing APIs.
  - Managing authentication & authorization.
  - Handling business logic and database queries.

### **Key Differences:**

| Aspect      | Front-End (Client-Side)                  | Back-End (Server-Side)                    |
| ----------- | ---------------------------------------- | ----------------------------------------- |
| Focus       | User interface & experience              | Server logic, database, and APIs          |
| Languages   | HTML, CSS, JavaScript                    | Node.js, PHP, Python, Java, Ruby, etc.    |
| Frameworks  | React, Angular, Vue.js                   | Express, Laravel, Django, Spring Boot     |
| Interaction | Directly with the user                   | Processes requests from front-end         |
| Goal        | Make app visually appealing & responsive | Make app secure, scalable, and functional |

### **Summary:**

- **Front-end developers** build the part of the app users see and interact with.
- **Back-end developers** build the behind-the-scenes logic, databases, and servers.
- Together, they create a **full-stack application**.

## 87. What are LTS releases of Node.js?

**LTS** stands for **Long-Term Support**.  
In Node.js, LTS releases are versions that receive **critical bug fixes, security updates, and performance improvements** for an extended period — typically **30 months** from their release date.

### **Key Points about LTS Releases:**

- Marked as **"Active LTS"** for 18 months (receives regular bug fixes, updates, and improvements).
- Then moved to **"Maintenance LTS"** for another 12 months (only critical fixes and security patches).
- LTS releases are intended for **production environments** because of their stability and long support.
- Non-LTS versions (Current releases) are intended for testing new features but are **not recommended for production**.

### **Example of Node.js Release Schedule:**

| Release Type | Support Duration | Purpose                       |
| ------------ | ---------------- | ----------------------------- |
| **LTS**      | 30 months        | Stable, production-ready      |
| **Current**  | ~6 months        | Latest features, experimental |

### **Summary:**

- **Use LTS versions for production apps** (ensures stability & security).
- **Use Current versions for experimenting with the latest features**.

## 88. What do you understand about ESLint?

**ESLint** is a popular **open-source linting tool** for JavaScript and Node.js applications.  
It helps developers **analyze code, find errors, and enforce coding standards** to maintain clean, consistent, and bug-free codebases.

### **Key Features of ESLint:**

- Detects **syntax errors** and **potential bugs**.
- Enforces **coding style rules** (indentation, semicolons, quotes, etc.).
- Supports **custom rules** and **plugins**.
- Can automatically **fix many issues** with `--fix`.
- Integrates with editors (VS Code, WebStorm, etc.) for real-time feedback.

### **Example Usage:**

```bash
# Install ESLint locally
npm install eslint --save-dev

# Initialize ESLint config
npx eslint --init

# Lint a file
npx eslint app.js
```

Example output might show unused variables, missing semicolons, or undefined variables.

### **Why Use ESLint?**

- Maintains consistent coding style across teams.
- Reduces bugs by catching issues early.
- Improves code quality and readability.
- Essential in large projects and when multiple developers collaborate.

### **Summary:**

👉 ESLint is not just an error-checking tool — it’s a code quality enforcer that ensures best practices and standards are followed throughout your JavaScript/Node.js project.

`⚡ Interview Tip:` If they ask _“How does ESLint help in team projects?”_, `Answer:`  
✅ It ensures **everyone writes code in the same style**, reduces merge conflicts, and improves maintainability.

## 89. Define the concept of the test pyramid. Please explain the process of implementing them in terms of HTTP APIs.

The **test pyramid** is a concept in software testing that illustrates the **ideal balance of automated tests** in a project.  
It emphasizes having **many small and fast unit tests**, fewer integration tests, and even fewer end-to-end (E2E) tests.

### **The Three Layers of the Test Pyramid:**

1. **Unit Tests (Base of the Pyramid)**
   - Test small, isolated pieces of code (e.g., functions, controllers).
   - Run very fast and give quick feedback.
   - Example: Testing an API route handler without hitting the database.
2. **Integration Tests (Middle Layer)**
   - Test interactions between modules or services.
   - Example: Test if an API endpoint properly integrates with the database or external service.
3. **End-to-End (E2E) Tests (Top of the Pyramid)**
   - Test the system as a whole, simulating real-world scenarios.
   - Example: Sending an HTTP request to the API and checking if the correct response is returned after processing.

---

### **Implementing the Test Pyramid for HTTP APIs**

1. **Unit Tests (Majority)**

   - Test **controllers, validators, and services** in isolation.
   - Use mocking/stubbing for dependencies.

   ```javascript
   // Example: Jest unit test for a controller
   const requestHandler = require("../controllers/userController");
   const userService = require("../services/userService");

   test("should return user data", async () => {
     userService.getUser = jest.fn().mockResolvedValue({ id: 1, name: "John" });
     const req = { params: { id: 1 } };
     const res = { json: jest.fn() };

     await requestHandler.getUser(req, res);
     expect(res.json).toHaveBeenCalledWith({ id: 1, name: "John" });
   });
   ```

2. **Integration Tests**

- Test if endpoints work correctly with the database or services.
- Run with a test database.

```javascript
const request = require("supertest");
const app = require("../app");

describe("GET /users/:id", () => {
  it("should return user from DB", async () => {
    const res = await request(app).get("/users/1");
    expect(res.statusCode).toBe(200);
    expect(res.body).toHaveProperty("name");
  });
});
```

3. **End-to-End (E2E) Tests**

- Simulate full user flows with real DB, API, and possibly UI.
- Example: Creating a user and then fetching it.

```javascript
describe("E2E: User API", () => {
  it("should create and retrieve a user", async () => {
    const createRes = await request(app).post("/users").send({ name: "Alice" });

    const getRes = await request(app).get(`/users/${createRes.body.id}`);
    expect(getRes.body.name).toBe("Alice");
  });
});
```

### **Key Benefits of Following the Test Pyramid**

- Faster feedback from unit tests.
- Confidence in API correctness with integration tests.
- Real-world validation with fewer but important E2E tests.
- Balanced test suite → reduces flakiness and speeds up CI/CD pipelines.

### **Summary**

`👉 The test pyramid ensures a balanced testing strategy:`

- Many unit tests for speed & reliability.
- Some integration tests for correctness.
- Few E2E tests for real-world assurance.
- In HTTP APIs, this means starting small (endpoint logic), moving up to DB/API integration, and finishing with end-user scenarios.

`⚡ Interview tip:` If asked _“Why fewer E2E tests?”_ → `Answer:` Because they’re **slower, costlier, and more fragile**, so we rely more on **unit and integration tests** for speed.

### 90. How does Node.js handle the child threads?

Node.js is `single-threaded` by default (using the event loop model), but it provides ways to handle `child threads or parallel execution` through:

1. **`child_process` module**

- Node.js allows creating `child processes` (not threads) that run independently.
- You can use methods like:
  - `spawn()` → for starting a new process.
  - `exec()` → for executing shell commands.
  - `fork()` → for creating new Node.js instances that can communicate with the parent process via messaging.
- Each child process runs in its own memory space but can `communicate with the parent using IPC (Inter-Process Communication)`.

**Example:**

```javascript
const { fork } = require("child_process");

const child = fork("child.js");

child.on("message", (msg) => {
  console.log("Message from child:", msg);
});

child.send({ task: "processData" });
```

2. **Worker Threads (`worker_threads` module)**

- Since Node.js v10.5.0 (stable in v12+), you can use `Worker Threads` to run JavaScript in parallel threads within the same process.
- Unlike `child_process`, workers share memory using `SharedArrayBuffer`.

**Example:**

```javascript
const { Worker } = require("worker_threads");

const worker = new Worker("./worker.js", { workerData: { number: 5 } });

worker.on("message", (result) => {
  console.log("Result from worker:", result);
});
```

3. **Libuv Thread Pool**

- Internally, Node.js uses `Libuv` which has a thread pool (default size = 4) to handle expensive tasks like file system operations, DNS lookups, and crypto operations.
- This allows Node.js to delegate heavy work to background threads, so the event loop remains non-blocking.

**✅ In short:**

- Node.js doesn’t use threads like Java or C# by default.
- It achieves concurrency via `event loop + Libuv thread pool`.
- For explicit parallelism, developers can use `child_process` or `worker_threads`.
