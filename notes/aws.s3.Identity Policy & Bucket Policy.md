---
id: d1fk1r5o4q4wo1oozqc6dmp
title: Identity Policy & Bucket Policy
desc: ''
updated: 1715914368968
created: 1715912866936
---

Permission are denied by default.<br />
Check this flow chart [[aws.s3.basic.Poclicy & ACLs]]

# Examples
## 1.Identity Policy
1. List all buckets and Get Bucket Location
    1. S3:ListAllMyBuckets: Allows listing all the S3 Buckets in the account
    2. S3:GetBucketLocation: Allows getting the location of any S3 bucket.
2. List Specific bucket
    1. s3:ListBucket: Allows listing the objects in asny S3bucket
3. Put and Get Objects in a Specific Bucket:
    1. s3:PutObject: Allows uploading objects
    2. s3:GetObject: Allows dlownloading objects
```json

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListAllMyBuckets",
                "s3:GetBucketLocation"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::buxs3test/*"
            ]
        }
    ]
}
```

## 2.Bucket Policy
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowDeleteObject",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::123456789012:user/username"
            },
            "Action": [
                "s3:DeleteObject"
            ],
            "Resource": [
                "arn:aws:s3:::bucketname/*"
            ]
        }
    ]
}
```

<hr />
If 1 and 2 are applied and if 1 has additinal deny like bellow, despite bucket policy allowing deletion, deletion will be denied.

``` json
{
    "Sid": "DenyDeleteObject",
    "Effect": "Deny",
    "Action": "s3:DeleteObject",
    "Resource": [
        "arn:aws:s3:::my-example-bucket/*"
    ]
}
```
