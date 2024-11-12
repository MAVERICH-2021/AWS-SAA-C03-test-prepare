Manage your resources on AWS and in multicloud and hybrid environments

# Agent
https://docs.aws.amazon.com/systems-manager/latest/userguide/ssm-agent.html


# Parameter Store
https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html

存放所有可动态加载的参数

# State Manager
automates the process of keeping your Amazon EC2 and on-premises servers in a consistent state. 
allows you to define and maintain desired configurations on your instances, ensuring that they are always compliant with predefined policies or baselines.

This feature is particularly useful for tasks like enforcing security patches, software configurations, and infrastructure management standards across instances.

### Key Capabilities of State Manager:

1. **Configuration Management**: State Manager helps configure and maintain instances at scale. For example, it can ensure that specific software is installed, certain OS configurations are applied, or security policies are enforced on all instances.

2. **Automated Remediation**: If an instance falls out of the desired state (e.g., a required software package is uninstalled or a setting is changed), State Manager can automatically bring it back to compliance by reapplying the defined configuration.

3. **Scheduled Execution**: You can set up schedules to apply configurations at regular intervals, such as every hour or every day, to ensure continuous compliance and detect changes.

4. **Integration with Systems Manager Documents**: State Manager uses Systems Manager documents (SSM documents), which contain scripts or configuration policies, to define the desired state. These documents specify the actions that need to be taken on instances (e.g., installing a package or updating security settings).

5. **Centralized Management and Reporting**: Through the AWS Systems Manager console, you can view the compliance status of instances, review the history of changes, and monitor configuration drift across your environment.

### Common Use Cases for State Manager:

- **Enforcing Security Policies**: Ensuring that all instances have the latest security patches and correct firewall or antivirus settings.
- **Standardizing Environments**: Applying specific OS configurations, file permissions, or application settings across multiple instances.
- **Compliance**: Continuously monitoring instances for drift from predefined configurations and automatically correcting any deviations.
- **Software Deployment**: Installing or updating applications, scripts, or tools consistently across instances.

### Benefits:

- **Reduced Operational Overhead**: Automated configuration management reduces the need for manual intervention.
- **Consistency and Compliance**: Ensures instances remain compliant with company policies and reduces the risk of configuration drift.
- **Scalability**: Allows centralized, scalable management across large numbers of EC2 and on-premises servers.

In summary, **State Manager** helps ensure that your instances are always in the desired configuration state, allowing for better compliance, security, and operational efficiency across your AWS and hybrid environments.