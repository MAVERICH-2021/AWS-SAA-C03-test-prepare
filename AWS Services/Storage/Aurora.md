# Replica

## Endpoint
### reader endpoint
A _reader endpoint_ for an Aurora DB cluster provides connection-balancing support for read-only connections to the DB cluster. Use the reader endpoint for read operations, such as queries. By processing those statements on the read-only Aurora Replicas, this endpoint reduces the overhead on the primary instance. It also helps the cluster to scale the capacity to handle simultaneous `SELECT` queries, proportional to the number of Aurora Replicas in the cluster. Each Aurora DB cluster has one reader endpoint.

If the cluster contains one or more Aurora Replicas, the reader endpoint balances each connection request among the Aurora Replicas. In that case, you can only perform read-only statements such as `SELECT` in that session. If the cluster only contains a primary instance and no Aurora Replicas, the reader endpoint connects to the primary instance. In that case, you can perform write operations through the endpoint.

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Endpoints.Reader.html

### Custom endpoints

- **Custom endpoints** allow you to specify which nodes should handle the traffic for a specific workload. You can create a **custom endpoint** in Aurora that targets just the three Aurora Replicas that are configured for the reporting queries. This allows you to direct the workload to specific replicas based on your custom configuration and requirements (e.g., different compute and memory specifications).
    
- With **custom endpoints**, you can control which nodes handle the workload without relying on the automatic distribution provided by the **reader endpoint**, which would route traffic across all Aurora Replicas indiscriminately.