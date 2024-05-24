---
id: c11r321ja1x5i7pe313qc4n
title: Policy
desc: ''
updated: 1716512713282
created: 1716509767082
---
# Cue

# Summary

# Note



<hr >

## IAM Policy Structure
1. Version: version of IAM Policy Language
2. Statement: array of object with properties:
    1. Effect
    2. Action
    3. Resource

Note that 1st s3 resouce is for bucket and 2nd is for all objects in the bucket.
```JSON
"Version": "2012-10-17",
"Statement": [
    {
        "Effect": "Allow",
        "Action": [
            "s3:*",
            "dynamodb:Describe*",
            "dynamodb:List*",
            "dynamodb:GetItem"
        ],
        "Resource": [
            "arn:aws:s3:::mys3bucekt",
            "arn:aws:s3:::mys3bucket/*",
            "arn:aws:dynamodb:us-east-1:number:table/mytable"
        ]
    }
]
```

<hr />

## Evaluation Flow
```mermaid
flowchart TB
Deny 
subgraph a[Deny evaluation]
    a1(Default: Deny)
    a2[Evalueate all policies]
    a3{Found explicit deny}
end
a1-->a2-->a3--yes-->Deny

subgraph b[Service Control Policy]
    b1{is principal's account belongs to SCP?}
    b2{Found allow?}
end
a3--no-->b1-->b2--no-->Deny

subgraph c[Resource based Policy]
    c1{has Resource based policy?}
    c2{Found allow?}
    c3(Resource based policy rule)
end
b2-->c1-->c2--yes-->c3

subgraph d[Identity based policy]
    d1{has Id based policy}
    d2{found allow?}
end
c2--no-->d1-->d2--no-->Deny

subgraph e[IAM permission boundaries]
    e1{has Permission boundary?}
    e2{found allow?}
end
d2--yes-->e1-->e2--no-->Deny

subgraph f[Session Policy]
    f1{is principal a session principal?}
    f2{found session policy?}
    f3{found allow}
    f4{is this a role session?}
end
e2--yes-->f1--no-->Allow
f1--yes-->f2--yes-->f3
f2--no-->f4
f3--yes-->Allow
f3--no-->Deny
f4--yes-->Allow
f4--no-->Deny

Allow
```

