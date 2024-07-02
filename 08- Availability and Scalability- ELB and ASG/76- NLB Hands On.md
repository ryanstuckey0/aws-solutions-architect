- when selecting subnets/AZ, option to have static IP assigned by AWS or use elastic IP
- select security group, similar to ALB
- can select target- instances, Lambda, IP addresses, ALB (same options as ALB)
- select protocol and port
- select health check protocol and port

# Possible problems
- make sure instances are not unhealthy- make sure security group allows traffic from NLB
- 