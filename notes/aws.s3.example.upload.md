---
id: wevfztpv4jhhcx6tqn9zuyu
title: Upload
desc: ''
updated: 1715905439227
created: 1715904955047
---

# Upload Example

# ! important note
ACL is no longer encouraged for S3. remove ACL from the code example and use bucket policy on S3 side.
<br />
Check: [[Basic Bucket Polidy|aws.s3.basic.Setting up]]

## Queue
1. Make images saved available to public

## Summation

Images saved to S3 might not be publicly available. In that case, you need to adjust permission settings to turn off block public access and enable ACL, then, you use ACL “public-read” option when uploading image from your program.


```jsx
import AWS from 'aws-sdk'
import util from 'util'
import fs from 'fs'

const bucketName = "my-bucket"
const s3 = new AWS.S3({
	accessKeyId: "",
	secretAccessKey: "",
	region: ""
})
const readFile = util.promisify(fs.readFile)
const fileContent = await readFile("image-to-be-saved.jpg")

const uploadResponse = await s3.upload({
	Bucket: bucketName,
	Key: "image-to-be-saved.jpg"
	Body: fileContent
	ContentType: "images/jpeg"
	ACL: "public-read"
})

const savedImageUrl = uploadResponse.Location
```

### By default setup of S3 Bucket, ACL option won't be accepted

1. Go to the bucket on AWS Console
2. Click Permissions tab
    1. Turn off Block public access
    2. Edit Object Ownership → ACLs enabled
    3. Edit Access control list

https://www.learnaws.org/2023/08/26/aws-s3-bucket-does-not-allow-acls/

