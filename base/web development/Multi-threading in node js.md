Node.js provides ways to achieve multi-threading through the use of **Worker Threads** and the **Cluster module**.

## Worker Threads Module

The Worker Threads module **allows you to create and manage multiple JavaScript threads**, enabling parallel execution of code. 

This is useful for CPU-intensive tasks, as it allows you to run tasks in the background without blocking the main event loop. Worker Threads are **suitable for heavy computation** tasks that need to run in parallel, such as data processing, encryption, or image manipulation.

Each worker thread **runs in its own isolated context**, meaning they don’t share memory with the main thread. However, t**hreads can communicate with each other using message-passing**.

## Cluster Module

The **Cluster** module allows you to **run multiple instances of the Node.js** application in separate processes, **utilizing multiple CPU cores**. Each instance (called a worker) runs its own event loop, enabling efficient scaling of applications across all available CPU cores.

The Cluster module is ideal **for scaling I/O-bound applications** that need to handle many concurrent connections but **don’t require shared memory or heavy CPU-bound computation**.

s When the **Cluster** module is used, the **master process spawns worker processes**. Each worker listens on the same port and handles incoming requests. The m**aster process distributes incoming client requests among the workers**.



References:
1. [[Node js]]
2. [[Node js main components]]
