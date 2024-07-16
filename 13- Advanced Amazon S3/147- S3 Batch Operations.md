# 147- S3 Batch Operations
- Lets you perform bulk operations on several existing S3 objects with a single request
- Use cases
	- Modify object metadata
	- Encrypt un-encrypted do objects
	- Modify ACLs
	- Restore objects from S3 Glacier
- Job is list of objects, action to perform, and optional parameters
- Why us batch operations over a custom implementation?
	- Offers retries, easy progress tracking, integrated completion notifications
- Can use S3 Inventory and S3 select to filter objects
![400](attachments/Pasted%20image%2020240715181331.png)

