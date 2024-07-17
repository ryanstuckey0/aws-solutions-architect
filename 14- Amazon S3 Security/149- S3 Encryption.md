# 149- S3 Encryption
- Encrypt objects in any of 4 methods
	- Server side encryption (SSE)
		- SSE with Amazon S3- managed keys (SSE-S3) enabled by default
		- SSE with KMS keys stored in AWS KMS (SSE-KMS)
		- SSE with Customer provided keys (SSE-C)
	- Client-side encryption

## SSE-S3
- Encryption keys are handled, managed, and owned by AWS- customer never has access
- Uses AES256
- Must set header to `x-amz-server-side-ecnryption`:`AES256`
	- Tells AWS to encrypt object
- Enabled by default for new buckets and new objects
![](attachments/Pasted%20image%2020240716182243.png)

## SSE-KMS
- Encrypt using keys handled and managed by AWS KMS
- User can control these keys, and see audit trail in CloudTrail (AWS Audit solution)
- Header must be set to `x-amz-server-side-encryption`:`aws:kms`
- To read object, user needs access to key used to encrypt object
![](attachments/Pasted%20image%2020240716182402.png)

### Limitations of SSE-KMS
- Limited by capabilities of SSE-KMS
- Operations (encryption and decryption) call KMS APIs, and each call counts toward KMS calls/second quota
- Quota can be increased using Service Quotas Console

## SSE-C
- Keys are managed outside of AWS by user
- Object is still encrypted with the key we send them, but the key is never stored in AWS servers
- Key is sent in headers, meaning we must use HTTPS
- Encryption key must be provided in header for every single request made
- To read file, user must provide key used to encrypt file
![](attachments/Pasted%20image%2020240716183528.png)

## Client Side Encryption
- Use client library like Amazon's S3 Client-Side encryption library
- Client must both encrypt and decrypt their date when posting and reading objects
![](attachments/Pasted%20image%2020240716183645.png)

## Encrypting Data in Transit 
- Uses SSL/TLS (HTTPS)
- S3 bucket has two end points- HTTP and HTTPS
- Always recommended to use HTTPS

### How can you enforce encryption in transit (i.e., HTTPS)?
- Can attach policy to bucket with condition aws:SecureTransport
- So with the below policy, any GET request would be denied
![](attachments/Pasted%20image%2020240716183859.png)

## DSSE-KMS
- There is also a new type of encryption, which is double encryption based on KMS
- Not in exams yet