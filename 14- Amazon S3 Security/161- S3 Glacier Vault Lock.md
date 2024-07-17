# 161- S3 Glacier Vault Lock
- Vault lock is a tool that allows a WORM (write once, read only) model
- Create a vault lock policy- which means object cannot be changed or edited by anybody
- Useful for compliance and data retention

## S3 Object Lock
- Versioning must be enabled
- Can be applied to a single object
- Can block specific object version(s) from being delete for a specified amount of time
- Two retention modes
	- Compliance- 
		- object versions can't be overwritten or deleted by any user (even root)
	- Governance
		- Only a select set of users can change retention mode, or delete object
- Retention period- protects the object for a fixed period
- Legal hold- different kind of hold that protects an object forever
	- There is an IAM permissions- s3:PutObjectLegalHold, which allows any user with this permission to add/remove legal hold