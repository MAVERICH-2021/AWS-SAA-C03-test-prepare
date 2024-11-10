
AWS provides two levels of protection against DDoS attacks: AWS Shield Standard and AWS Shield Advanced. AWS Shield Standard is automatically included at no extra cost beyond what you already pay for AWS WAF and your other AWS services. For added protection against DDoS attacks, AWS offers AWS Shield Advanced. AWS Shield Advanced provides expanded DDoS attack protection for your Amazon EC2 instances, Elastic Load Balancing load balancers, Amazon CloudFront distributions, and Amazon Route 53 hosted zones.


## Related Services

**[[WAF]]** is a web application firewall that lets you monitor web requests that are forwarded to Amazon CloudFront distributions or an Application Load Balancer. You can also use AWS WAF to block or allow requests based on conditions that you specify, such as the IP addresses that requests originate from or values in the requests. For more information, see the [AWS WAF documentation](https://docs.aws.amazon.com/waf/).

**AWS Firewall Manager** simplifies your AWS WAF administration and maintenance tasks across multiple accounts and resources. With AWS Firewall Manager, you set up your firewall rules just once. The service automatically applies your rules across your accounts and resources, even as you add new resources. For more information, see the [AWS Firewall Manager documentation](https://docs.aws.amazon.com/firewall-manager/).

For more information about choosing the right protection service, see [Which should I choose?](https://docs.aws.amazon.com/waf/latest/developerguide/waf-which-to-choose.html)