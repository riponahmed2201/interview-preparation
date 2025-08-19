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
