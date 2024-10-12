# 220- Lambda in VPC
- Lambda functions are launched in an AWS VPC (not your own)
- Thus, it cannot access resources in your VPS (RDS, ElasticCache, etc.)
	- can only access private resources
- You can launch your Lambda function in your VPC by defining VPC ID, subnets, and security groups
- Lambda will create an elastic network interface in your subnets

## Lambda w/ RDS Proxy
- Since Lambda functions scale to large numbers, it might overwhelm database w/ too many open connections
- Instead, we can run the connections through an RDS proxy to manage the connections for us
- Pool, shares, preserves connections to DB
- For this, Lambda functions **must be launched in your private VPC** as the RDS proxy is never public

![](attachments/Pasted%20image%2020241009162830.png)