| **Feature**      | **ALB (Application Load Balancer)**  | **NLB (Network Load Balancer)** |
| ---------------- | ------------------------------------ | ------------------------------- |
| OSI Layer        | Layer 7 (Application)                | Layer 4 (Transport)             |
| Protocols        | HTTP, HTTPS, WebSockets              | TCP, UDP, TLS                   |
| Routing Logic    | Path-based, Host-based, Header-based | IP and Port-based               |
| Latency          | Higher latency                       | Low latency                     |
| Use Case         | Web apps, microservices              | Low-latency, gaming, IoT        |
| Target Types     | EC2, IPs, containers, Lambda         | EC2, IPs                        |
| IP Address       | DNS-based                            | Static IP                       |
| Health Checks    | Application-level (HTTP/HTTPS)       | Transport-level (TCP)           |
| Session Handling | Sticky sessions via cookies          | Session affinity (IP-based)     |
