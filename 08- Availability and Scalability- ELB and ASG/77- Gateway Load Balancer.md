# 77- Gateway Load Balancer
- Used to deploy, scale, and manage fleet of 3rd party network virtual appliances in AWS
- Examples: firewalls, intrusion detection, prevention systems
- Useful to route all traffic through another application before routing to final destination
- Balances traffic over target group, inspects it, and then drops or forwards traffic it is within parameters
- Operates at layer 3 (network layer) 
- Two main functions
	- Network gateway- single point of entry for all traffic
	- Load balancer- distribute traffic to virtual appliances
- Uses GENEVE protocol on port 6081

## Potential Targets
- EC2 instances
- private IP addresses

Diagram of functionality: [image](Pasted image 20240704145730.png)
