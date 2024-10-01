Distributed transactions involve **coordinating multiple services or databases** to ensure that a series of **operations either all succeed or all fail**, preserving the consistency of the system. This is particularly important in microservices architectures where different services may handle different parts of a business process. Distributed transaction patterns help manage this complexity and maintain data integrity.

## Two-Phase Commit 2PC

### How It Works:

- **Phase 1 (Prepare)**: The transaction coordinator **sends a prepare request to all participants**. Each participant performs any necessary checks and prepares to commit the transaction but does not yet commit it. The participant then sends a response back (ready or not ready).
- **Phase 2 (Commit/Rollback)**: If all **participants respond with "ready,"** the coordinator sends a commit message. If **any participant fails, the coordinator sends a rollback message**, and all participants roll back their part of the transaction.
#### Pros:
- Guarantees consistency across distributed systems.
- Ensures atomicity (all-or-nothing).
#### Cons:
- **Blocking**: If a participant or coordinator fails, other participants may remain in a blocked state, waiting for a decision.
- Can lead to **performance bottlenecks** in high-latency systems.
- Not highly scalable due to centralized coordination.


## Saga Pattern

The **Saga Pattern** is an alternative to 2PC and is widely used in microservices architectures. It breaks down a large transaction into a series of smaller, independent transactions across different services, with compensation mechanisms for rollback.
### How It Works:

- A **saga** is a **sequence of local transactions** where each transaction updates the state within a service. If any transaction in the sequence fails, the previously completed transactions are undone by executing **compensating transactions**.

There are two main types of sagas:

- **Choreography**: Each service involved in the saga **listens for events and triggers** its local **transaction or compensation** based on the outcome of the previous step.
- **Orchestration**: A central **orchestrator** manages the saga and tells each service what action to take (whether to proceed or roll back).
#### Pros:

- Avoids the blocking and coordination overhead of 2PC.
- Decentralized and more scalable.
- Works well in highly distributed environments, like microservices.
#### Cons:

- Requires compensating transactions to undo completed work, which may add complexity.
- Rolling back might not be possible in some real-world scenarios (e.g., sending an email can’t be undone).

