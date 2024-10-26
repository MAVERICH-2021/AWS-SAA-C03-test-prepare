### Stactic IP

Amazon **Network Load Balancer (NLB)** allows you to associate **static IP addresses** with your load balancer, which ensures predictable endpoints for incoming traffic. Here's how the relationship works:

1. **Static IP for Stability:** NLB provides each availability zone with a **static IP**. This is useful for clients that need to whitelist IPs, such as firewalls or DNS configurations, ensuring the IPs won’t change even if the underlying resources are updated.

3. **Low-Latency Routing with Static IPs:** Since NLB operates at **Layer 4 (transport layer)**, using static IPs ensures direct, efficient routing with minimal delays, making it ideal for latency-sensitive applications.

---

