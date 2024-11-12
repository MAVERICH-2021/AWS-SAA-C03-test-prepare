Application Layer - HTTP

> integrated with AWS Shield for DDoS protection.

Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content


- **Global Content Delivery**: **Amazon CloudFront** is a global **content delivery network (CDN)** optimized to reduce latency by caching content at edge locations closer to users worldwide. This ensures faster delivery of both **static and dynamic content**.
    
- **Single Origin with Low Latency**: Using the **ALB as the origin** for CloudFront ensures that CloudFront retrieves dynamic content from the backend only when needed. Static content, such as images and CSS files, is cached at edge locations, reducing the load on the ALB and minimizing response times for users.
    
- **HTTPS Offloading**: CloudFront handles HTTPS termination at the edge, improving security and performance by reducing the overhead on the backend infrastructure.
    
- **Cache Behavior for Dynamic Content**: CloudFront can intelligently cache dynamic content using **cache-control headers** and **TTL (time-to-live)** settings, further enhancing performance. Even when dynamic content cannot be fully cached, CloudFront ensures optimized delivery with lower latency than accessing the origin server directly.


Q: 缓存有效性问题  **When to Cache Dynamic Content?**

- **Best for Content with Moderate Variability**: Content that doesn’t change on every request but can remain valid for a short time (e.g., stock prices, API responses).
- **Use Case Examples**: News articles updated every few minutes, weather summaries, or personalized but infrequent data.

#  signed URLs & signed cookies
**Amazon CloudFront signed URLs** and **signed cookies** are methods to control access to content distributed through Amazon CloudFront, ensuring that only authorized users can view or download restricted content. Both methods involve providing access to specific users for a limited time or under specific conditions. Let’s look at each in detail.

---

### 1. **CloudFront Signed URL**

A *CloudFront signed URL* is a unique URL with an embedded signature, granting temporary access to restricted files or objects on CloudFront for a specific user. It’s commonly used when you need to:

- **Grant access to individual files**: Signed URLs are typically used for single files, such as videos, documents, or images.
- **Control access time and permissions**: Signed URLs allow you to specify a time range or expiration date for access to the content.
- **Embed links for specific users**: This is useful when you want only certain people to view or download a file, perhaps as part of a subscription, pay-per-view, or premium content model.

#### How It Works

- **Signing**: The signed URL is generated by encrypting URL parameters with a private key associated with your CloudFront key pair.
- **Validation**: When a user requests the file, CloudFront checks the URL signature and expiration time. If valid, it allows access; otherwise, access is denied.

**Example Use Cases**:
   - Granting temporary access to a video file for a rented streaming service.
   - Providing a download link to a specific document for a limited period.

---

### 2. **CloudFront Signed Cookie**

A *CloudFront signed cookie* provides temporary access to multiple files within a restricted section of your website rather than a single file. Signed cookies are used when:

- **Granting access to multiple files**: If you want users to access an entire directory or a group of files without creating individual signed URLs for each file, a signed cookie is more convenient.
- **Session-based access**: Signed cookies work well when a user’s session should grant them access to multiple resources, like browsing an entire catalog, gallery, or playlist.
- **Controlling time-based access**: Like signed URLs, signed cookies allow you to set expiration times for access.

#### How It Works

- **Setting Cookies**: You generate the signed cookies and set them in the user’s browser. The signed cookies contain authentication details and expiration information.
- **Access Control**: When the user requests files from CloudFront, CloudFront checks the signed cookies. If the cookies are valid, it allows access; otherwise, access is denied.

**Example Use Cases**:
   - Allowing access to all images in a secure photo gallery for a specific time.
   - Granting a subscriber access to an entire playlist of videos within a premium section.

---

### **Choosing Between Signed URLs and Signed Cookies**

- **Use Signed URLs**: When access is required for **a single file** or object. For example, you might provide a unique, expiring link to a downloadable eBook or a single video.
- **Use Signed Cookies**: When access is required for **multiple files or an entire directory** of resources. This is useful for authenticated users who should have temporary access to multiple restricted resources within a browsing session.

In summary, **signed URLs** are great for secure, limited access to individual files, while **signed cookies** offer a convenient way to grant session-based access to multiple files, making both options essential tools for secure content delivery with Amazon CloudFront.