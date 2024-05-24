---
id: 2wf8xqjtjoqgh6yekkfq1d1
title: Overview
desc: ''
updated: 1716419819172
created: 1716418090463
---
# Cue

<hr>

# Summary

<hr>

# Note
IAM creates and authenticate principals.<br >
IAM Authorize actions with policies attached to priciplas.<br />
Up to 5,000 users can be created. Users have no permissions by default.
```mermaid
flowchart LR

IAM

subgraph access
    direction LR
    CLI
    Console
    API
end

subgraph principal
    direction LR
    User
    Role
    Application
end

subgraph policy
    direction LR
    p1[Identity based]
    p2[Resource based]
end

subgraph actions
    direction LR
    ec2[Run EC2 Instances]
    s3[Get S3 Bucket]
    iam[Create User with IAM]
end

access-->IAM
IAM-->principal
IAM-->policy-->actions

```

## User Groups, Roles and Policies
``` mermaid
flowchart LR

ug[User Group]

u[User]

subgraph authorization
    direction LR
    Role
    Policy
end

u-->ug
Role --> ug
Role --> u

Policy --> ug
Policy --> u

```