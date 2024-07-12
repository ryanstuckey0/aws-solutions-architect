# 129- S3 Security
- User-based
	- IAM policies- Use IAM policies to determine which API calls are allowed for specific user
- Resource-based
	- Bucket policies- bucket wide rule from the S3 console, allows cross account
	- Object access control list- finer grain (can be disabled)
	- Bucket access control list- less common (can also be disabled)
- an IAM principle can access an S3 object if
	- the user IAM permissions allow it OR the resource policy allows it
	- AND there's no explicit DENY
- Encryption- encrypt objects in Amazon S3 using encryption keys

## S3 Bucket Policies
- JSON based
	- Resources- what buckets/objects policy applies to
	- Effect- Allow/Deny
	- Actions- set of APIs to allow/eny
	- Principal- account or user to apply the policy to
- Can use an S3 bucket policy to 
	- grant public access to bucket
	- force objects to be encrypted at upload
	- grant access to another account\
	![400](attachments/Pasted%20image%2020240711222334.png)

## Public Access & Bucket Policy
- Attach S3 bucket policy that allows anonymous public user to access bucket
- Can also use IAM policy that allows user to directly access bucket
- Can use IAM role to allow EC2 instance to access bucket
- For cross-account access, need to use bucket policy

## Blocking Public Access
- Blocks all public access, even if S3 policy allows public access to bucket
- Acts as an additional safeguard to protect against data leaks
- Can also be set at account level