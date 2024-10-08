# 92- AWS Aurora Hands On
- Creation options
	- Standard create- two options w/ MySQL or Postgres compatible
	- Choose template based on production or dev/test
	- credentials
	- cluster storage configuration- Aurora standard, or I/O optimized
	- instance config- can choose instance type- memory optimized, burstable, etc.; also has serverless option
	- availability and durability- lets you create or not create Aurora replicas
	- Connectivity
		- connect to EC2 or don't
		- choose network type- IPv4 or dual stack (IPv4 and IPv6)
		- public vs private access
		- security group
	- Authentication- IAM or Kerberos
	- Enhanced monitoring
	- Other options- backtracking, encryption, log exports, deletion protection
- On creation, we can see we have a regional cluster, then a single writer instance and single reader instance
- When connecting, we will have 1 writer endpoint and 1 reader endpoint
	- Each instance will also have a dedicated endpoint
- Actions
	- Add more readers, another AWS region, cross-region replication
	- Restore from a point in time
	- Add replica auto-scaling
		- Based on average CPU of replicas or average # connections to replicas
		- set min and max capacity
- When deleting, need to delete reader instance, then writer instance, and then can delete whole DB cluster