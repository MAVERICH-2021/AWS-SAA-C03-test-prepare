- Blocking Internet or Region-Level Access
goal: **restrict access to AWS resources across regions** and only allow access to **`ap-northeast-3` (Osaka)**,

- **SCPs** allow you to define permissions across multiple accounts in an organization. You can **deny access to all AWS regions except ap-northeast-3** at the account level.
- Example SCP to block other regions:
   
```
{   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Deny",       "Action": "*",       "Resource": "*",       "Condition": {         "StringNotEquals": {           "aws:RequestedRegion": "ap-northeast-3"         }       }     }   ] }
```

- Apply this SCP to the appropriate organizational unit (OU) or account.