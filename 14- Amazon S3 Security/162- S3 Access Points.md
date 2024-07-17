# 162- S3 Access Points
- Consider a bucket that has a lot of data, and lots of users that want to access it
- If we are creating policies for every set of users that wants to access, this can get messy and the policy will just keep growing as users and data scales
- Can use S3 Access points to solve this
	- Access point policies are just like bucket policies, but grants permissions to certain prefixes
- Each access policy can have different permissions
![](attachments/Pasted%20image%2020240716224157.png)

- Users can then access the access points with correct IAM permissions
- Each access point has its own DNS name (as origin or VPC origin)

## VPC Origins and Access Points
- can define these to be privately accessible, meaning other AWS resources can connect to bucket w/o going through Internet
- need to create VPC endpoint to access the access point
- The VPC endpoint has a policy that must alllow access to target bucket and access point
![400](attachments/Pasted%20image%2020240716224427.png)

