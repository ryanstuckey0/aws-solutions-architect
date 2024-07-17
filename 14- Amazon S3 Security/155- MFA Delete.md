# 155- MFA Delete
- Forces MFA for users before running risky operations on AWS S3 buckets
- MFA required to:
	- permanently delete an object version
	- suspend versioning on a bucket
- Only bucket owner (root account) can enable/disable MFA delete