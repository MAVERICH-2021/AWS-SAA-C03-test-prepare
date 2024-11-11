IAM Roles for Service Accounts

You create an **IAM role** that defines the permissions required for a service account and then **annotate** the Kubernetes service account with the **ARN** of that IAM role.

When a pod uses that [[service account]], it can assume the IAM role specified in the annotation, granting it the permissions defined in the IAM policy attached to the role.

- Amazon EKS uses [[OIDC]] to establish a trust relationship between **Kubernetes service accounts** and **IAM roles**. By setting up this trust relationship, the service accounts are able to assume IAM roles securely.
- The OIDC identity provider is configured when setting up EKS, allowing Kubernetes to authenticate service accounts to assume specific IAM roles based on the service account annotations (as mentioned in Option D).