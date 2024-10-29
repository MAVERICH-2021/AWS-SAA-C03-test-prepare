## 1. **Encryption at Rest:**
- **Definition**: Encryption at rest protects data stored on a physical or virtual medium (e.g., disks, databases, file systems).
- **Purpose**: It ensures that if someone gains unauthorized access to the underlying storage or backups (e.g., by stealing a disk), they cannot read the data without the decryption key.

- **Examples in AWS**:
  - **S3**: Data can be encrypted using AWS-managed keys (SSE-S3) or ==customer-managed keys (SSE-KMS)==.
  - **EBS (Elastic Block Store)**: When you enable encryption, your EBS volumes are encrypted at rest.
  - **RDS Databases**: Data stored in databases is encrypted at rest, including backups, snapshots, and logs.

**Key Aspects**:
- The encryption and decryption processes are handled automatically by AWS services if enabled.
- Data remains encrypted until accessed through an authorized request, which decrypts it on-the-fly.

---

## 2. **Encryption in Transit:**
- **Definition**: Encryption in transit protects data as it moves between systems, services, or networks.
- **Purpose**: It ensures that data transmitted over a network cannot be intercepted or read by unauthorized users (e.g., man-in-the-middle attacks).

- **Examples in AWS**:
  - **HTTPS/SSL**: Data transferred to and from S3 buckets is encrypted via HTTPS.
  - **TLS (Transport Layer Security)**: AWS services like API Gateway and RDS use TLS for secure communications between clients and servers.
  - **VPC Peering or Private Links**: Data traveling between VPCs over the AWS network can use encrypted transit options.

**Key Aspects**:
- Encryption in transit uses protocols like **SSL/TLS** to secure data while it’s being transmitted.
- Once the data reaches its destination, it can be decrypted (if needed) for further processing.

---

### **How They Work Together:**
- **Encryption at rest** ensures the data is secure when stored, even if storage devices are compromised.
- **Encryption in transit** ensures the data is protected while being transferred between systems or across networks.

Together, these mechanisms provide **end-to-end data protection**, covering both storage and movement phases.

