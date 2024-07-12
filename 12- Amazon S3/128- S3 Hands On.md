# 128- S3 Hands On
- Two types- general purpose or directory
	- general purpose- self explanatory
	- directory- low-latency (not in exam)
- Set bucket name- must be unique across all regions
- Object ownership- leave at ACLs disabled
- Block all public access
- Bucket versioning
- Tags
- Encryption- enabled using Amazon S3 managed keys

- If bucket is not set to public, cannot use public bucket URL
	- Must open from AWS console, uses S3 pre-signed URL, which contains signature that verifies ID of requestor