**Round-robin load balancing** is a simple method of distributing client requests across a group of servers in a sequential, cyclic order. ==Each new request is assigned to the next server in the list, looping back to the start once it reaches the end==. This approach helps distribute workloads evenly, assuming each request has a similar processing time.

### Example:
If there are three servers (A, B, and C), requests would be assigned in this order: A → B → C → A → B → C, and so on.

### Key Points:
- **Simplicity**: Easy to implement and configure.
- **Equal distribution**: Each server gets an equal number of requests over time.
- **Best suited for**: Workloads where each request has similar processing demands.

It’s commonly used in applications where requests are similar, but may be less effective if servers have different capacities or if request processing times vary significantly.