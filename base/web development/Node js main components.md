Node.js has several core components that form the foundation for its functionality.

## V8 Javascript Engine

V8 is the JavaScript engine developed by Google, originally for the Chrome browser. Node.js uses V8 to execute JavaScript code on the server. It **compiles JavaScript into machine code**, enabling high-performance execution. V8 is responsible for the fast execution of JavaScript, which is one of the reasons Node.js is so efficient.

## Libuv

**Libuv is a C library** that provides Node.js with its event-driven, asynchronous I/O model.
It **handles asynchronous events** (like file system operations, network requests, timers, etc.) and **enables Node.js to perform non-blocking operation**s. Libuv is also responsible for managing the event loop and thread pool.

## Event loops

The event loop is a key part of Node.js’s non-blocking architecture. It **continuously checks for I/O operations and processes them when they are ready**, without blocking the execution of other tasks. It allows Node.js to handle multiple tasks at the same time (asynchronously) by managing callbacks and I/O events. This makes Node.js highly scalable and suitable for I/O-heavy applications.

## Node.js APIs (Core Modules)

Node.js comes with **built-in modules**, which provide key functionalities for developing applications. These modules allow interaction with the operating system, file systems, networking, etc.
**Examples**
- `http`: For creating HTTP servers.
- `fs`: For interacting with the file system (reading/writing files).
- `path`: For working with file and directory paths.
- `crypto`: For handling cryptography and encryption.
- `events`: For handling and emitting events.
- `stream`: For handling data streaming operations.

## NPM 

NPM is the default package manager for Node.js. It allows developers to install, manage, and share third-party libraries and modules.

## C++ bindings
Some parts of Node.js are written in C++ to interface with the system's underlying operating system and hardware. **C++ bindings are used to implement performance-critical parts** of Node.js and **to interface with lower-level APIs**, such as file I/O and networking.

## Worker threads

Although Node.js is single-threaded, Worker Threads **enable running multiple JavaScript threads in parallel**. Worker Threads are used for CPU-intensive tasks or scenarios that require parallel execution, such as data processing or calculations, without blocking the main event loop.

References:
1. [[Node js]]
2. [[Event Loop]]
3. [[Libuv]]