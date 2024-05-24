---
id: 9cmmk3d5f46jjhstt2p5l1k
title: Poclicy & ACLs
desc: ''
updated: 1716391035182
created: 1715905813972
---


## Cue
1. what are recommended to use instead of ACL?
2. what policy should you use when you want centralized control?
3. what's the language of JSON writtenf for IAM Policy called?
<hr />
## Note
### IAM Policy
- Identity based policies.
- written in JSON using the AWS access policy language
- Policies are attached to:
    - users
    - groups
    - roles

### Bucket Policy
- Only for S3 Buckets
- Use AWS access policy language

Policy looks like this: [[aws/basic/2|aws.s3.basic.Setting up]]

### S3 Access Control Lists (ALCS)
- Legacy mechanism
- Recommended to use Bucket Policies or IAM Policies instead
- ACL can be attached to a bucket or directly to an object.

<hr>

### Which one to use?
- Use IAM Policy when you need centralized control
- Use Bucket Policy when you need simpler control

<hr>

### Auth Process
```mermaid
flowchart LR
A(Default is Deny)
B[Evaluate All Policies]
C{Explicit Deny}
D{Is there an allow?}
End1(Deny)
End2(Allow)

End3(Deny by default)
A-->B-->C
C--yes-->End1
C--no-->D
D--yes-->End2
D--no-->End3


```

<hr />

## Summary
IAM Policy and Bucket Policy are encouraged to use instead of ACL. You can use the both and when there is deny for an action in either of the policy, it will be denied.