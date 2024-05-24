---
id: 60cyp6ea9uu0kyvce6nx02e
title: Permissions Boundaries
desc: ''
updated: 1716423618106
created: 1716423017175
---

# Note

Permissions boundary restrict permissions. It can be attached to users and roles.<br>
Even when permssion for certain resource is allowed in policy, user or role cannot have that permission if it is not on permission boundary.
```mermaid
flowchart
subgraph policy
    subgraph pAllow[allow]
        S3
        IAM
    end
end
Joanne

subgraph pb[Permission Boundary]
    subgraph pbAllow[allow]
        S3
    end
end

s1[S3]
s2[IAM]

pb --> Joanne
policy --> Joanne

Joanne --Allowed-->s1
Joanne --Not Allowed-->s2

```


