# 137- Replications Hands On
- Go to bucket settings -> Management tab -> scroll down to replication rules
- Can use filters to only apply to some objects
- Need to create IAM roles so S3 can read/write to/from bucket
- Can also use one time batch operation to copy existing objects
- Versions are also equivalent with objects replicated between buckets

- By default, delete markers are not replicated
	- If enabled, delete markers will be replicated
	- So if a file is delete in one bucket, it will be delete in the destination bucket 