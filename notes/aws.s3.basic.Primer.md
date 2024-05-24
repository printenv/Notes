---
id: f0e99hy156ji1lw3crxcay9
title: Primer
desc: ''
updated: 1716161137342
created: 1715905258100
---

# Cue
1. how does the s3 resource path start?
2. does s3 have hieararchy like directories?
3. how can a VPC connects to s3 without using public internet gateway?
4. enumerate seven storage classes.

# Summary

# Notes
### Bucket path

- **bucket**.s3.**aws-region**.amazonaws.com
- s3.**aws-region**.amazonaws.com/**bucket**


### Object Storage

- No hierarchy (mimicked by prefixes, e.g. user01_img-a.jpg)
- Cannot be mounted like File Storage

### Object

- Key (name, e.g. test.jpg)
- Version ID
- Value (Data)
- Metadata
- Subresources
- Access control information (not encouraged. [[more info|aws.s3.basic.Setting up]])

### Connecting from VPC

1. Internet gateway (if S3 is public)
2. S3 Gateway Endpoint (if S3 is private)
    1. VPC connects to S3 using private IP address on VPC end
    2. It’s like non public routes inside AWS network
    

### Storage Classes

1. Standard
2. Intelligent Tiering
    1. auto cost optimization
    2. moves data between access tiers based on usage
3. Standard-IA (IA = Infrequent Access)
    1. Lower cost
    2. High retrieval fee
4. One Zone-IA
    1. Stored in a single AZ
5. Glacier Instant Retrieval
    1. Fast access
6. Glacier Flexible Retrieval
    1. Cost effective with flexible access speed
7. Glacier Deep Archive
    1. lowest cost, longest retrieval times.