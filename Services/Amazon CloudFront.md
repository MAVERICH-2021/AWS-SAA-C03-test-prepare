> integrated with AWS Shield for DDoS protection.


Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content


- **Global Content Delivery**: **Amazon CloudFront** is a global **content delivery network (CDN)** optimized to reduce latency by caching content at edge locations closer to users worldwide. This ensures faster delivery of both **static and dynamic content**.
    
- **Single Origin with Low Latency**: Using the **ALB as the origin** for CloudFront ensures that CloudFront retrieves dynamic content from the backend only when needed. Static content, such as images and CSS files, is cached at edge locations, reducing the load on the ALB and minimizing response times for users.
    
- **HTTPS Offloading**: CloudFront handles HTTPS termination at the edge, improving security and performance by reducing the overhead on the backend infrastructure.
    
- **Cache Behavior for Dynamic Content**: CloudFront can intelligently cache dynamic content using **cache-control headers** and **TTL (time-to-live)** settings, further enhancing performance. Even when dynamic content cannot be fully cached, CloudFront ensures optimized delivery with lower latency than accessing the origin server directly.


Q: 缓存有效性问题  **When to Cache Dynamic Content?**

- **Best for Content with Moderate Variability**: Content that doesn’t change on every request but can remain valid for a short time (e.g., stock prices, API responses).
- **Use Case Examples**: News articles updated every few minutes, weather summaries, or personalized but infrequent data.