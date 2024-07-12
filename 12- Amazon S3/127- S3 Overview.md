# 127- S3 Overview
- infinitely scaling storage
- many websites are built on top of S3

## Main Use Cases
- Backup/storage
- DR
- Archive
- Hybrid Cloud Storage
- Application Hosting
- Data lakes and big data analytics
- Software delivery
- Static website
- NASDAQ stores 7 years of data in S3 Glacier

## Buckets
- Files (objects) are stored into buckets
- Buckets must have globally unique name (across all regions)
- Buckets defined at region level
- Seems global- but buckets are created in regions
- Naming convention- no uppercase, no underscore, not an IP, cannot start with lowercase letter or number, not start with prefix `xn--` 
- Must not end with suffix `-s3alias`

## Objects
- each object has a key- which is the full path
- so the key for the following is:
	- s3://my-bucket/**my_file.txt**
	- s3://my-bucket/**my_folder01/my_folder02/my_file.txt**
- So there aren't really actually directories, everything is just a key
- Object values are the content of the body
- Max object size  = 5TB
- Files > 5GB must use mutli-part upload
- Metadata - list of key value pairs set by system or user
- Tags- up to 10 key/value pair, useful for security/lifecycle
- Version ID- if versioning is enabled