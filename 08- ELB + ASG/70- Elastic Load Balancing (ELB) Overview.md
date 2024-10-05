- Load balancers are servers that will forward traffic to multiple EC2 instances downstream
- Users are unaware of load balancer- don't know what instance they're connecting to
- Load balancer can health and seamlessly handle failures
- enforce stickiness with cookies
- Elastic load balancer
	- managed by AWS
	- AWS takes care of upgrades, maintenance, high availability
	- Only a couple of settings are available
	- Integrated with many AWS services
- Health checks
	- Used to verify an EC2 instances is properly working
	- Uses port and route to check health
	- If health check is bad, ELB will mark instance as unhealthy and not send traffic to it

## Types of load balancers
- 4 types
- Classic load balancer (CLB)- 2009- v1
	- Supports HTTP, HTTPS, TCP, SSL
- Application load balancer (ALB)- 2016- v2
	- Supports HTTP, HTTPS, WebSocket
- Network load balancer (NLB)- 2017- v2
	- Supports TCP, TLS, UDP
- Gateway load balancer (GWLB)- 2020
	- Operates at layer 3 (network layer)- IP protocol
- Some load balancers can be set up as internal or external

## Security groups
- User can connect to LB on specific ports w/ specific protocols
- EC2 instance can then only accept traffic from load balancer then
	- Security group of EC2 instance will be linked to security group of load balancer
- 