# 84- Auto Scaling Group Hands On
- Need to create launch template first
	- Pick AMI, instance type
	- Key pair to use
	- Subnet- not included in template by default
	- security group
	- memory/storage
- Creating auto scaling group
	- select launch template, VPC to us, which subnets/AZ to use
	- select instance requirements
	- Can have a mix of on-demand and spot instances
- Load balancing is optional- if desired, can attach to existing LB or create a new one
- Can specify which health checks to use
- Specify group size- min, max, desired
- Autoscaling policies- optional
- If instance never gets healthy, ASG will terminate instance and create new one
- Can check activity history in ASG to monitor status