## 251-275
### 251
An Amazon EC2 instance is located in a private subnet in a new VPC. This subnet does not have outbound internet access, but the EC2 instance
needs the ability to download monthly security updates from an outside vendor.
What should a solutions architect do to meet these requirements?
A. Create an internet gateway, and attach it to the VPC. Configure the private subnet route table to use the internet gateway as the default
route.
B. Create a NAT gateway, and place it in a public subnet. Configure the private subnet route table to use the NAT gateway as the default route.
C. Create a NAT instance, and place it in the same subnet where the EC2 instance is located. Configure the private subnet route table to use
the NAT instance as the default route.
D. Create an internet gateway, and attach it to the VPC. Create a NAT instance, and place it in the same subnet where the EC2 instance is
located. Configure the private subnet route table to use the internet gateway as the default route.
### 252
### 253
### 254
### 255
### 256
### 257
### 258
### 259
### 260
### 261
### 262
### 263
### 264
### 265
### 266
### 267
### 268
### 269
### 270
### 271
### 272
### 273
### 274
### 275

## 276-300
### 276
### 277
## 301-325
## 326 - 350

### 326


### 350
A company uses a 100 GB Amazon RDS for Microsoft SQL Server Single-AZ DB instance in the us-east-1 Region to store customer transactions.
The company needs high availability and automatic recovery for the DB instance.
The company must also run reports on the RDS database several times a year. The report process causes transactions to take longer than usual to
post to the customers’ accounts. The company needs a solution that will improve the performance of the report process.
Which combination of steps will meet these requirements? (Choose two.)
A. Modify the DB instance from a Single-AZ DB instance to a Multi-AZ deployment.
B. Take a snapshot of the current DB instance. Restore the snapshot to a new RDS deployment in another Availability Zone.
C. Create a read replica of the DB instance in a different Availability Zone. Point all requests for reports to the read replica.
D. Migrate the database to [[RDS#RDS Custom]].
E. Use RDS Proxy to limit reporting requests to the maintenance window.
Correct Answer:AC