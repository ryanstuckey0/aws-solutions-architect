# 152- Default encryption vs bucket policies
- SSE-S3 is auto-applied to all new objects in S3 bucket
- For SSE-KMS and SSE-C, can force encryption using a bucket policy that checks for encryption key headers and refuses request otherwise
![400](attachments/Pasted%20image%2020240716185606.png)

- 