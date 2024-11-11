# Routine Strategy
## Multivalue answer routing
return multiple values, such as IP addresses for your web servers, in response to DNS queries. You can specify multiple values for almost any record, but multivalue answer routing also lets you check the health of each resource, so Route 53 returns only values for healthy resources. It's not a substitute for a load balancer, but the ability to return multiple health-checkable IP addresses is a way to use DNS to improve availability and load balancing.
Use case : [[DR strategy]] [[Failover]]

## Simple routing
Simple routing lets you configure standard DNS records, with no special Route 53 routing such as weighted or latency. With simple routing, you typically route traffic to a single resource, for example, to a web server for your website.

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-simple.html

## Failover routing
Failover routing lets you route traffic to a resource when the resource is healthy or to a different resource when the first resource is unhealthy.

## IP-based routing

IP-based routing gives you granular control to optimize performance or reduce network costs by uploading your data to Route 53 in the form of user-IP-to-endpoint mappings.

### Use Cases
You want to route end users from certain ISPs to specific endpoints so you can optimize network transit costs or performance.

You want to add overrides to existing Route 53 routing types, such as geolocation routing, based on your knowledge of your clients' physical locations.

### Mapping
map user IP with CIDR block