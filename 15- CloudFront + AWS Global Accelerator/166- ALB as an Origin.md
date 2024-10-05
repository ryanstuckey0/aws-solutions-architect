# 166- ALB as an Origin
- Can use ALB or EC2 instance
- EC2 instance must be public
	- Due to no private VPC connection from CloudFront
	- Security group must contain list of all IP addresses of CloudFront
- Can connect to ALB instead of straight to EC2 instance
	- ALB must be public, but EC2 instance can be private
	- Again, public IP of edge locations must be allowed in security group of ALB 