# 158- S3 Access Logs
- Set destination bucket under properties
	- Destination must have format `s3://bucket-name/optional-prefix`
- Can also specify log formatting
- So then, things like uploading files, accessing files, etc. will be uploaded to logging bucket
- When we enable access logging, the receiving bucket policy gets auto updated to allow access
- In demo, took several hours for logs to appear 