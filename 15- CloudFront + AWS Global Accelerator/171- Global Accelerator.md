# 171- Global Accelerator
- No free tier of service
- Global accelerator is global- not region based
- Create two resources in two regions (used EC2 in video)
- Create global accelerator, provide name
	- Setup listener (port + protocol)
		- Client affinity- stickiness to GLB
	- Endpoint groups
		- Specifies how to group endpoints by region
		- Traffic dial is weight of traffic that goes to region
		- Health check is configured for EC2 instance
		- Add second endpoint group based on where other application instances are deployed
		- Add endpoint to each group- can be EC2, ALB, NLB, or Elastic IP addresses
- After creation, we get two static IP addresses
	- Also get DNS name
- Cost is charged per hour ran as well as cost / GB
	- Relatively expensive