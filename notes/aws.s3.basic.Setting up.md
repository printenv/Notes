---
id: 1qwucefgy8ignumy1kxto3s
title: Setting up
desc: ''
updated: 1716159250196
created: 1715905341928
---
# Summary

# Queue

# Note

## S3 Basic Setup

managing permissions with ACL is deprecated.
therefore, use bucket policy.

1. Create buckets

- keep all default setting except Block all public access
- untick block all public access
1. Create Policy
    - Go to Permissions tab
    - click Edit on Bucket policy section
    - write policy

```jsx
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::aiam-cms/*"
        }
    ]
}
```

the policy allows all users to retrieve objects from the specified S3 bucket