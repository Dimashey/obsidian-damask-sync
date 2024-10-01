[[Node js|Node.js]] is great for many tasks, but there are some areas where it is not the best choice. Here are the tasks for which Node.js is not well-suited:

## 1. CPU intensive operating

Node js is designed for I/O - bound applications, not for CPU-bound tasks like heavy computations. 

It is single-threaded event-loop can become a bottleneck during CPU-intensive operations, causing delays and poor performance for other tasks.

**Examples**:
1. Image and video operations
2. Complex mathematical computations 
3. Real-time rendering or simulation

## 2. Multi-threaded, Parallel Processing Applications

Nodejs is single-threaded by default, which makes it less efficient for tasks that requires heavy parallel processing or multi-threading 

***Examples*: 
1. High-performance computation applications
2. Advances machine learning algorithms 
3. Real-time data analytics systems

## 3. Applications Requiring Stable Performance under High CPU Load

- Applications that need to maintain stable, predictable performance even under heavy CPU load

**Example**
1. High-frequency trading systems
2. 3D rendering engines
3. Video game engines


In summary, NodeJs excels at handling I/O - bound tasks with low CPU loads, such web servers, real-time applications, and microservices. 



